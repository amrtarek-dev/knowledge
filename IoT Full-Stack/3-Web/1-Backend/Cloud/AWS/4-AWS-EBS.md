# EBS
An EBS (Elastic Block Store) is a storage can be attached to the EC2 to persist data even after their termination.

## EBS Volume
Elastic Block Store Volume is a **network drive**  (Not a physical drive) you can attach to EC2 instance while they run
(Think about it like a USB stick):
- To persist data, even after EC2 termination.
- Can connect to only one EC2 instance at a time.
- It is locked to a specific availability zone