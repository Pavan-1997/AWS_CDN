# AWS CDN

Before CDN - Say a user uploads a reel to Instagram which stores that in Central Storage (say US North Virginia), now a user from India is trying to access that reel then the request goes to multiple routers (hops) and finally reaches the Instagram server and again from there the request goes to multiple routers (hops) reaches the Central Storage and now back vice-versa. Latency is directly proportional to number of routers(hops). People in the US can get the reels without buffering.

After CDN - Will create local copies and saves in edge locations on top of central locations, solves the problem of latency created better UX

CloudFront - It's the AWS offering of CDN 


## 1. Introduction to Content Delivery Networks (CDN)

Imagine you have a website with lots of cool content, like images, videos, and documents. When a user visits your site from a different location far away from your server, the content might take a long time to load. That's where CDN comes to the rescue!

A CDN is like a network of servers spread across various locations worldwide. These servers store a copy of your website's content. When a user requests your website, the content is delivered from the server closest to the user, making it super fast! It's like having a local store for your website content everywhere in the world.


## 2. How Does CloudFront Work?

Let's understand how CloudFront works with a simple example:

Imagine you have a website with images stored on an Amazon S3 bucket (a cloud storage service). When a user requests an image, the request goes to CloudFront first.

Here's how the process flows:
- **Step 1**: CloudFront checks if it already has the requested image in its cache (storage). If it does, great! It sends the image directly to the user. If not, it proceeds to Step 2.
- **Step 2**: CloudFront fetches the image from the S3 bucket and stores a copy in its cache for future requests. Then, it sends the image to the user.

The next time someone requests the same image, CloudFront will deliver it from its cache, making it super fast and efficient!


## 3. Benefits of CloudFront

- **Fast Content Delivery**: CloudFront ensures your content reaches users with minimal delay, making your website lightning fast.
- **Global Reach**: With servers in various locations worldwide, CloudFront brings your content closer to users, regardless of where they are.
- **Security**: CloudFront provides security features like DDoS protection and SSL/TLS encryption to keep your content and users safe.
- **Scalability**: CloudFront can handle traffic spikes effortlessly, ensuring a smooth experience for your users.
- **Cost-Effective**: Pay only for the data transfer and requests made, making it cost-effective for businesses of all sizes.


## 4. Use Cases and Scenarios

### Scenario 1: E-Commerce Website
Let's say you have an e-commerce website that sells products globally. By using CloudFront, your product images and videos load quickly for customers all over the world, improving the shopping experience.

### Scenario 2: Media Streaming
You're running a video streaming platform. With CloudFront, you can stream videos to users efficiently, regardless of their location, without buffering issues.

### Scenario 3: Software Downloads
If you offer software downloads, CloudFront can distribute your files faster, reducing download times and providing a better user experience.


## 5. Tips and Best Practices

- **Caching Strategies**: Configure cache settings wisely to balance freshness and speed for different types of content.
- **Invalidation**: Learn how to invalidate or clear cached content when you make updates to your website.
- **Monitoring and Reporting**: Use AWS tools to monitor your CloudFront distribution's performance and gain insights into user behaviour.

---
# Implementing a Static website on S3 and accessing it through CloudFront

1. Go to S3 from AWS console - > Create bucket -> Give Bucket name (you can give your customer domain name) -> Bucket Versioning - Enable -> Click on Create a bucket


2. Click on the bucket created -> Goto Properties tab -> Click on Edit beside Static website hosting -> Click on Enable -> Give a name to Index document - index.html -> Click on Save changes


3. Go back to the bucket created -> Click on upload and Add files -> Add the files present in Squadfree folder -> Click on Upload 


4. Go to CloudFront from AWS console -> Click on Create distribution -> Origin domain - Select the S3 bucket where you have uploaded the website files -> Origin access - Click on Legacy access identities  ->  Origin access identity - Click on Create new OAI - Click on Create -> Select Yes, update the bucket policy -> Default root object - index.html -> Web Application Firewall (WAF) - Do not enable security protections 

![CF](https://github.com/Pavan-1997/AWS_CDN/assets/32020205/328ef914-7539-459c-8cf9-d847755a7eb4)

Below we are trying to access the static website from the Bucket which shows as access denied since the Public access is blocked 
