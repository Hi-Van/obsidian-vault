![[Pasted image 20250201134459.png]]


# What is CAP Theorem
---
CAP theorem describes the fundamental qualities of a software system. The acronym of CAP represents the following qualities:

* **Consistency:** A guarantee of the system to return the most recent write for a given record.
* **Availability:** The ability to return a response from the system within a reasonable time frame
* **Partition Tolerance:** The ability to have partial failure, where certain servers or services can become inoperable without forcing the entire system to become inoperable.

Software systems can have 2 of the 3 qualities, but cannot have all three. Based on the requirements of the system, it is up to the architect to design the system towards 2 qualities of their choosing. Since networks are always unreliable, **Partition Tolerance** is always required. Therefore, we must choose between **Consistency** and **Availability**.
# Further Reading
---
* [Cap Theorem: Revisited](https://robertgreiner.com/cap-theorem-revisited/)
* [CAP Theorem](https://www.ibm.com/topics/cap-theorem#:~:text=IBM-,What%20is%20the%20CAP%20theorem%3F,'P'%20in%20CAP)
* [Cap Theorem - System Design Primer](https://github.com/donnemartin/system-design-primer?tab=readme-ov-file#cap-theorem)