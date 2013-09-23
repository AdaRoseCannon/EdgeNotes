Real Time Data
==============

Websockets have now been with us for several years and enjoy near universal support. WebRTC is just starting out. Chat, live blogging, telemetry/dashboards, remote assist and video conferencing are all proven and popular use cases for real time data. Developers are becoming increasingly comfortable integrating real time elements into new projects, but problems remain with the complexity of scaling a real-time backend, as well as implementing APIs that are practical and useful.

There has been many ways to do realtime communication over the years. The current main implementations are WebRTC and sockets.

They are now easy enough that they pass the 'mum test'.

## Low Latency Peer to Peer Networking

See peerCDN

Allow users viewing a file to share it to other users visiting the site.

Also pro security with result to NSA etc.

## How is it coming along?

att.js

Demo for making and recieving phone calls in the browser. Support is pretty good but it is still quite finicky.

## Set up a video call.

See slide very complex.

Screensharing requires https. 

There are many different way to do videos on different browsers.

## Signaling server

* Not speced
* Help users find each other
* capabilities detection.
* Screensharing between chrome and firefox does not work.

### Peer connections 

* preFixed
* createDataChannel (Very finnicky)
* Upload limitation in chrome!!!
* It's going to be really difficult because all browser manufacturers need to agree on a spec.
..* PeerJS
..* OpenTok

###Notes;

WebRTC needs to be tinkerable to take off. Needs some cool work to go.

 Applause

* Websockets is now only coming into it's own after 2 years.
* What's next for WebRTC?
* Sockets and WebRTC solve different problems.
* WebRTC has lots of different potential possibilities.

# Questions

### Corporate firewalls block proxies and peer to peer. How can the technology cope with this.

* It's gettting better, encryption (ssl) can avoid interception. But not enough, reuse existing transports bt ideally the web browser needs to give more information to the webapp.
* Schools block ssl which can be a very big problem.
* Difficult problem to solve to break through firewalls.
* More information from people with experience in these feilds is needed.

### When to use websockets vs webrtc
* Sockets is client to server and webrtc is p2p.
* Sockets is reliable but slow and webrtc is unreliable but fast.
* Communicating with a game server via udp in the browser would be awesome.
* WebSockets and WebRTC are complimentary and overlap.
* Server sent events overlaps websockets and is also complimentary.
* Websockets is more versatilel than SSE.
* Bidirectional websockets over http2??

### WebRTC spec has made centralised solutions to a decenturalised problems how can we make it flly decenturalised.
* Firewalls make this too difficult but someone is currently working on it.
* Need to figure out away to see who is arond without a central server.
* Discoverability is a problem. It would be nice to go completely peer to peer. 
* Also trying to connect to local devices would be nice to not need a central server.
* An interesting solution is to play audio to transmit connection/routing data to set up WebRTC.

### Too many TCP connections can kill a webserver how do you solve keep alive to stop this problem?
* Only one handshake can be made at a time.
* SPDY as an envelope tends to solve this problem.

### Bandwidth throttling from tcp streams is hard to do.
* Two problems:
* Skype will use the strongest device for the rebroadcaster.
* Upload bandwidth can be a bottleneck as WebRtC does not throttle down.
* Throttling bandwidth is the 'secret sauce' for streaming problems.
* Need to be able to automatically adjust streaming size.
* This problem is solved in some situations need to be handled creatively to make sure only the right people recieve the correct information.
* Early days yet. 
* Battery life on mobile device e.g. if a mobile device had many connections need to send Nx as much data.
* Video + WebRTC would kill mobile devices because video + network is very power intensive.
* Responsive video.
* The current usecase is audio/video but can be used for games as well.
* Is battery draining really an issue?
* (Audience says yes)
* Some native apps do not care about battery power are we too holier than thou?

### WebRTC focuses on audio/video?
* Should it just be any data where the type of data is encapsulated at the start.
* Can it be used for just regualr data?
* WebRTC should be able to do it but there is not a lot of exploration in that area.
* Data channels is the next big area.
* Also any other information Temperature data?
* It's a 'disruptive' you can build your own telecom!!

### What are cool possibilities (each panel member)?
* Using a users device at conference as a microphone.
* Finding devices in the room using a geolocation api.
* Enabling internet of thing because devices could talk to one another without a centralised server. Web of things (higher level than internet of things)
* Broadcasting live from a phone!!
* Multiplayer video gaming.
* Web of things (again)
* Ultra low latency connection between through objects in the browser.