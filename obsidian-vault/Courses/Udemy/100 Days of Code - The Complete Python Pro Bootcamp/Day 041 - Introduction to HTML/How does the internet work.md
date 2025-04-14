# How does the internet work?

Internet is like a long wire with computers connected to it at various points.

Servers are one such computers connected to this wire that serves data 24/7.

Clients are computers that use the internet to access data from the servers.

A Web server is a giant library that is open 24/7.

For example, if I want to access ' [https://www.google.com](https://www.google.com) '

![[Pasted image 20231010092047.png|500]]

The browser will send the message to an ISP(Internet Service Provider) that I want to visit the google homepage.

You need to pay the ISP to access the internet.

The ISP will relay the message to DNS(Domain Name System) server.

The DNS server is like a phone book that contains the exact IP address of where the data requested is available.

Every computer connected to the internet has its own unique IP address. Something like, 192.18.1.1.

The DNS server upon finding the direct IP address will send it back to the client via ISP.

The Client can then directly contact the Google severs using the direct IP address.

Large websites like google use Dynamic IP address and Content Delivery Networks(CDNs) allows you to get access to the closest Google servers geographically.