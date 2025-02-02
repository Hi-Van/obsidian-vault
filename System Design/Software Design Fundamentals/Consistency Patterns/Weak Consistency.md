![[Pasted image 20250201182048.png]]

Weak consistency is a consistency model used in distributed systems where data updates are not immediately reflected across all nodes. This means different clients might observe different versions of the data, even after a write operation. While prioritizing high availability, ensuring that clients _always_ receive a response, weak consistency makes no guarantee that all clients will see the same data. The system tolerates temporary inconsistencies to maintain responsiveness and availability.

- **Online Games:** MMOs prioritize responsiveness. Small delays in updates are acceptable to prevent lag and maintain playability. Weak consistency allows game servers to prioritize speed, even with minor inconsistencies, resulting in a smoother overall experience.

- **Zoom:** Real-time communication tools like Zoom prioritize connection stability. Occasional glitches are less disruptive than dropped connections. Zoom tolerates minor inconsistencies in data delivery to maintain a continuous flow of audio and video.

- **Figma/Notion:** Collaborative editors benefit from low latency. Users want to see others' changes quickly. Temporary inconsistencies between user views are acceptable, as these applications are designed to handle conflicts gracefully, prioritizing a responsive editing experience.

- **Memcached:** Caching systems like Memcached prioritize speed. Serving slightly outdated data is a trade-off for significantly faster access times. Memcached tolerates these temporary inconsistencies to improve overall performance.

# Further Readings
---
* [Weak Consistency in System Design](https://www.geeksforgeeks.org/weak-consistency-in-system-design/)