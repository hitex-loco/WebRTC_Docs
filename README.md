#WebRTC (Web Real Time Communication) provides browsers and mobile applications with Real-Time Communications (RTC) capabilities via simple APIs.

#WebRTC APIs are :
	getUserMedia() : capture audio and video.
	MediaRecorder : record audio and video.
	RTCPeerConnection : stream audio and video between users.
	RTCDataChannel : stream data between users.

WebRTC uses RTCPeerConnection to communicate streaming data between browsers, but also needs a mechanism to coordinate communication and to send control messages, a process known as signaling.

#Signaling

Signaling is the process of coordinating communication. In order for a WebRTC application to set up a 'call', its clients need to exchange information :
	- Session control messages used to open or close communication.
	- Error messages.
	- Media metadata such as codecs and codec settings, bandwidth and media types.
	- Key data, used to establish secure connections.
	- Network data, such as a host's IP address and port as seen by the outside world.

This signaling process needs a way for clients to pass messages back and forth. That mechanism is not implemented by the WebRTC APIs to avoid redundancy and to maximize compatibility with established technologies.

!(sig.png?raw=true)

WebRTC is designed to work peer-to-peer, so users can connect by the most direct route possible. However, WebRTC is built to cope with real-world networking: client applications need to traverse NAT gateways and firewalls, and peer to peer networking needs fallbacks in case direct connection fails. As part of this process, the WebRTC APIs use STUN servers to get the IP address of your computer, and TURN servers to function as relay servers in case peer-to-peer communication fails.

#WebRTC Architecture :

!(wrtc_arch.png?raw=true)
