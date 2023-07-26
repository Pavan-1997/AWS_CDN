# AWS CDN

Before CDN - Say a user uploads a reel to Instagram which stores that in Central Storage (say US North Virginia), now a user from India is trying to access that reel then the request goes to multiple routers (hops) and finally reaches Instagram server and again from there the request goes to multiple routers (hops) reaches the Central Storage and now back vice-versa. Latency is directly proportional to number of routers(hops). People in the US can get the reels without buffering.

After CDN - Will create local copies and saves in edge locations on top of central locations, solves the problem of latency created better UX

CloudFront - It's the AWS offering of CDN service
