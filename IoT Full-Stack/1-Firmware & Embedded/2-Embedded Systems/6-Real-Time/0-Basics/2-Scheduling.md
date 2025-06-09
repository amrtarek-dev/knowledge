## Rate Monotonic Scheduling (RMS)
is a foundational real-time scheduling algorithm used in embedded and real-time systems. It’s a _fixed-priority_ scheduling method that assigns priorities to tasks based on their request rates (periods).

- Tasks with **shorter periods** (i.e. higher frequency) are assigned **higher priority
- Tasks with **longer periods** get **lower priority**.
Period ↓ = Priority ↑

For RMS to work as designed, these conditions must be met:
- All tasks are **periodic** (repeated at fixed intervals).
- Tasks are **independent** (no shared resources or synchronization).
- Deadlines are equal to periods (`Deadline = Period`).
- No task self-suspends.
- Context switch time is negligible or accounted for.
  

Each task `Ti` is described by:
- `Ci` = Worst-case execution time
- `Ti` = Period
- `Di` = Deadline (typically `Di = Ti` in RMS)

Utilization test
If there are `n` periodic tasks, the total CPU utilization must satisfy:
- `n = 1`: U ≤ 100%
- `n = 2`: U ≤ ~83%
- `n → ∞`: U ≤ ~69.3%


## Earliest Deadline First (EDF)

Dynamic Priority Scheduling, **Used in**: **Hard**, **Firm**, and **Soft** Real-Time Systems

- **How it works**:
    - Dynamically assigns the **highest priority** to the task with the **earliest absolute deadline**.
    - Priorities change at runtime based on task deadlines.

- **Strengths**:
    - **Optimal**: Can use up to **100% of CPU** (no idle time if tasks are schedulable)
    - More flexible than RMS
        
- **Limitations**:
    - Slightly more complex to implement
    - Harder to analyze worst-case context switching or overload scenarios