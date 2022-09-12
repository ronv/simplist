---
date: "2019-11-17T00:00:00Z"
description: How to setup free SSL certificate using Cloudflare.
summary: How to setup free SSL certificate using Cloudflare.
categories:
- article
tags:
- security
- cloudflare
title: Get free SSL for your website with Cloudflare
---
### What is SSL?

SSL (Secure Socket Layer) is the standard security technology for establishing an encrypted link between a web server and a browser. This secure link ensures that all data transferred remains private. It’s also called TLS (Transport Layer Security). Millions of websites use SSL encryption everyday to secure connections and keep their customer’s data safe from monitoring and tampering.

### Why do you need an SSL certificate on your website?

Every website on the Internet should be served over HTTPS. Here’s why:

* Performance: Modern SSL can actually improve page load times.
* Search Ranking Boost: Search engines favor HTTPS websites.
* Security: Encrypting traffic with SSL ensures nobody can snoop on your users’ data.
* Trust: By displaying a green lock in the browser’s address bar, SSL increases visitor’s trust.
* Regulatory Compliance: SSL is a key component in PCI compliance.

The Cloudflare Universal SSL certificate is an SSL certificate provided absolutely free of charge to everyone who would like to use that type of SSL certificate for securing the connection to their website absolutely free of charge. 

### Today, we’ll walk through the simple steps for setting up SSL with Cloudflare.

* First, create your free Cloudflare account.
* Add your site.
* Select the free plan. For most websites, the free plan would be enough. Just select it and click on ‘Continue’.
* Change your domain name servers to those provided by Cloudflare. You need to point your name servers to Cloudflare. To do this you would have to log into your domain registrar account, find the setting to change the name servers.
* Now you will only have to access the Crypto icon located across the top of your dashboard. The option you are looking for here is Flexible SSL as the other options will require from you to have an existing SSL certificate and also those are only available on the paid plans Cloudflare provides.
* The SSL certificate will be issued in an hour or so. You can check the status from the ‘Crypto’ page once it is issued.

That's it! SSL certificate is configured and your will see a lock icon on your website.
