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

## CICD, Canarying

- SREs believe that change is best when it is small and frequent. Although change is risky, it's less disruptive to users when rolled out in smaller waves.
- Continuous integration, usually refers to building, integrating, and testing code within the development environment. The main goal of this practice is to enable engineers to work on code and test more often.
- Continuous delivery just means that you can deploy to production frequently, but may choose not to, usually due to businesses preferring a slower rate of deployment.
- Canaries are smaller and breathe faster than humans, so if they died, the miners knew there was danger. The small thing detects danger as we go into the unknown.
- We have a large service that we want to sustain. We are okay losing a small portion of it. We employ a production change with unknown impact to the small portion to detect danger.
- Canarying is deploying a change in service to a group of users who don't know they are receiving the change, evaluating the impact to that group, then deciding how to proceed. If the change contains bugs, the cost is much less than if it was rolled out to the whole system and can be reversed quickly.
- Design thinking is one approach that combines creativity and structure to solve complex problems.
- Design thinking methodology has five phases.:
  - empathize,
  - define the problem you are attempting to solve.
  - ideate: Now that you've defined the problem, you can start generating ideas for solutions.
  - prototype: ou can get the ideas out of your head and into the real world. It's meant to be experimental, so you can identify the best possible solution before committing.
  - test: You'll want to test your prototype solutions in a real-world setting with your intended users.
- Physical prototyping
- Paper and drawing.
- Clickable
- role play
- video

## TOIL

Toil is work directly tied to a service that is manual, repetitive, automatable, tactical, without enduring value, or that scales linearly as the service grows.

- ![image](https://github.com/user-attachments/assets/4777ddde-2183-4b68-90eb-af5affd1497b)
- By keeping your SREs working on toil less than 50% of the time, you're also distinguishing the SRE role as clearly different from a typical operations role.
- ![image](https://github.com/user-attachments/assets/c352ecf0-ca40-421d-a43c-fa5d31e7e91c)
- 

## psychology of change

- Navigators, these are the people who will make teams and businesses successful, as leaders, spot them and celebrate their behaviors, use them as champions for the change.
- Critics, these are the second type of individuals that you should care about, they have passion and energy, critics care, and they have valid fears, so it's important not to ignore them. Spend time with them, because they will be very powerful advocates if you can persuade them.
- Victims, often this type of individual just needs to get their emotions out, victims tend to take organizational change very personally.
- bystanders have no idea what's going on, and they will just continue as if nothing or no change is happening, you should try to communicate with them, to ascertain their feelings.

## Regulate Workload

- Choosing good SLIs is key to measuring reliability. You are making a connection between your SLIs and your user's experience so you'll want to decide what to measure based on their perspective.
- For example, it doesn't matter to a user whether your database is down or if your load balancers are sending requests to bad backends.  They experience a slowly loading web page, and that makes them unhappy. If you can quantify slowness, you can then tell how unhappy your users are in aggregate, which lets you define your SLO.
- ![image](https://github.com/user-attachments/assets/a360910d-a324-41ac-b11d-3de4c4b26357)
- The biggest risk you have to contend with is that perhaps the SLI doesn't recover after the outage as quickly as you might have hoped for.
- The second aspect to measure is toil.
- As you've learned, toil is work that is directly tied to running a service that is manual, repetitive, automatable, tactical, and without enduring value.
- You can measure toil in three steps.
- First, identify it.
- Who is best positioned to identify toil depends on your organization.
- Ideally, these people are stakeholders and those who perform the actual work.
- Next, select an appropriate unit of measure.
- This unit needs to express the amount of human effort applied to this toil.
- Minutes and hours are a good choice because they are objective and universally understood.
- And third, track the measurements continuously.
- Do this before, during, and after toil reduction efforts.
- Streamline the measurement process using tools or scripts so that collecting these measurements doesn't create additional toil.
- Start simple, count the number of tickets you receive, count the number of alerts, collect alert stats on cause and action.
- These can prove useful in identifying the source of toil.
- You can measure actual human time spent on toil by collecting data, either in the ticketing system directly or by asking your team to estimate the time spent on toil every day or week.
- Monitoring allows you to gain visibility into a system, which is a core requirement for judging service health and diagnosing your service when things go wrong.
- Let's first look at what you should monitor.
- It's best practice to alert on symptoms rather than causes.
- Users don't care whether they can't get to your website because your router is rebooting or because the database is overloaded.
- Similarly, they don't care if CPU utilization is very high if they can still access the system and it feels fast.
- Creating a separate alert for each cause typically results in a lot of spam alerts.
- It's better to have fewer symptom-based alerts combined with good debugging tools, like dashboards that will allow responders to more easily identify specific cause.
- Ideally, Google recommends alerting based on error budget burn.
- You might pay someone when you are consuming your error budget very quickly.
- For example, when you spend ten hours worth of error budget within one hour, you might just create a ticket for a lower burn rate.
- For example, if you spent three days worth of budget within three days, basically only escalate to a human if you risk dropping below the SLO for the month.
- If your SLO is set correctly, you won't be paging people for problems that users don't care about.
- There are exceptions to this rule of course, because there might be a problem that does not result in user-visible symptoms.
- Capacity alerts can be an example of this.
- If you know you will exhaust a particular limit soon, it wants an alert even if there is no user-visible symptom yet.
- ![image](https://github.com/user-attachments/assets/1a125806-3fcd-444e-abd5-24aa02c9ef7d)


## Goal Settings

- Google uses OKRs, objectives and key results, as KPIs.
- OKRs are usually graded on a scale of to where indicates a fully achieved objective.
- Consider these things when grading OKRs.
- The optimal point for an OKR grade is to %.
- Think big when developing your OKRs.
- OKRs are not synonymous with performance evaluation, instead they show individuals' contributions and impact.
- ![image](https://github.com/user-attachments/assets/a9d681ed-b39c-4751-8a16-d50466b3ce68)
- There are several common biases that show up in organizations and influence the way decisions are made.
- Affinity bias, this is a bias towards those who are similar to you.
- This could mean similar in many different ways, such as race, gender, socioeconomic background, or education level.
- People tend to gravitate towards those who are like them.
- Confirmation bias, this bias is the tendency to find information, input, or data that supports your preconceived notions.
- Labeling bias, this bias is making opinions based on how people look, dress, or show up externally.
- Selective attention bias, this bias is when you pay attention to things, ideas, and input from people you tend to gravitate toward.
- All of these biases can create environments that are not very diverse or inclusive.
- They can also impact the creativity, innovation, morale, engagement, and turnover in an organization.


## Organizational Maturity

Organizational maturity is considered low if your organization has not yet adopted SRE principles, practices, and culture.

- ![image](https://github.com/user-attachments/assets/75256980-a50a-4fa6-a038-cac64dca957e)
- Well-documented and user-centric SLOs, where a target level of reliability is ideally correlated with customer happiness.
- Error budgets, which are budgets for failure.
- The error budget is the difference between perfection and your SLO.
- They allow IT teams to move fast as long as the budget is not exhausted, but with defined actions to improve reliability if the production service fails.
- A blameless postmortem culture.
- This culture recognizes that things will go wrong and that human errors are really systems problems.
- A low tolerance for toil.
- Again, toil is work that tends to be manual, repetitive, automatable, tactical, and devoid of enduring value, and that scales linearly as a service grows.
- ![image](https://github.com/user-attachments/assets/8d11c249-8f8c-40fb-ae75-71df6523d6e7)

## SRE TEAM

- ![image](https://github.com/user-attachments/assets/91eaa164-7ff3-4fc8-9f5b-f26b0ca4254f)
-  kitchen sink:
  -  If you've never created an SRE team, this is a good place to start.
  -  ![image](https://github.com/user-attachments/assets/405baef4-f3a1-41d2-8d05-e44a7c2d9dcb)
  -  ![image](https://github.com/user-attachments/assets/182739e3-fe25-4b20-af73-c293f886a34c)
  - There are several benefits to kitchen sink implementation.
  - There are no coverage gaps between SRE teams given that only one team is in place.
  - It's easy to spot patterns and draw similarities between services and projects.
  - SREs tend to act as glue between disparate developer teams, creating solutions at a distinct pieces of software.
  - There are also several disadvantages.
  - There's usually a lack of an SRE team charter, or the charter states that everything in the company can be in scope, running the risk of overloading team.
  - As the company and system complexity grows, the team tends to move from having a deep positive impact on everything, to making more shallow contributions.
  - And issues involving a team may negatively impact your entire business.
- Infrastructure:
  - This type of team focuses on behind the scenes tasks, that help make other team's jobs easier and faster.
  - They work on maintaining shared services and components related to infrastructure, versus an SRE team dedicated to working on services related to products, like customer facing code.
  - ![image](https://github.com/user-attachments/assets/71c3e42e-59d1-4347-a40a-cd52865b7596)
  - It is common for large companies to have both an infrastructure DevOps team and SRE team, where the DevOps team focuses on features, and SRE focuses on reliability.
  - A benefit of the infrastructure implementation is that it allows product developers to use DevOps practices to maintain user facing products, without divergence in practice across the business.
  - ![image](https://github.com/user-attachments/assets/f42504ca-01de-4f2d-ba30-f322f0b0ecec)
  - They will often define production standards as code, and work to smooth out any sharp edges to greatly simplify things for the product developers running their own services.
  - 









