# Learning the OSI model

Just one of the things I'm learning. https://github.com/hchiam/learning

OSI model = Open Systems Interconnection model.

- https://www.reddit.com/r/computing/comments/1o5cmp/eli5_osi_layer_model

- https://simple.wikipedia.org/wiki/OSI_model

- https://en.wikipedia.org/wiki/OSI_model#Comparison_to_other_networking_suites

## 7 layers

Host layers:

- (7) Application (top-most; UI)
- (6) Presentation (translates data to/from UI, security encryption)
- (5) Session (client/server request/response communication, sessions)
- (4) Transport (reliability, quality, flow control, security(?), not actually sending)

Media layers:

- (3) Network (plan data path itinerary + organize/reassemble data, logical addressing)
- (2) Data Link (disassemble data into frames, check/correct errors, physical addressing)
- (1) Physical (bottom-most; hardware)

The process goes from the top-level concerns down to the bottom-level and back up:

7 -> 6 -> 5 -> 4 -> 3 -> 2 -> 1 -> 2 -> 3 -> 4 -> 5 -> 6 -> 7

Here's a list of which parts of the OSI model different protocols correspond to: https://en.wikipedia.org/wiki/OSI_model#Comparison_to_other_networking_suites (note that some things like TCP/IP and security span different layers).

## Further reading

- OSI model: https://www.cloudflare.com/en-gb/learning/ddos/glossary/open-systems-interconnection-model-osi/ helps you troubleshoot network problems
- TCP/IP model: https://www.geeksforgeeks.org/tcp-ip-model/ (BTW Internet protocol suite = TCP/IP) (BTW TCP/IP model is closer than OSI model to modern internet)
  1. Process/App Layer
  2. Host-to-Host/Transport Layer
  3. Internet Layer
  4. Network Access/Link Layer
