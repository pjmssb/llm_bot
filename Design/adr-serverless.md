---
# These are optional elements. Feel free to remove any of them.
status: accepted
date: 2023-10-28
deciders: Pablo Mogollón
consulted: -
informed: -
---
# channels-hub - Serverless architecture

## Context and Problem Statement

It is needed to respond to dynamic loads of users asking for assistance over direct message channels. The load and behaciour is not known in advance because this system is expected to server to several small and mid-sized organizations, and the dynamics of the users demand depends on the diverse nature of each organization activity. In addition, organizations may acquire or leave this service. 

All of this makes hard to calculate the right capacity to serve users while maintaining a minimum SLA and keeping costs controlled.

<!-- This is an optional element. Feel free to remove. -->
## Decision Drivers

* To prevent any unaswered request message
* To guarantee a time response comparable to human response (t < 5s>)
* To minimize over-capacity or sub-capacity of the system
* To minimize the need to configure platform to respond to users behaviour (picks and valleys of demand) or addition/retire of organizations

## Considered Options

* Virtual server with enough capacity to cover any change on demand.
* Virtual Servers medium capacity + Auto Scaling Groups.
* Serverless functions able to manage the full answering process. 
* Serverless functions to deal with dm messages + virtual server for the LLM

## Decision Outcome

Chosen option: "Serverless functions to deal with dm messages + virtual server for the LLM", because
serverless functions are designed to accept very dynamic bandwidths and costs is directly related to demand. To keep controled the costs, lambda machine sizes will be kept at a minimum. Therefore, LLM needs to move to a medium-size server and probably later to a scaling group of servers.

<!-- This is an optional element. Feel free to remove. -->
### Consequences

* Good - DM messages and LLM reasoning with different behaviours are de-coupled. 
* Good - Variable demand is supported while costs are controled.
* Bad - Architecture gets a bit more complicated than the initial EC2 server planned 
* Bad - To have LLM in one server limits the response capacity of the system. It is needed to keep an eye on time response and sqs dead messages metrics to check that everything is going well or rethink the configuration or the expansion of the platform. 


<!-- This is an optional element. Feel free to remove. -->
### Confirmation

{Describe how the implementation of/compliance with the ADR is confirmed. E.g., by a review or an ArchUnit test.
 Although we classify this element as optional, it is included in most ADRs.}

<!-- This is an optional element. Feel free to remove. -->
## Pros and Cons of the Options

### {title of option 1}

<!-- This is an optional element. Feel free to remove. -->
{example | description | pointer to more information | …}

* Good, because {argument a}
* Good, because {argument b}
<!-- use "neutral" if the given argument weights neither for good nor bad -->
* Neutral, because {argument c}
* Bad, because {argument d}
* … <!-- numbers of pros and cons can vary -->

### {title of other option}

{example | description | pointer to more information | …}

* Good, because {argument a}
* Good, because {argument b}
* Neutral, because {argument c}
* Bad, because {argument d}
* …

<!-- This is an optional element. Feel free to remove. -->
## More Information

{You might want to provide additional evidence/confidence for the decision outcome here and/or
 document the team agreement on the decision and/or
 define when/how this decision the decision should be realized and if/when it should be re-visited.
Links to other decisions and resources might appear here as well.}
