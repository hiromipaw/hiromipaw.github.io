---
title: 'Using Solid with Tor .onion services. How to decentralise your online identities.'
date: 2019-06-21
permalink: /posts/2019/04/solid-tor-onion-services/
tags:
  - tor
  - privacy
  - web
  - anonymity
  - solid
---

Tor is an important tool providing privacy and anonymity online. The property of anonymity itself is more than just providing an encrypted connection between the source and the destination of a given conversation. Encryption only prevents the content of the communication between two parties from becoming known, but there is a lot of information that can still be learned by just observing the traffic.

A lot of information is given away by certain properties of communications beyond just the content. These properties are usually referred to as communication metadata. Metadata include information such as the lenght of the conversation, who was involved, where are the parties involved in the conversation located, and so on.

Questions that can be answered by looking at metadata are:
- how long you talk, how often ...
- the people you talk to, or a group of people that communicate between eachothers frequently ... - network addresses, traffic patterns
- location services, geo-coding ...

As you see Metadata give a lot away about you even if the actual content of your communication is encrypted. We could also say that the metadata can give away more information than reading the actual content, and in a form that is easily processed by machines.

When you use the Tor network, you are not sharing your communication metadata. So that, not only your communication are encrypted, but you can also stay anonymous. Anonymity is a broad concept, and it can mean different things to different groups.

The main advertised property of the Tor network is that it provides strong anonymity given a variety of people using the network.
For the Tor network to function properly and to satisfy users' needs, we need a certain degree of diversity. We need diversity in the relays comprising the network and in the user population sending traffic through it. We want Tor to be able to reach and serve a diverse population of users and use cases. We believe everyone should be able to browse the web and enjoy privacy, independently of where they live and who they are.

But hiding network traffic is not all you have to do to be protect websites and services from tracking you online. There is a lot of information that is given away when you use your google or facebook accounts to login to a third party service.

The risk in this case doesn't only involve you transferring your profile information to a third party service, but also Facebook and Google learning about how and which third party services you use.

Tor provides a technology called onion services that allows users to offer various kinds of services, such as web publishing or an instant messaging server making that available on the Tor network. Using Tor "rendezvous points," other Tor users can connect to these .onion services, formerly known as hidden services, each without knowing the other's network identity.

An .onion service needs to advertise its existence in the Tor network before clients will be able to contact it. Therefore, the service randomly picks some relays, builds circuits to them, and asks them to act as introduction points by telling them its public key. By using a full Tor circuit, it's hard for anyone to associate an introduction point with the .onion server's IP address. While the introduction points and others are told the onion service's identity (public key), we don't want them to learn about the onion server's location (IP address).

In a-not-so imaginary more privacy friendly web, applications could be made available through onion services and we could use different identity providers that wouldn't necessarly need to access and share all our data, therefore without us losing control over our online footprints.

Recently I have have learned about Solid. Solid can be defined as a set of protocols leveraging on the idea of the semantic web to allow online applications to access user data. Building on top of hypermedia protocols, Solid is completely compatible with the current technologies of the web.
With Solid all your data are stored in an online Solid Pod. The data is owned by the user who is always free to move it as they wanted.

Users can give other users or services permission to read or write to their POD. This approach is great for services' developers while also protecting user privacy. Ultimately the user retains control on their pod.

I have created a test application running on onion services and connecting to a solid community pod. This example is particularly interesting, because by using the .onion protocol the solid pod doesn't know about the app retrieving data. They will just see their .onion address.

The code is available via the [myonion wrapper](https://github.com/hiromipaw/myonion). An experiment in making available through docker containers different app via .onion services.

In this post we show how a web application made available through .onion on the Tor network can exchange information with a Solid pod and allow a user to login and share some data. Because .onion services live on the Tor network, you do not need hosting or a public ip address to offer some service via .onion address. This means .onion services are a gateway to a decentralised, peer-to-peer internet, where you regain control on the content you create and who you are sharing it with. The .onion is hosted on your computer for the time you desire, allowing the people visiting your site to remain anonymous, and also you. We believe anonymity to be very important since it can free people, allowing them to decide how to expose themselves or to make themselves visible on their own terms.
