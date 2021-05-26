---
layout: post
title:  "Building an identity solution with Duende IdentityServer"
date: 2021-05-26 09:30:00 +0100
categories: [development]
tags: [talentech, security, identityserver]
excerpt_separator: <!--more-->
---

Back in 2016 we started looking into how we could modernize our SaaS offering. At the time we were offering a web based application tracking system (ATS) to our customers, built using ASP.NET WebForms and implemented as a monolithic app. We had also recently started offering a second product, a Talent Management system. The two systems had separate user databases, so if a customer used both products, their users would have two separate user accounts and the user experience could have been better.

We saw that we wanted to make some improvements to the user experience, and we also wanted to improve the technical implementation and look into how we could modernize our technical platform.

Our tech stack with ASP.NET WebForms was starting to get a bit dated and we had started to look into [ASP.NET 5](https://www.hanselman.com/blog/aspnet-5-is-dead-introducing-aspnet-core-10-and-net-core-10) as it was called at the time. I think we were a bit lucky with the timing, because after some Googling we quickly found out that Dominick Baier and Brock Allen had just [announced IdentityServer for ASP.NET 5](https://leastprivilege.com/2016/01/11/announcing-identityserver-for-asp-net-5-and-net-core/). To make a long story short, we went all in on IdentityServer and 5 years later we have a solid solution and have a quarter million user accounts and are repidly growing.


<!--more-->

## Supporting a growing application landscape

Initially we used IdentityServer for API authentication only, but we had bigger plans. As mentioned we had two separate products and we wanted to improve the user experience by offering a more seamless integration between these products. We started the work of migrating our two separate user databases into the new centralized user database and could now offer a modern single sign on experience to our users.

It turned out that this was also a smart move, because in 2019 the company HR Manager Talent Solution was aquired by Verdane along with one of our competitors, Webcruiter. Soon after we also merged with ReachMee and Talmundo, and we aquired Weekli and iRecommend. We now had a portfolio of 6 products and it started to become clear that a solid identity platform was a key factor to succeed with our goal of building a talent platform for our customers. The new company launched it's new name, Talentech, and we got a new graphical profile. Each product team put rebranding and integrating with the new common identity platform, Talentech ID, with high priority on their roadmaps.

IdentityServer is not only helping us with authentication, but it has helped us build a more scalable architecture with shared services communicating via REST APIs where we can now handle authentication in a good way across different tech stacks and infrastructures.


## Federation gateway

One big advantage we get with IdentityServer is the support for external identity providers. Where we earlier had a myriad of different integrations with third party identity providers in all our products, we can now have these integrations in one single place and IdentityServer acts as a [federation gateway](https://identityserver4.readthedocs.io/en/latest/topics/federation_gateway.html) for all our products. This gives us a lot more control over our identity structure and simplifies the architecture. 


## Taking identity and access control seriously

We've used Duende IdentityServer to make sure we can offer our users a secure and scalable platform. During the implementation, we've had good help from the team behind IdentityServer and have had several architecture and review sessions with Dominick Baier.

> It has been interesting to follow Talentech on their journey from the initial adoption of IdentityServer to where they are today. With 6 merged companies and a broad range of product offerings, IdentityServer makes sure they can handle identity and access control in a secure and future proof way.
>
>\- _Dominick Baier, Duende Software_


Talentech ID is one of the core parts of our SaaS platform. Building it on Duende IdentityServer gives us the flexibility we need, and at the same time giving us the advantage of leaving protocol implementation to the trusted team at Duende Software. IdentityServer has enabled us to have full control over the UI/UX and it has made it possible to adapt the flows to fit our domain logic and requirements unlike any of the off-the-shelf products we have evaluated. This gives us a lot of possibilities going forward.



