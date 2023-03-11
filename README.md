# Section1: Non-technical
<br><br>
Peter, a member of the sales team just onboarded a high value merchant - Codak Ventures. Before go-live during the integration review session, you had given Codak Ventures' integration a green light and the merchant has gone ahead to open the service to its customers.

In recent times, the merchant has escalated a number of issues which point to the fact that there are issues with their integration. These errors are primarily responsible for the escalated issues. The dev team for the merchant is becoming impatient and has threatened to churn if their issues are not resolved ASAP. How will you handle such a merchant and manage the expectations of Peter in preventing Churn.
<br>
## Solution: Codak Venture Issue

A straight answer to this is to share with Codak Ventures a Calendly link (or any in-house adopted booking tool) to enable them to book a technical meeting with me (at a mutually convenient time) for us to review how they are consuming our API.
<br><br>
I have come to realise from experience that complaints like that from Codak Ventures could be related to any of:
<br><br>
- User-generated issue: a poor understanding of the documentation could lead to a wrong implementation. Let us take for instance looking at Okra's Spending Habit API, the endpoint to process spending patterns:

It is required that the customer\_id be sent in the body of the request. This customer\_id is supposed to be common to Okra and Codak Ventures' backend system (say a database they maintain for populating the responses to their webhook). This customer\_id is gotten at the point of authentication.

A poorly implemented process could be saving request-id in a database table field originally meant to save the customer\_id returned at the point of calling Okra's account authentication.

In such a scenario, calling the spending habit endpoint will be using the wrong value as request\_id does not identify any user on Okra's system.

A meeting with Codak Ventures for live troubleshooting will fix this kind of problem.
<br><br>
- Internal issue: in honesty, you cannot have a 100% perfect system, especially when it has to do with a technical product.

While it is of utmost importance to have downtime alerts implemented to ensure the internal stakeholders are immediately aware of any problem, some could take minutes to hours to resolve which might affect the overall operations and the efficiency of the API within that downtime period.

Partners should be well informed of such downtime and giving them an estimate of when the service will be back up will be great too. If there is a Slack channel maintained with the third parties, a broadcast can be sent coordinating with the Customer Experience Team.

When this is resolved, a root-cause analysis should be done and documentation maintained on what caused the issue and how this was resolved. This will help for faster resolution if it ever comes up in the future.
<br><br>
- Third-party issue: Okra works with banks and other parties. A downtime with any of its partners will affect a part of its operation.

In such a scenario, Okra has no control but to Codak Ventures, the API is Okra's API and a problem with it is a problem with Okra.

Before a partner raises an alarm for a third-party emanating downtime, it is important that as a support person, Peter (and other members of the Sales Team) are informed of the third-party issue on time and can explain the situation to all partners using the Okra API for their business while myself and members of the technical support team work with the third party to resolve the issue.
<br><br><br><br>
# Section 2: Semi technical

As a Technical Support Engineer, you'll need to have exceptional people skills and the engineering mindset that will allow you to troubleshoot, diagnose and resolve while communicating the issue effectively to the client. As such, we'd like to evaluate your language and engineering skills.

Please answer on the below list of questions as if you would answer a customer in real-life, feel free to use the Okra docs ([https://docs.okra.ng/docs](https://docs.okra.ng/docs)).
<br>

## Jesse's Issue

1. Hey Okra team, I'm trying to get the latest transactions and I'm hitting the [https://api.okra.ng/v2/transactions/getById](https://api.okra.ng/v2/transactions/getById) but it's only giving me a week old transactions for some reason. Please help! Jesse
<br><br>
### Reply to Jesse:

Hi Jesse,

Please, apologies to learn you are facing a challenge getting the desired result for the request.
<br>
Kindly note that the getById endpoint only pulls records tied to an Id and if the Id is for records for a specific period (last week according to you), it will always return that.
<br>
Kindly refer to the endpoint below which could resolve the challenge you are facing if you intend to get the transactions for a customer within a specific period:
<br>
- Use the [https://docs.okra.ng/reference/gettransactionbycustomerdate](https://docs.okra.ng/reference/gettransactionbycustomerdate) endpoint and specify the period for which you want to retrieve the transaction details for the customer.
<br>

Kindly try this and if you still face any challenges or you want to achieve another objective with your request, you can reply to this ticket.
<br><br>
Regards,
<br>
Meed Umoru
<br><br>
## Mike's Issue

2. Hi! I've setup the Widget and I can connect the account, however I don't understand how to programmatically indicate that the connection was successful or it thrown an error. Thanks in advance. Mike
<br><br>
### Reply to Mike:
<br><br>
Hi Mark,
<br><br>
Thanks for reaching out to us and happy to know you have been able to set up the widget.
<br>
Kindly note that the widget allows you to define custom messages for successful and failed connections using the below properties:
<br>
- widget\_success: use this to define a custom message for a successful connection
- widget\_failed: use this to define a custom message for a failed connection
<br><br>

Please, you can explore other properties available to use when configuring your widget by visiting the widget-properties page at [https://docs.okra.ng/docs/widget-properties](https://docs.okra.ng/docs/widget-properties).
<br><br>
Do reply to this email if you require more assistance.
<br><br>
Regards,
<br>
Meed Umoru
<br><br>
## Blessing's Issue
<br><br>
3. Hello, my name is Blessing and I would like to understand how do I test Okra. I wouldn't like to pay for my testing.
<br><br>
### Reply to Blessing:
<br><br>
Hi Blessing,
<br><br>
We are happy to know of your interest to explore our API.
<br>
Kindly note that you do not need to pay to test our APIs.
<br>
To get started, kindly:
<br>
- Create an account at [https://dash.okra.ng/register](https://dash.okra.ng/register) and provide the needed KYC information. Once your account is created and activated, you can then
- Check our documentation at [https://docs.okra.ng/docs/home](https://docs.okra.ng/docs/home) to see the list of the amazing things you can do with our API
- Once you have an understanding of the API, you can test it within our sandbox environment. You require your API keys which you can retrieve from your dashboard
<br><br>

Kindly note that our sandbox contains dummy data but will allow you to simulate the flow in a production scenario.
<br>
Thank you and let me know if you face any issues testing the APIs.
<br><br>
Regards,

Meed Umoru
<br><br>
# Section1: Technical

Given the following, can you troubleshoot why the customer is having issues with these routes? Feel free to use Postman or any tool of your choice.

## Problem 1:

\*\*Route\*\*

[https://docs.okra.ng/reference/fetchauths](https://docs.okra.ng/reference/fetchauths)

\*\*Bearer Token\*\*

```jsx

eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJfaWQiOiI1ZGE2MzU4MTMwYTk0MzQ4NmYzM2RjZWQiLCJpYXQiOjE2NzU4NDk5NTR9.DP2dfE9xDXKwviPeMQa6a1\_pXkxIa3C8G8kPbg9o1Vk

```

Payload

```jsx

{

page: 1

}

```
<br>

### The reason for Problem 1:

From the body of the request, the parameter page is expected as a string but it has not been specified.
<br>
Though, this request retrieved records actually when pushed with the parameter as a string.
<br>
Refer to attached the request and response received.

https://drive.google.com/file/d/16tjRXodLjqPeWTxjc3gFhVzVs-YQtURA/view?usp=sharing

<br>
Another likely problem could be the client's webhook getting too much data not required because no limit was specified in the body of the request.

<br><br>

## Problem 2:

**Route**

[https://docs.okra.ng/reference/getidentitybydate](https://docs.okra.ng/reference/getidentitybydate)

**Bearer Token**

```jsx

eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJfaWQiOiI1ZGE2MzU4MTMwYTk0MzQ4NmYzM2RjZWQiLCJpYXQiOjE2NjI2MjE0MTN9.EflhGhk91iyA\_wssscl78-dM7KBfmtQZBfXUa\_mv5-E

```

**Payload**

{

page: 1

}

<br>

### The reason for Problem 2:
<br>
Please, the request format is wrong for the getidentitybydate endpoint.
<br>
The endpoint requires two parameters not given in the body of the request:
<br>

- From
- To

