---
# These are optional elements. Feel free to remove any of them.
status: accepted
date: 2023-10-28
deciders: contact@pablomogollon.tech
consulted: -
informed: -
---
# channels-hub - Serverless architecture

## Context and Problem Statement

It is needed to respond to dynamic loads of users asking for assistance over direct message channels. The load and behavior is not known in advance because this system is expected to serve to several small and mid-sized organizations, and the dynamics of the users' demand depends on the diverse nature of each organization's activity. In addition, organizations may acquire or leave this service. 

All of this makes it hard to calculate the right capacity to serve users while maintaining a minimum SLA and keeping costs controlled.

<!-- This is an optional element. Feel free to remove it. -->
## Decision Drivers

* To prevent any unanswered request message
* To guarantee a time response comparable to human response (t < 5s>)
* To minimize over-capacity or sub-capacity of the system
* To minimize the need to configure the platform to respond to users' behavior (picks and valleys of demand) or addition/retirement of organizations

## Considered Options

* Virtual server with enough capacity to cover any change on demand.
* Virtual Servers medium capacity + Auto Scaling Groups.
* Serverless functions able to manage the full answering process. 
* Serverless functions to deal with dm messages + virtual server for the LLM

## Decision Outcome

Chosen option: "Serverless functions to deal with DM messages + virtual server for the LLM", because serverless functions are designed to accept very dynamic bandwidths, and costs are directly related to demand. To control the costs, lambda machine sizes will be kept at a minimum. Therefore, LLM needs to move to a medium-sized server and probably later to a scaling group of servers.


### Consequences

* Good - DM messages and LLM reasoning with different behaviors are de-coupled. 
* Good - Variable demand is supported while costs are controlled, and it is not needed frequent configuration.
* Bad - Architecture gets a bit more complicated than the initial EC2 server planned 
* Bad - To have LLM in one server limits the response capacity of the system. It is necessary to keep an eye on time response and sqs dead messages metrics to check that everything is going well or rethink the configuration or the expansion of the platform. 



