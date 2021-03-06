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


- Hardware failures can be : hard disks crash, RAM becomes faulty, the power grid has a blackout, unplugging wrong network cable
- First thing can be done to add rendundancy to inidividual hardware components in order to reduce the failure rate of the system
- Until recently, redundancy was sufficient but now we are using large number of machines so multi machine redundancy is required so we don't do this
- Now we focus on flexibility and elastivciy rather than on single-machine reliablity


### Software Errors

- Hardware faults are genrally random and independent from each other, except some common cause is there such as temperature in the server rack
- Software faults are systematic faults 
- The software faults lie domrant for a long time until they are trigger by an usual set of circumstances. Only under those circumstances it is revealed that the software is making some kind of assumption about its environment -- and while that assumptions is usually true, it eventually stops being true for some reason.
- There is no quick solution to the problem of systematic faults in software. 
- Lots of small things can help:
 1. carefully thinking about assumptions and interactions in the system
 2. Thorough testing
 3. Process isolation
 4. allowing process to crash and restart
 5. measuring, monitoring and analysing system behoaviour in production


### Human Errors

- Software is designed, built and maintained by humans, so humans errors can also cause harm to the system
- So we can have many approaches to make system reliable inspite of unreliable of humans
  1. Minimise the opportunities for error by well designed abstraction, APIs , admin interfaces etc.
  2. Decouple the places where people make the most mistakes from the places where they can cause failures
  3. Test thoroughly at all levels unit testing, whole system integration tests and manual tests
  4. Allow quick and easy recovery from human errors to minimise the impact in the case of failure; for example make it fast to roll back configuration changes
  5. Set up detailed and cleare monitoring such as performance metrics and error rates
  6. Implement good management practices and training
  
  
  ### How important is reliability?
  
  - Reliablity is important for all types of application because application developer have a responsibility to their users
  - Sometimes we sacrifice reliabilty to reduce development cost or operataional cost -- but we should be very consicous of when we are cutting corners
  
  
 ## Scalability
 



