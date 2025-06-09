
# 3 Main types of RTOS
1. Hard Real-Time systems
   These systems **must** meet every deadline **strictly and deterministically**. Missing a deadline can lead to **system failure or catastrophic consequences**.
**Examples**:
- Pacemakers
- Automotive airbag systems
- Industrial safety control systems
- Avionics (flight control systems)

**Characteristics**:
- Predictable worst-case execution time (WCET)
- Often formally verified and tested for real-time guarantees

2. Firm Real-Time systems
These systems **should** meet deadlines, and **missing a few deadlines is tolerable**, but those results are **discarded** (i.e., no use if late).
**Examples**:
- Video conferencing
- Sensor data acquisition (where stale data is not useful)
- Voice over IP (VoIP)

**Characteristics**:
- Deadlines are important but not critical
- Occasional deadline misses degrade quality, not cause failure
- Uses hybrid techniques (sometimes RTOS with best-effort handling)

3. Soft Real-Time systems
Deadlines are **preferred**, but **not strictly enforced**. Performance degrades gracefully as deadlines are missed.
**Examples**:
- Multimedia systems (video playback, gaming)
- Online transaction systems
- Virtual reality environments

**Characteristics**:
- Latency is important but not life-critical
- Focuses on **response time optimization**, not strict deadlines
- Can run on general-purpose OS with RT extensions

## Concurrency

Scheduling of services:
- Math models : **Rate Monotonic Analysis** (RMA) of fixed priority, adaptive analysis of dynamic priority.
- Feasibility: determine by manual analysis or mathematical feasibility tests (algorithms) if concurrency services meet deadlines (constraint)
- Specification of RT constraints - Si, Ti, Ci, Di
	- Si, is service i
	- Ti, is time of the service i
	- Ci, is the capacity or computation requirements of service i
	- Di, is the dead line constraint of service i.