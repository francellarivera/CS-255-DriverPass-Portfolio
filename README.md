# CS 255: DriverPass System Analysis and Design

This repository holds my portfolio work from CS 255 (System Analysis and Design):

- **[Business Requirements Document](DriverPass_Business_Requirements_Document.docx)** (Project One)
- **[System Design Document](DriverPass_System_Design_Document.docx)** (Project Two)

## Reflection

**Briefly summarize the DriverPass project. Who was the client? What type of system did they want you to design?**

The client was DriverPass, a company that helps people pass their driving exams. Many people fail the exam because they don't have enough practice or training. DriverPass wanted a cloud-hosted, browser-based system where customers could buy one of three training packages, schedule two-hour driving lessons, and take online practice tests that stay in line with current DMV rules. The system also had to support DriverPass staff. The secretary books lessons for customers who call in, drivers log their lesson times and notes, the IT officer manages accounts, and the owner views and downloads reports from anywhere. Each of those users needed access that matched their role.

**What did you do particularly well?**

I think I did a good job turning the interview into a clear, organized set of requirements, especially security and role-based access. I specified hashed passwords, HTTPS/TLS, lockout after repeated failed logins, self-service password resets, and an activity log that records who created, changed, or canceled each reservation. That log was something the owner specifically asked for. In the system design document, I carried those requirements into the UML diagrams and the technical requirements. For example, I enforced package rules and driver/vehicle conflict checks on the server instead of trusting the browser, and I used a third-party payment processor so that card data never ends up in DriverPass's database.

**If you could choose one part of your work on these documents to revise, what would you pick? How would you improve it?**

I would revise the nonfunctional requirements in the business requirements document so they are measurable. Some of them are too vague to test. For example, "the system must provide a quick response" would be better as "pages should load in under two seconds for 95% of requests." I would also use "The system shall…" for every functional requirement, because I switched between "shall" and "will." Finally, I would give the DMV update requirement a specific check frequency and a backup manual process in case the DMV doesn't offer an API.

**How did you interpret the user's needs and implement them into your system design? Why is it so important to consider the user's needs when designing?**

I read through the interview transcript and noted what each person actually said they needed, then turned each need into a requirement and traced it into the design. When the owner said they wanted to know who made or canceled a reservation, that became an audit-log requirement, then a reservation-history class in the class diagram and a step in the scheduling sequence diagram. When the owner said they didn't want to deal with backups or server security, that led to a cloud-hosted design. Considering the user's needs matters because a system can be technically correct and still fail if it doesn't solve the client's real problem. Changes are also far cheaper to make in the requirements phase than after the system is built.

**How do you approach designing software? What techniques or strategies would you use in the future to analyze and design a system?**

I start by gathering requirements from the people who will use the system, through interviews, questions, and follow-ups. Then I separate those requirements into functional and nonfunctional ones and write down my assumptions and limitations. From there I model the system with UML. Use case diagrams show who does what, activity and sequence diagrams show how processes flow, and class diagrams show how the data is structured. In the future, I would keep using these techniques along with a Gantt chart for planning. I would also use iterative, agile-style check-ins with the client, user stories with acceptance criteria, and early prototypes or wireframes so users can give feedback before development is too far along.
