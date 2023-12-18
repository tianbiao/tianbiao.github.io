---
layout: post
title: Saving your GCP cost over 50%
categories: [FinOps]
description: share some of my experience on how to save your cost on GCP
keywords: cost saving, cloud, GCP
---

Google Cloud Platform (GCP) is a great cloud platform, but it is also very easy to spend a lot of money on it. In this article, I will share some of my experience on how to save your cost on GCP.

## Background
Starting from January 2020, I have been working on ramping up a new team that focusing on the internal regional requirements of our company. As the sensible default cloud provider for our department is GCP, the team started to build our services on GCP and also migrate some of the legacy services from other cloud to GCP. As of today, our team is developing and maintaining 6 major products. There are 18 gcp projects for all products and service, including test/staging and production environments. The total cost of these projects is around 4K USD per month.
Driven by below reasons, the team started to look into the cost saving opportunities on GCP from middle of 2023.
* The cost is increasing month by month and the number is even over 5K in Nov 2022. it is not sustainable for the team if we are not take infrastructure cost into consideration.
* The gcp is releasing new features and services all the time, more cost optimization service like GKE autopilot was available after the services was already live.
* The team's capability on gcp is growing, and we are able to analysis and optimize the gcp cost in efficient way.
* Reduce the cost is one of the team's OKR. Especially the business requirements is not growing as fast as we expected, the team has more bandwidth to take care of the cost saving.
As of today, the team has saved over 50% of the cost on GCP. 
![GCP cost comparison of 2023 and 2022](/images/blog/gcp-cost-comparison-2022-2023.png)

## How to save the cost
Here are the steps of how we save the cost on GCP.
![Gcp cost saving steps](/images/blog/gcp-cost-saving-steps.png)
### Analysis

#### Visualizing the cost structure and cost trend
The first step is doing analysis on the cost. The analysis is not only for the current cost, but also for the cost trend. The analysis will help us to understand the cost structure and the cost trend. and finally help us to identify the cost saving opportunities. 
Trying to answer below questions during the analysis:
1. What's the total infrastructure cost of the team?
2. What's the cost trend during the these years?
3. What's the cost of each product?
4. What's the cost of each gcp project and gcp service?
5. What's the cost of none-prod environments?
6. What's the pricing model of major gcp services used by the team?
7. What's the gcp discount strategy at organization level and project level?
8. What's the utilization of each gcp service?

[GCP Billing Reports](https://cloud.google.com/billing/docs/how-to/reports) page shows your Google Cloud usage costs at a glance and discover and analyze trends. It is a good starting point to get the cost structure and cost trend.

#### Visualizing the infrastructure architecture
The second step is visualizing the application architecture. The visualization will help us to understand the infrastructure architecture of each product and services. 
Trying to prepare below documents during the analysis:
1. Infrastructure architecture diagrams
2. Data flow diagrams
3. System integration diagrams
4. Architecture decision records if the team has any

Having more context of the as-is architecture will help us to identify the cost saving opportunities and prevent us from making any mistakes during the cost saving process.

#### Identify the cost saving opportunities
The third step is identifying the cost saving opportunities. We can use "How might we" questions to finding the opportunities. For example:
1. How might we decommission the products or services?
2. How might we migrate the existing architecture to serverless?
3. How might we reduce the frequency of scheduled workloads?
4. How might we resize the configuration(like CPU and memory) of managed gcp services?
5. How might we use alternative solutions for the existing modules with lower cost?

We'd better to have all members of the team to join the brainstorming session. The more ideas we have, the more opportunities we can find. You may curious about do we need business analysis and product owners to join the brainstorming session? The answer is yes. The business analysis and product owners can help us to understand the product vision, goal and usage. Which helps us to understand the business impact of each cost saving opportunity.

### Planing
After we have identified the cost saving opportunities, we need to plan the cost saving actions. We can use below metrics to evaluate the saving and effort of each action. Take the actions with the highest saving and lowest effort first. 
![Managing GCP Cost saving opportunities](/images/blog/gcp-cost-opportunities.png)

Here are some of the actions we have taken:
1. Sunset one of our products which is at Decline stage of the product life cycle.
2. Shutdown the non-prod environments during non-working hours and automatically start them up before working hours.
3. Migrate some services from app engine and gke to cloud run(Serverless). 
4. Redesign the scheduled job frequency from all hourly to hourly or daily or weekly based on the business requirements.
5. Resize the configuration of managed gcp services. like Postgresql database on Google cloud sql.
6. Add maintenance mode to products that will not have business requirements in long time. During the maintenance mode, we will remove all non-prod gcp resources.

### Iteration
Adding the cost saving opportunities to your team's backlog and breaking down them to story cards. The story cards will include the business impact and exactly acceptance criteria of each action. Try to create a spike card if there is any uncertainty of the actions.
During the iteration of agile development, we need to take below into consideration:
1. Git branching strategy. We need to make sure the cost saving actions will not impact the development of new features.
2. CI/CD pipeline. We need to make sure the cost saving actions will not impact the CI/CD pipeline.
3. Testing. We need to make sure the cost saving actions will not impact the testing of new features.
4. Zero downtime. We need to make sure the deployment of cost saving actions will not impact the availability of the products and services.
5. Rollback plan. We need to make sure the cost saving actions can be rolled back if there is any issue.
6. Security. We need to collaborate with the InfoSec team to make sure the cost saving actions will not impact the security of the products and services.

After the story is done, we can do the cost analysis again to see if the saving is as expected. If the saving is not as expected, we can do the root cause analysis and try to find out the reason. If the saving is as expected, we move to the next one.

## Summary
In this article, I have shared some of my experience on how to save your cost on GCP. We can follow the steps of analysis, planing and iteration to save the gcp costs. The analysis will help us to understand the cost structure and cost trend, identify the cost saving opportunities. The planing will help us to plan the actions. The iteration will help us to implement the actions and evaluate the saving and effort of each action.
