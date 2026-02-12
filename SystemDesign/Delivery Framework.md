Basically the delivery framework is a set of steps and timings that help you to focus on the important stuff while working on a system design, this is important since often is common that you can get distracted on something that is not important and do not deliver a working system in your interview.

- [Requirements](## Requirements)
- [Capacity Estimation](## Capacity Estimation)
- [Core Entities](## Core Entities)

-----

## Requirements
#### 5 Minutes

### Functional Requirements
These are the ones that start with "user should be able to ....", for example if we are designing twitter some examples would be:
- User should be able to post tweets
- User should be able to follow other users
- User should be able to see tweets from it's followers

Tips is that you keep your requirements targeted you will need to pick the top requirements that need to be implemented this is important since this systems could end up having tons of requirements but for the design we might want to focus on a couple, **identify and focus on the top ones**


### Non-Functional Requirements
These are the ones that start with "The system should be able to ..",  they describe qualities of the system

- The system should be highly available, prioritizing availability over consistency
- The system should be able to scale to support 100M+ DAU (Daily Active Users)
- The system should be low latency, rendering feeds in under 200ms

> Important here is that these requirements are quantifiable, i.e "system should have low latency" vs "system should be able to display user feed in under 200ms"

#### Checklist of things to consider (pick top 3-5)
- CAP theorem
	- Consistency
	- Availability
	- Partition tolerance is a given, so assume is always need
- Environment constraints
	- Are we running this on a RPI? on a mobile network etc
- Scalability
	- All system have a need to scale but does this system has a specific pattern we need to account for? i.e super high traffic at nights?
- Latency
	- How fast does the system need to be? , i.e low latency search is expected in your system
- Durability
	- How important is that the data in your system is durable, maybe on a social network is ok to lose a post but not in a bank application
- Security
	- Data protection, PII, credit card info usage etc
- Fault tolerance
	- Redundancy (hardware, software apps, data replicas), failover (automatic switch to redundant option when primary fails) and recovery mechanisms (checkpointing, transaction logging, rollback)
- Compliance
	- Country compliance regulations for your software, i.e California show fees etc

## Capacity Estimation

> Skip and tell your interviewer you will do the estimates while design the app, no need to stop and do some math and then jump to next step.

- What to estimate
	- **identify what makes the problem genuinely hard** - the "crux" - and tackle that part first.
		- For example if you're designing twitter search it may be the search indexes
		- If you're designing a URL shortener how do you generate unique keys and handle collisions etc
- Break it down
	- Use dimensional analysis to get a mental graph on how big things are, for example if you have size of tweet (150 chars) and DAU of 250m you're only missing avg tweets per use to get an idea of how much data a day your system takes in, that will give you an idea on the search index size etc.
- Facts to know
	- Metrics (bytes, kilo, mega, giga, tera, peta)
	- Latencies (1mb read, .25ms read from memory, 1ms read from ssd)
	- Storage (two hour movie 1.5gb, book 2.5 mb)
	- Business (DAU from google searches, social networks, hours streamed on netflix)

### Common mistakes
This should take 2 to 3 min of your interview:
- Do not estimate things that don't matter
- Avoid getting stuck on math
- Getting amounts all wrong 1gb instead of 1tb


## Core Entities
#### 2 minutes

Continue here....
