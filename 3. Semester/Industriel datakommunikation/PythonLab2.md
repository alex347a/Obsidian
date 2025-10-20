### Part 1: UDP
![[Pasted image 20251020115704.png]]
#### Code:
##### Server
```Python
import socket

  

def udp_server():

    server_socket = None

    try:

        server_socket = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)

        server_address = ('localhost', 12000)

        server_socket.bind(server_address)

        server_socket.settimeout(1.0)

        print("UDP Server is listening on port 12000...")

        print("Press Ctrl+C to stop the server")

        while True:

            try:

                data, client_address = server_socket.recvfrom(1024)

                message = data.decode('utf-8')

                print(f"Received from {client_address}: {message}")

                modified_message = message.upper()

                server_socket.sendto(modified_message.encode('utf-8'), client_address)

                print(f"Sent to {client_address}: {modified_message}")

            except socket.timeout:

                # Normal timeout - continue waiting for data or KeyboardInterrupt

                pass

            except KeyboardInterrupt:

                # This will break the inner loop and be caught by the outer try-except

                raise

            except Exception as e:

                print(f"Unexpected error: {e}")

                # Continue running for other errors

    except KeyboardInterrupt:

        print("\nServer is shutting down gracefully...")

    finally:

        if server_socket:

            server_socket.close()

            print("Server socket closed successfully")

        print("Server shutdown complete")

  

if __name__ == "__main__":

    udp_server()
```
##### Client:
```Python
import socket

  

def udp_client():

    # Create a UDP socket

    client_socket = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)

    server_address = ('localhost', 12000)

    try:

        while True:

            # Get input from user

            message = input("Enter a message to convert to uppercase (or 'quit' to exit): ")

            if message.lower() == 'quit':

                break

            # Send data to server

            client_socket.sendto(message.encode('utf-8'), server_address)

            # Receive modified data from server

            modified_data, server = client_socket.recvfrom(1024)

            modified_message = modified_data.decode('utf-8')

            print(f"Server response: {modified_message}\n")

    except KeyboardInterrupt:

        print("\nClient is shutting down...")

    finally:

        client_socket.close()

  

if __name__ == "__main__":

    udp_client()
```
### Part 2: TCP
![[Pasted image 20251020120139.png]]
#### Code: 
##### Server:
```Python
import socket

  

def tcp_server():

    server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

    server_socket.setsockopt(socket.SOL_SOCKET, socket.SO_REUSEADDR, 1)  # Prevent "Address already in use"

    server_address = ('localhost', 12000)

    server_socket.bind(server_address)

    server_socket.listen(5)  # Allow multiple pending connections

    server_socket.settimeout(1.0)  # ← CRITICAL: Timeout for accept()

    print("TCP Server is listening on port 12000...")

    print("Press Ctrl+C to stop the server")

    connections = []  # Track all active connections

    try:

        while True:

            try:

                # Accept new connections (with timeout)

                connection, client_address = server_socket.accept()

                connection.settimeout(1.0)  # Set timeout for this connection too

                connections.append(connection)

                print(f"New connection from {client_address}")

                print(f"Active connections: {len(connections)}")

            except socket.timeout:

                # No new connections - this is normal

                pass

            except OSError as e:

                print(f"Accept error: {e}")

                break

            # Check existing connections for data

            for connection in connections[:]:  # Use slice copy to avoid modification during iteration

                try:

                    data = connection.recv(1024)

                    if data:

                        # Received data

                        message = data.decode('utf-8')

                        print(f"Received: {message}")

                        # Process and send response

                        modified_message = message.upper()

                        connection.sendall(modified_message.encode('utf-8'))

                        print(f"Sent: {modified_message}")

                    else:

                        # Client disconnected gracefully

                        print("Client disconnected")

                        connection.close()

                        connections.remove(connection)

                except socket.timeout:

                    # No data from this client - continue to next connection

                    continue

                except ConnectionResetError:

                    # Client disconnected unexpectedly

                    print("Client disconnected unexpectedly")

                    connection.close()

                    connections.remove(connection)

                except OSError:

                    # Connection error

                    connection.close()

                    connections.remove(connection)

    except KeyboardInterrupt:

        print("\nServer is shutting down gracefully...")

    finally:

        # Clean up ALL connections

        print(f"Closing {len(connections)} active connections...")

        for connection in connections:

            try:

                connection.close()

            except:

                pass

        server_socket.close()

        print("Server shutdown complete")

  

if __name__ == "__main__":

    tcp_server()
```
##### Client:
```Python
import socket

  

def tcp_client():

    # Create a TCP socket

    client_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

    server_address = ('localhost', 12000)

    try:

        # Connect to the server

        client_socket.connect(server_address)

        print(f"Connected to server at {server_address}")

        while True:

            # Get input from user

            message = input("Enter a message to convert to uppercase (or 'quit' to exit): ")

            if message.lower() == 'quit':

                break

            # Send data to server

            client_socket.sendall(message.encode('utf-8'))

            # Receive modified data from server

            modified_data = client_socket.recv(1024)

            modified_message = modified_data.decode('utf-8')

            print(f"Server response: {modified_message}\n")

    except ConnectionRefusedError:

        print("Could not connect to the server.")

    except KeyboardInterrupt:

        print("\nClient is shutting down...")

    finally:

        client_socket.close()

        print("Connection closed")

  

if __name__ == "__main__":

    tcp_client()
```
### Part 3: Changing functionality of one chosen protocol (UDP)
![[Pasted image 20251020120845.png]]
#### Code
##### Server
```Python
import socket

  

count = 0

  

def udp_server():

    server_socket = None

    try:

        server_socket = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)

        server_address = ('localhost', 12000)

        server_socket.bind(server_address)

        server_socket.settimeout(1.0)

        print("UDP Server is listening on port 12000...")

        print("Press Ctrl+C to stop the server")

        while True:

            try:

                data, client_address = server_socket.recvfrom(1024)

                message = data.decode('utf-8')

                print(f"Received from {client_address}: {message}")

                character_count = len(message)

                print(f"Message length: {character_count} characters")

                server_socket.sendto(str(character_count).encode('utf-8'), client_address)

                print(f"Sent to {client_address}: {character_count}")

  

            except socket.timeout:

                # Normal timeout - continue waiting for data or KeyboardInterrupt

                pass

            except KeyboardInterrupt:

                # This will break the inner loop and be caught by the outer try-except

                raise

            except Exception as e:

                print(f"Unexpected error: {e}")

                # Continue running for other errors

    except KeyboardInterrupt:

        print("\nServer is shutting down gracefully...")

    finally:

        if server_socket:

            server_socket.close()

            print("Server socket closed successfully")

        print("Server shutdown complete")

  

if __name__ == "__main__":

    udp_server()
```
##### Client (same as UDP in part 1)
```Python
import socket

  

def udp_client():

    # Create a UDP socket

    client_socket = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)

    server_address = ('localhost', 12000)

    try:

        while True:

            # Get input from user

            message = input("Enter a message to convert to uppercase (or 'quit' to exit): ")

            if message.lower() == 'quit':

                break

            # Send data to server

            client_socket.sendto(message.encode('utf-8'), server_address)

            # Receive modified data from server

            modified_data, server = client_socket.recvfrom(1024)

            modified_message = modified_data.decode('utf-8')

            print(f"Server response: {modified_message}\n")

    except KeyboardInterrupt:

        print("\nClient is shutting down...")

    finally:

        client_socket.close()

  

if __name__ == "__main__":

    udp_client()
```