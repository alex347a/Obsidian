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

### Part 2: TCP
![[Pasted image 20251020120139.png]]

### Part 3: Changing functionality of one chosen protocol (UDP)
![[Pasted image 20251020120845.png]]
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