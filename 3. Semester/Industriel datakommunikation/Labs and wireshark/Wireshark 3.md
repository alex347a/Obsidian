1. Is your browser running HTTP version 1.0, 1.1, or 2? What version of HTTP is the server running?
![[Pasted image 20250915102155.png]]
HTTP 1.1
2. What languages (if any) does your browser indicate that it can accept to the server?
![[Pasted image 20250915102243.png]]
Engelsk US og engelsk

3. What is the IP address of your computer? What is the IP address of the gaia.cs.umass.edu server?
![[Pasted image 20250915102506.png]]
Min IP: 10.126.90.208
Skolens IP: 128.119.245.12
4. What is the status code returned from the server to your browser?
![[Pasted image 20250915102628.png]]
Status code 200: OK.

5. When was the HTML file that you are retrieving last modified at the server?
![[Pasted image 20250915102743.png]]
6. How many bytes of content are being returned to your browser?
![[Pasted image 20250915102909.png]]
128 bytes.
7. By inspecting the raw data in the packet content window, do you see any headers within the data that are not displayed in the packet-listing window? If so, name one.
I do not.

8. Inspect the contents of the first HTTP GET request from your browser to the server. Do you see an “IF-MODIFIED-SINCE” line in the HTTP GET?
![[Pasted image 20250915103837.png]]
Yes.

9. Inspect the contents of the server response. Did the server explicitly return the contents of the file? How can you tell?
![[Pasted image 20250915105239.png]]
It says file data 371 bytes in the first get message but in the cache it doesn't return data.

10. Now inspect the contents of the second HTTP GET request from your browser to the server. Do you see an “IF-MODIFIED-SINCE:” line in the HTTP GET? If so, what information follows the “IF-MODIFIED-SINCE:” header?
![[Pasted image 20250915105652.png]]
Yes, it gives a date.
11. What is the HTTP status code and phrase returned from the server in response to this second HTTP GET? Did the server explicitly return the contents of the file? Explain.
![[Pasted image 20250915105855.png]]
304 Not modified.

12. How many HTTP GET request messages did your browser send? Which packet number in the trace contains the GET message for the Bill or Rights?
![[Pasted image 20250915110847.png]]
I got 1 request, but 4 TCP 
I think it was packet number 9:
![[Pasted image 20250915111242.png]]
13. Which packet number in the trace contains the status code and phrase associated with the response to the HTTP GET request?
The first packet has the status code.

14. What is the status code and phrase in the response?
![[Pasted image 20250915150831.png]]
Status code 200 and phrase OK.

15. How many data-containing TCP segments were needed to carry the single HTTP response and the text of the Bill of Rights?
If you just look at the above picture you can see 4 TCP segments between the two HTTP segments.

16. How many HTTP GET request messages did your browser send? To which Internet addresses were these GET requests sent?
![[Pasted image 20250915151635.png]]
It sent 4 GET messages. They were sent to my computer Alexanders_ASUS.lan

17. Can you tell whether your browser downloaded the two images serially, or whether they were downloaded from the two web sites in parallel? Explain.
![[Pasted image 20250915152901.png]]
![[Pasted image 20250915152938.png]]
Since the first image is get and acknowledged before the second image is gotten that must mean its downloaded serially.

18. What is the server’s response (status code and phrase) in response to the initial HTTP GET message from your browser?
![[Pasted image 20250915153532.png]]
It says 401 Unauthorized.

19. When your browser’s sends the HTTP GET message for the second time, what new field is included in the HTTP GET message?
![[Pasted image 20250915153817.png]]
Authorization is included which consists of the username and password separated by a colon. Credentials: wireshark-students:network 