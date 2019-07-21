---
title: "Onion adventures: how to use onion services and the Tor network in your web endeavors"
collection: talks
type: "Talk"
permalink: /talks/2019-02-02-onion-adventures
venue: "FOSDEM"
date: 2019-02-02
location: "Brussels, Belgium"
---

Tor is an important tool providing privacy and anonymity online. The Tor network itself is only a part of what Tor is. Tor also provides privacy at the application level through the Tor Browser. The Tor Browser was designed to provide privacy while surfing the web and defend users against both network and local forensic adversaries. The same properties can be adopted by applications and services wishing to integrate the tor network in their architecture. Furthermore, onion services provide better authentication and assurance of who you are talking to. With onion services Tor can provide bi-directional anonymity by making it possible for users to hide their locations while offering various kinds of services, such as web publishing or an instant messaging server. This talk is going to explain how it is possible to integrate tor and build onion applications.

or is an important tool providing privacy and anonymity online. The property of anonymity itself is more than just providing an encrypted connection between the source and the destination of a given conversation. Encryption only prevents the content of the communication between Alice and Bob from becoming known. There is in fact a lot of information that can still be learned by just observing encrypted communications. For example, it is always possible to guess certain information by learning some properties of the conversation beyond just the content, such as the length of the conversation, or who was involved, or even guessing a group of people that communicate with a certain frequency. These properties are called metadata and can be used to describe information even when the full data is not available.

Anonymity is a broad concept, and it can mean different things to different groups. The main advertised property of the Tor network is that it provides strong anonymity given a variety of people using the network. For the Tor network to function properly and to satisfy users' needs, we need a certain degree of diversity. We need diversity in the nodes relays comprising the network and in the user population sending traffic through it. Lately, we have been introducing new traffic scheduling features in the network in order to solve problems, reduce congestion, and improve overall performance. The Tor network itself is only a part of what Tor is. Tor also provides privacy at the application level through the Tor Browser.

Other applications can also make use of the Tor network to be more secure. Onion services provide better authentication and assurance of who you are talking to. In this case, Tor can provide bi-directional anonymity by making it possible for users to hide their locations while offering various kinds of services, such as web publishing or an instant messaging server.

This talk is going to introduce what it does mean to do web development with privacy in mind. We will start by presenting a few example of applications that use onion services and follow up with tips on how to integrate onion services in your architecture and how to provide a seamless frontend experience for privacy-concerned people that prefer to use the Tor Browser.



[Slides](https://fosdem.org/2019/schedule/event/onion_adventures/attachments/slides/3049/export/events/attachments/onion_adventures/slides/3049/onion_adventures.)

[Video](https://video.fosdem.org/2019/UD2.218A/onion_adventures.mp4)