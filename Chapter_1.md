# Reliable, Scalable, and Maintainable Applications

## Introduction

- Nowadays, applications are data-intensive rather than compute-intensive.

- There are many database systems are available with different features/characteristics as different applications have different requirements.
- It is very tricky to combine different tools to accomplish a single task because maybe a single tool cannot do that.
- In this book we we will be learning about design discussion to achieve : reliablity, scalability, and maintainability of data systems.


## Thinking About Data Systems

- Generally we think that databases, queues and caches are of different categories but they share some similarity such as both sotre data for sometime
- If we are desigining  a data-system or service lot of tricky question arise:
   1. How do you ensure that the data remains correcta and complete, even when things go wrong intrenally?
   2. How do you provide consistently good performance to clients, even when your system are degraded?
   3. How do you scale to handle an increase in load?
   4. What does a good API for the service look like?

- In this book we focus on three concerns:
   1. **Reliability** : The system should continue to work correclty even in the face of adversity.
        correctly => performing the correct function at the disired level of performance
        adversity => hardware or software faults, and even human error
   2. **Scalability** : As the sysyem grows (in data volume, traffic volume, or complexity), there should be resonable ways of dealing with that growth
   3. **Maintainability** : Over time, many different people will work on the system and they should be able to work on it productively.
  
- In this chapter we will deep dive into these concepts first and then in subsequent chapters we will look at various techniques, architectures adn algorithms that are sued in order to achive those goals.


## Reliability

- By word Reliability, in the context of a software, we can have following expectations:
  1. The application performs the function that the user expected.
  2. It can tolerate the user making mistakes or using the software in unexpected ways.
  3. Its performance is good enough for the required use case, under the expected load and data volume.
  4. The system prevents any unauthorised access and abuse.
  
- Overall we can say that Reliability means continuing to work correclty, even things go wrong.
- Things that can go wrong are called *faults*, and the systems that anticipate faults and can cope with them are called *fault-tolerant* or *resilient*.
- But fault-tolerant doesn't mean that it should tolerate all type of faults, rather than it will be tolerating certain types of faults only.
- Fault is not the same as a failure. A fault is usually defined as one component of the system deviating from its spec, whereas a failure is when the sysyem as awhole stops providing the required service to the user. 
- It is impossible to reduce the probability of a fault to zero; therefore it is usually best to design fault-tolerance mechanisms that prevent faults from causing failures.
- In this book we will cover several techniques for nuilding reliable systems from unreliable parts.


### Hardware Faults




