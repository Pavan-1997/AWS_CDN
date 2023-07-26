# AWS CDN

Before CDN - Say a user uploads a reel to Instagram which stores that in Central Storage (say US North Virginia), now a user from India is trying to access that reel then the request goes to multiple routers (hops) and finally reaches the Instagram server and again from there the request goes to multiple routers (hops) reaches the Central Storage and now back vice-versa. Latency is directly proportional to number of routers(hops). People in the US can get the reels without buffering.

After CDN - Will create local copies and saves in edge locations on top of central locations, solves the problem of latency created better UX

CloudFront - It's the AWS offering of CDN 

## 1. Introduction to Content Delivery Networks (CDN)

Imagine you have a website with lots of cool content, like images, videos, and documents. When a user visits your site from a different location far away from your server, the content might take a long time to load. That's where CDN comes to the rescue!

A CDN is like a network of servers spread across various locations worldwide. These servers store a copy of your website's content. When a user requests your website, the content is delivered from the server closest to the user, making it super fast! It's like having a local store for your website content everywhere in the world.



