# 📐 Module 30: System Design Estimation & Latency Numbers

Essential back-of-the-envelope estimation formulas, data sizing powers of 2, latency numbers, and QPS calculations for System Design interviews.

---

## ⚡ 1. Power of 2 Data Sizing Memory Table

| Power of 2 | Exact Bytes | Approximate Size |
| :-: | :-: | :-: |
| $2^{10}$ | $1,024$ Bytes | **$1$ KB** |
| $2^{20}$ | $1,048,576$ Bytes | **$1$ MB** |
| $2^{30}$ | $1,073,741,824$ Bytes | **$1$ GB** |
| $2^{40}$ | $1,099,511,627,776$ Bytes | **$1$ TB** |
| $2^{50}$ | $1,125,899,906,842,624$ Bytes | **$1$ PB** |

---

## ⏱️ 2. Latency Numbers Every Programmer Should Know

| Operation | Typical Latency |
| :--- | :---: |
| L1 Cache reference | $0.5$ ns |
| L2 Cache reference | $7$ ns |
| Main Memory (RAM) reference | $100$ ns |
| Read $1$ MB sequentially from Memory (RAM) | $250$ $\mu$s |
| Read $1$ MB sequentially from NVMe SSD | $1$ ms |
| Read $1$ MB sequentially from HDD | $20$ ms |
| Send packet California to Netherlands & back (WAN) | $150$ ms |

---

## 🧮 3. Back-of-the-Envelope QPS Calculation Formula

$$\text{Queries Per Second (QPS)} = \frac{\text{Daily Active Users (DAU)} \times \text{Average Requests per User}}{86,400 \text{ seconds}}$$

- **Example Calculation:**
  - $10 \text{ Million DAU}$ with $10 \text{ requests/day}$:
  - $\text{Daily Requests} = 100 \text{ Million requests/day}$
  - $\text{Average QPS} = \frac{100,000,000}{86,400} \approx 1,157 \text{ QPS}$
  - $\text{Peak QPS} = \text{Average QPS} \times 2 \approx 2,314 \text{ QPS}$
