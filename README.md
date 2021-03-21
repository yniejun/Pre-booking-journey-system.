# Pre-booking-journey-system.
## Requirement：
We need to implement a global-oriented journey management system that allows drivers to book/cancel journeys. According to the requirement, all road-vehicle drivers are required to prebook every journey that they wish to make,  no driver is allowed to start a journey without having received a notification that the requested journey is acceptable.

These require us to provide a high-performance service, it has to meet at least the following requirements (The focus of our system implementation exercise is not the business logic of journey management)  :
>* This service needs to be scalable.(All journeys required a prebook, the  amount of users might be very large.)
>* The service needs to be highly available. (No driver is allowed to start a journey without having received a notification)
>* The service needs to be reliable.(Before start journey, the drivers receive a notification that the requested journey is acceptable)

## Technology selection
### For scalability:
>* Distributed databse (data partitioning)
1. Distributed webserver
1. Use middle-ware (Mq/redis)
>* For availibility:
1. Disaster tolerance<br/>
Fault monitoring<br/>
Service degradation, current limit, self-protection capability<br/>
1. Fast recovery
>* For reliability:
1. Avoid single point of failure<br/>
Load balancing<br/>
Hot backup<br/>
>* For consistence:
1. Global ID, e.g. Snowflake
1. Transaction
1. Checksum/Salt
1. Synchronize Cache 
