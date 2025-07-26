**MetaTags:** #_Done
**Tags:** #Chuleta #ToLink 
- - -

| Operación                                  | Latencia      |
| ------------------------------------------ | ------------- |
| **🧠 Memoria y CPU**                       |               |
| L1 cache reference                         | 0.5 ns        |
| L2 cache reference                         | 7 ns          |
| L3 cache reference                         | 25 ns         |
| Main memory reference                      | 100 ns        |
| Branch misprediction penalty               | 5 ns          |
| Mutex lock/unlock                          | 25 ns         |
| Mutex contention (heavy)                   | 100 ns – 1 µs |
|                                            |               |
| **🧵 Hilos y procesos**                    |               |
| Wakeup of waiting thread                   | 1–10 µs       |
| Context switch (user ↔ kernel)             | 1–5 µs        |
| Context switch (process ↔ process)         | 5–20 µs       |
| Syscall (e.g., read() no bloqueante)       | 0.3–1 µs      |
| Pipe latency                               | 4–15 µs       |
| Unix domain socket round trip              | 5–50 µs       |
| Message passing (in-proc)                  | 1–5 µs        |
|                                            |               |
| **📦 Almacenamiento**                      |               |
| Compress 1K bytes with Zippy               | 10 µs         |
| Read 4 KB randomly from SSD                | 150 µs        |
| Read 1 MB sequentially from memory         | 250 µs        |
| Read 1 MB sequentially from NVMe           | 50–200 µs     |
| Read 1 MB sequentially from SSD            | 1 ms          |
| SATA SSD read (random)                     | 100–300 µs    |
| HDD transfer 4 KB (secuencial)             | 0.5–1 ms      |
| HDD seek                                   | 10 ms         |
| Read 1 MB sequentially from HDD            | 30 ms         |
|                                            |               |
| **🌐 Red y red externa**                   |               |
| Send 1 KB over 1 Gbps network              | 10 µs         |
| Send 1 KB over 10 Gbps network             | 1 µs          |
| Round trip within same datacenter          | 500 µs        |
| Intra-region AWS latency (same AZ)         | <500 µs       |
| Read 1 MB sequentially from 1 Gbps network | 10 ms         |
| Send packet CA → Netherlands → CA          | 150 ms        |
| Inter-region latency (e.g., US ↔ EU)       | 100–200 ms    |
| DNS resolution                             | 10–50 ms      |
| TLS handshake (cold start)                 | 100–300 ms    |


- - - 
#### ***Sources:***
- https://colin-scott.github.io/personal_website/research/interactive_latency.html