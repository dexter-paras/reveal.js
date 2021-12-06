## Question 1
# What do you understand by Distributed Tracing in Microservice context?

# What is the interviewer looking for?
- Whether you've worked in microservice architecture where there is 1 traceId to all microservices
- Bonus: if you can lay out some advantages and give some examples why distributed tracingId is required

--

# Answer
- Distributed tracing is a way which helps to visualize and analyse a request which spans in multiple microservices.
- This include
  - **Trace Id** : A uniqueId to trace the path of the request, if request spans across multiple services
    - Scope: Global
  - **Span Id** : A uniqueId to track request related to single service only.
    - Scope: local to service
- More often, there is a GUI where you enter traceId and able to visualize request end to end along with timeline.  

---
## Question 2
# What do you understand by Distributed Logging in Microservice context?

# What is the interviewer looking for?
- Whether you've worked in microservice architecture where there is log aggregation required at one place.
- Bonus: if you can lay out some advantages and give some examples why distributed logging is required


# Answer
- Distributed logging is a way of storing & aggregating of multiple of logs for visualization & analysis in a 
  centralized place.
- More often, there is a GUI where you enter traceId or any log info, and you would be able to see all logs 
  corresponding to all microservices.

---

## Question 3
# What are the advantages of Distributed Tracing and logging?

--

# What is the interviewer looking for?
- Whether you have hands-on experience working in microservice architecture where Distributed tracing and logging 
  was needed

--

# Answer
- Distributed Tracing & Logging helps developers, Ops team to trace a request end to end in case of 
    - Any error in production. TraceId helps to check aggregated logs in all Microservices at once
    - increase latency. TraceId & logs helps to check latency per service in all microservices at once. This helps 
      to see what part of microservice took more time and same can be fine-tuned later.
  
---

## Question 3
# Any disadvantages of using Distributed Tracing and Logging?

--

# What is the interviewer looking for?
- When to prefer using Distributed tracing and logging. When not to do over engineering.

--

# Answer
- Additional Infra setup and Cost.
- Additional complexity of creating own traceId logic other than 3P libraries
- Additional complexity of aggregating logs as per own logic other than 3P libraries.

---

## Question 4
# How can you implement Distributed logging and tracing in microservice architecture?

--

# What is the interviewer looking for?
- If you've worked in implementation of achieving logging and tracing in microservice architecture.

--

# Answer
- Spring Cloud Sleuth + Zipkin
- OpenTracing + Jaeger
- ELK(ElasticSearch, Logstash and Kibana)
- sofa-rpc framework by Ant Financial

---

## Question 5
# What all logs should be part of logging in microservice architecture?

--

# Answer
- Application logs - Logs related to application business logic
- Audit trail logs
- Event logs - Logs related to events produced by services.  
- rpc-client logs - RPC Logs related to hits host is making to other services.
- rpc-server logs - RPC Logs related to hits coming on host from other services.
