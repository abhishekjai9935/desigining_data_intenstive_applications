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
   1. **Reliability** : The system should continue to work correclty even int the face of adversity.
        correctly => performing the correct function at the disired level of performance
        adversity => hardware or software faults, and even human error
   2. **Scalability** : As the sysyem grows (in data volume, traffic volume, or complexity), there should be resonable ways of dealing with that growth
   3. **Maintainability** : Over time, many diffferen people will work on the system and they should be able to work on it productively.
  
- In this chapter we will deep dive into these concepts first and then in subsequent chapters we will look at various techniques, architectures adn algorithms that are sued in order to achive thsoe goals.


## Reliability


