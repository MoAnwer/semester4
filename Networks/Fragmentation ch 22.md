1. **Definition:** Fragmentation is the process of dividing an IP datagram into smaller pieces, called fragments, when it is too large to travel across a network.
2. **Maximum Transmission Unit (MTU):** Each network technology has a fixed limit on the maximum amount of data a single frame can carry, known as the MTU.
3. **Hardware Enforcement:** Network hardware is not designed to accept or transfer frames carrying more data than the MTU allows; there are no exceptions to this limit.
4. **IPv4 vs. IPv6 Approach:** In IPv4, intermediate routers perform fragmentation as needed, whereas in IPv6, only the sending host is responsible for fragmentation.
5. **Fragment Format:** Surprisingly, each IPv4 fragment uses the standard datagram format, appearing like any other independent datagram to the network.
6. **Identification Field:** A unique 16-bit identification number is assigned to the original datagram and copied into every fragment to allow the receiver to group fragments of the same datagram together.
7. **Fragment Offset:** This 13-bit header field specifies exactly where in the original datagram's payload the data in the current fragment belongs.
8. **The FLAGS Field:** In IPv4, bits in this field indicate whether a datagram is a fragment and if it is the final (rightmost) piece of the original datagram.
9. **IPv6 Extension Header:** Unlike IPv4, the IPv6 base header does not contain fragmentation fields; instead, this information is placed in a separate "fragment extension header".
10. **Replication of Headers (IPv6):** In IPv6, "unfragmentable" parts—the base header plus headers used by intermediate routers—are replicated in every fragment to ensure identical routing.
11. **Ultimate Destination Reassembly:** The process of recreating the original datagram, called reassembly, is performed exclusively by the ultimate destination host.
12. **Routers and Reassembly:** Intermediate routers are explicitly prohibited from reassembling fragments to reduce their state information and allow routes to change dynamically during transmission.
13. **Dynamic Routing Advantage:** Because reassembly is postponed until the final destination, the Internet is free to pass different fragments of the same datagram along different routes.
14. **Reassembly Timer:** To prevent fragments from occupying memory indefinitely, a receiver starts a reassembly timer when the first fragment of a datagram arrives.
15. **All-or-Nothing Rule:** Reassembly is an all-or-nothing process; if the timer expires before all fragments arrive, the receiver discards all fragments that have arrived for that datagram.
16. **Lossy Network Impact:** On lossy networks (like wireless LANs), the probability of losing an entire datagram is significantly higher if it is fragmented.
17. **Path MTU:** The smallest MTU along a path from a source to a destination is called the "path MTU".
18. **Path MTU Discovery:** In IPv6, hosts use an iterative process to discover the path MTU and adjust their datagram size to avoid fragmentation.
19. **Fragmenting a Fragment (IPv4):** In IPv4, if a fragment reaches a network with an even smaller MTU, a router can further fragment that fragment.
20. **General Recommendation:** Because fragmentation reduces efficiency and increases the risk of datagram loss, it should be avoided whenever possible.