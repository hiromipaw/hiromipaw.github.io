---
title: "Peeling onions: understanding and using the Tor network."
collection: talks
type: "Talk"
permalink: /talks/2018-02-04-peeling-onions
venue: "FOSDEM"
date: 2018-02-04
location: "Brussels, Belgium"
---

Tor is an important tool providing privacy and anonymity online. The property of anonymity itself is more than just providing an encrypted connection between the source and the destination of a given conversation. There is in fact a lot of information that can be still learned by just observing encrypted communications. Anonymity is a broad concept, and it can mean different things to different groups. The main advertised property of the Tor network is that it provides strong anonymity given a variety of people using the network. The Tor network itself is only a part of what Tor is. Tor also provides privacy at the application level through the Tor Browser. This talk is going to present what Tor is and how it works. We are also going to present new features we have been developing lately. Finally we are going to explain how you can build applications that use Tor.

Tor is an important tool providing privacy and anonymity online. The property of anonymity itself is more than just providing an encrypted connection between the source and the destination of a given conversation. Encryption only prevents the content of the communication between Alice and Bob from becoming known.

There is in fact a lot of information that can still be learned by just observing encrypted communications. For example, it is always possible to guess certain information by learning some properties of the conversation beyond just the content, such as the length of the conversation, or who was involved, or even guessing a group of people that communicate with a certain frequency. These properties are called metadata and can be used to describe information even when the full data is not available.

Anonymity is a broad concept, and it can mean different things to different groups. The main advertised property of the Tor network is that it provides strong anonymity given a variety of people using the network. For the Tor network to function properly and to satisfy users' needs, we need a certain degree of diversity. We need diversity in the nodes comprising the network and in the user population sending traffic through it. Lately, we have been introducing new traffic scheduling features in the network in order to solve problems, reduce congestion and improve overall performance.

The Tor network itself is only a part of what Tor is. Tor also provides privacy at the application level through the Tor Browser.

Other applications can also make use of the Tor network to be more secure. In this case Tor can provide bi-directional anonymity by making it possible for users to hide their locations while offering various kinds of services, such as web publishing or an instant messaging server. The next generation onion services have been recently launched in alpha and we are excited to touch on some of the new features that have been introduced on the old hidden service design.

[Slides](https://archive.fosdem.org/2018/schedule/event/tor/attachments/slides/2453/export/events/attachments/tor/slides/2453/slides_.pdf)

[Video](https://video.fosdem.org/2018/H.1301/tor.mp4)
