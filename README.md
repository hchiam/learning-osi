# Learning the OSI model (and TCP/IP model)

Just one of the things I'm learning. https://github.com/hchiam/learning

OSI model = Open Systems Interconnection model.

- https://www.reddit.com/r/computing/comments/1o5cmp/eli5_osi_layer_model

- https://simple.wikipedia.org/wiki/OSI_model

- https://en.wikipedia.org/wiki/OSI_model#Comparison_to_other_networking_suites

## Simple practical perspective

My summary of "Practical Networking" videos https://www.youtube.com/watch?v=LkolbURrtTs and https://www.youtube.com/watch?v=0aGqGKrRE0g

1) Physical layer = bits ("physics")
2) Data Link layer = hops (MACs, e.g. router MACs). Add header to data = data is now called a "frame".
3) Networking layer = ends (IPs, e.g. server IPs). Add header to data = data is now called a "packet".
4) Transport layer = services (e.g. ports/programs, like at TCP/UDP/etc ports). Add header to data = data is now called a "segment".
5) 5+6+7 Application layer = data
  - under TCP/IP model for networking, "Application layer" covers (Session layer, Presentation layer, Application layer) and can be conceptually grouped together in practice, left to specific implementations
  - btw, layers 1 (Physical) and 2 (Data Link) are also groupable under "Network Access layer"; layer 3 (Network) rename-able to "Internet layer": layer 4 (Transport) rename-able to "Host to Host layer".

## 7 layers

Host layers:

- (7) Application (top-most; UI, cookies, etc.)
- (6) Presentation (translates data to/from UI, security encryption/(de)compression/encoding)
- (5) Session (client/server request/response communication, open/close sessions)
- (4) Transport (reliability, quality, flow control, security(?), not actually sending. segmentation + ports.)

Media layers:

- (3) Network (plan data path itinerary + organize/reassemble data, logical addressing. packets + source/destination IPs)
- (2) Data Link (disassemble data into frames, check/correct errors, physical addressing. frames + source/destination MAC address)
- (1) Physical (bottom-most; hardware)

The process goes from the top-level concerns down to the bottom-level and back up:

7 -> 6 -> 5 -> 4 -> 3 -> 2 -> 1 -> 2 -> 3 -> 4 -> 5 -> 6 -> 7

Here's a list of which parts of the OSI model different protocols correspond to: https://en.wikipedia.org/wiki/OSI_model#Comparison_to_other_networking_suites (note that some things like TCP/IP and security span different layers).

## Further reading

- OSI model: https://www.cloudflare.com/en-gb/learning/ddos/glossary/open-systems-interconnection-model-osi/ and https://www.youtube.com/watch?v=dV8mjZd1OtU - the OSI model helps you troubleshoot network problems
  - data > segments > packets > frames > bit stream
- TCP/IP model: https://www.geeksforgeeks.org/tcp-ip-model/ (BTW Internet protocol suite = TCP/IP) (BTW TCP/IP model is closer than OSI model to modern internet) and https://www.youtube.com/watch?v=F5rni9fr1yE **just 4 layers:**
  1. Process/App Layer (OSI layers 7+6+5 = Application + Presentation + Session)
  2. Host-to-Host/Transport Layer (OSI layer 5 = Transport)
  3. Internet Layer (OSI layer 3 = Network)
  4. Network Access/Link Layer (OSI layers 2+1 = Datalink + Physical)

TCP/IP model:

1. Process/App Layer (HTTP, HTTPS, FTP, SMTP, SSH, DNS, DHCP, ...)
   - port
2. Host-to-Host/Transport Layer (TCP, UDP)
   - packets (and reassembly meta info)
3. Internet Layer (IP, ARP, RARP, IGMP)
   - add source and destination IP addresses
4. Network Access/Link Layer (hardware)
   - assign MAC addresses of sender and receiver to each packet
   - convert to 1's and 0's
