---
layout: post
title: "Dipping our toes into serverless architecture"
date: 2025-06-05
categories: articles
---
# Dipping our toes into serverless

  
![AWS RC blimp](https://skymabaranat.github.io/thoughts/assets/images/blimp.jpg)

Recently, I had the opportunity to attend the AWS Summit in London. It was, as expected, packed with various events, talks, demos, workshops, vendor stalls (free stuff yay!) and of course free lunch and beers ;).  

Some of the event heavily leaned into shoehorning AI into everything humanely possible, with some shameless plugging of AWS services. Nevertheless, there were some really great offerings providing brilliant insight into building serverless architectures at scale. 

Notably, one talk was able to truly provide some incredibly relevant eye opening views on tackling issues of modernisation, scalability and operational efficiency on the cloud. 

## Motorway's serverless case study

  In a a very informative talk "Zero to Production in 30 Days" Ryan Cormack, a Principal Engineer at Motorway, was there to share some of their journey, propelling from Elastic Beanstalk to ECS Fargate, and eventually to a "serverless-by-default" approach.

  Matt Meckes, an AWS Modernization Specialist, joined as well in explaining some of the important fundamental ideas behind working towards a serverless approach. The idea that there is a "minimum viable modernisation", instead of throwing everything away at once we can instead carve into legacy systems and rebuild them off manageable slices implementing modern patterns like Lambda, EventBridge and StepFunctions. 

  What stood out most from Motorways journey to serverless was their commitment to this iterative approach. Instead of undertaking a massive "lift -and-shift" effort they instead opted for incrementally taking "slices" of their current systems and gradually rerouted traffic to new services. 

A few lessons that hit home:

- Modernisation is a continous process
	- Instead of freezing legacy systems and writing code for a "big bang" approach. Motorway employed the use of Lambda@Edge for example to carry out edge routing allowing customers consistency with all their features while slowly trimming away in their legacy systems.
	 
![Sliced architecture migration](https://skymabaranat.github.io/thoughts/assets/images/sliced_architecture.png)

- Expose complexity carefully
	- AWS allows the use of a variety of tools like Step Functions and EventBridge in order to aide the observability of our distributed systems. When migrating approaches it can be crucial to use these tools to orchestrate business logic i.e. Step functions may help make complex workflows more explicit and visible making them easier to debug and EventBridge helps to decouple services as the event-driven communication allows each slice to integrate easily and cleanly with others. 
 
![Serverless edge architecture](https://skymabaranat.github.io/thoughts/assets/images/serverless.png)

- Speed doesn't necessarily mean chaos
	- Serverless can enable speed when deploying and can cut infrastructure costs greatly. Motorway specifically, reported up to 80% cuts in the cost of infrastructure whilst increasing their speed of deployment 
	- A quote given from Dave Farley, Founder and Director of Continuous Delivery, really summed this up "If you want speed, you must build high-quality systems. If you want high-quality systems, you must build them quickly as a series of small changes"


## Where do we go from here?

As in the case of Motorway, there is great potential for balancing legacy and newer service whilst maintaining overhead and scaling effectively. It highlights when trying to achieve serverless, we need to be weary of not just the tech stack but how we architect an incremental solution in order to ensure a smooth success. 

Even when creating a POC it can be as easy as leveraging EventBridge and Lambda for the workflows, using Lambda@Edge we can gradually shift traffic away from our legacy systems, and we can build new features inside isolated serverless accounts without having to worry about complexities like governance and observability. 

I'm not saying that serverless is the saving grace of all scaling and cost issues there are definitely things to be said about downing tools and letting AWS handle all our difficult problems. However, if Motorway's experience proved anything, it's that we can shift and improve incrementally without sacrificing speed and without breaking what already works.

![rap AI](https://skymabaranat.github.io/thoughts/assets/images/rap_ai.jpg)

