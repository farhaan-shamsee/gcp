# SRE

If you think about SRE as a journey, the first step is to develop service level objectives or SLOs with consequences. The performance of your service relative to SLOs should guide your business decisions.

## Blameless Postmortem

- After an outage, it's important to understand why an incident occurred, and then take steps to make sure it doesn't happen again in the same way. SREs do this by documenting and conducting a blameless postmortem.Some people also call this a retrospective.
- A postmortem's ultimate deliverable is a written record of the incident that consists of specific parts.
- ![image](https://github.com/user-attachments/assets/c1795b41-fe8e-494f-b02d-9c5a1ce81736)
- Particularly, a blameless postmortem only focuses on the root causes of an incident without accusing a particular person or team, or their actions or behavior.
- Tactics like the five whys are used to probe deep into what caused an incident in all of the contributing factors, not just what first appears to be the culprit.
- Hindsight bias is the tendency of people to overestimate their ability to have predicted an outcome, even though it could not have possibly been predicted.

## SLOs and Error budgets

- ![image](https://github.com/user-attachments/assets/56c3e2f5-277b-4e2f-af67-195a952322d9)
- As long as the measured up time is above your target, meaning as long as you have error budget remaining, you can push new feature releases. Alternatively, you can spend this remaining budget on something else, such as expected system changes, inevitable failures in hardware and networks, planned downtime, or risky experiments.
- Essentially, an error budget is an agreement that helps prioritize engineering work.
- Developer teams can manage the error budget on their own, knowing that unrealistic reliability targets will slow down innovation.
- SLOs are precise numerical targets for system reliability.

## SLI

- An SLI tells you at any moment in time how well your service is doing.
- t's a quantifiable measure of service reliability.SLIs are expressed as the number of good events divided by the number of valid events, times 100%.
- SLIs should map to user expectations, such as response time latency and quality, data processing, correctness and freshness, or storage latency and throughput.
- ![image](https://github.com/user-attachments/assets/b74848ad-d62f-4bcd-a84a-df730268ed69)
- an SLO is your target for SLIs aggregated over time.
- Assuming you've expressed your SLIs as a percentage between zero and 100, your SLO should generally be just short of 100%, like 99.9%, or 'three nines.'
- A typical customer should be happy if you barely meet your SLO. Anything below your SLO will result in an unhappy customer who's expectations for reliable service are not being met.
- an SLA, which you are likely familiar with already, is the promise you make about your service's health to your customers.
- It defines what your business is willing to do if you fail to meet your SLOs. For example, refunding money.

