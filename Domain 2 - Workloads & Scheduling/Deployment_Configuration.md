## Deployment Configuration

While performing a rolling update, there are two important configurations to know.

a. maxUnavailable=0 and maxSurge=20%  << Full Capacity is maintained.

b. maxUnavailable=10% and maxSurge=0   << Update with no extra capacity. In-place updates.

If you want fast rollout, make use of maxSurge.

If there might be a resource quota in place and partial unavailability is acceptable, maxUnavailable can be used.
