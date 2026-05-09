# CAP Theorem
- Consistency, Availability, Partition Tolerance
- Brewer’s Theorem after computer scientist Eric Brewer
- A distributed system can deliver only two of three desired characteristics
- In the presence of a network partition, one has to choose between consistency and availability

### Consistency

- All clients see the same data at the same time
- Every read receives the most recent write or an error

### Availability

- Any client making a request for data gets a response
- Every request receives a (non-error) response

### Partition

- A communications break within a distributed system
- The system continues to operate despite messages being dropped (or delayed)

---

- MongoDB follows Consistency, Partition Tolerance (CP) characteristics
- A CP database delivers consistency and partition tolerance at the expense of availability
- When a partition occurs between any two nodes, the system has to shut down the non-consistent node, until the partition is resolved

<p align="center">
  <img src="/Images/CAP Theorem.png">
</p>