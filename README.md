<img src="banner.jpeg"/>

## Frontend Engineer - Coding challenge

This test is a part of our hiring process at Tailwarden for the Frontend Engineer position. It should take you between 1 and 3 hours depending on your experience.

**Feel free to apply! Drop us a line with your LinkedIn/GitHub/Twitter and link of your code repository at [mohamed@tailwarden.com](mailto:mohamed@tailwarden.com)**

At Tailwarden, our frontend stack consists of React and Next.js, but you are free to use any modern framework you wish, or do it VanillaJS style. 

> Threat this project as if you/we would continue working on this after your assignment: maintainability, scalability, and readability are super important.

## Goal

For this assignment, you are supposed to build a dashboard for developers to monitor their cloud costs and usage.

To give you an idea, here how the app should look like:

![Mokckup](mockup.png)

Developers can do the following:

- Add a cloud account (AWS, GCP, Azure ...)
- Track cloud account stats (costs & usage)
- Filter data by cloud account.

>  Bonus: Surprise us! Add a feature that you think would work well here ! Also, feel free to add your own look & feel.

### API documentation

To fetch the list of cloud accounts, you’ll need to make request to a publicly-available API to get JSON content:

```json
GET https://hiring.tailwarden.com/v1/accounts
```

The JSON response contains an array of cloud accounts, each account has the following JSON attributes:

```json
{
    "id": "62666a73422739696d520c91",
    "provider": "AWS",
    "label": "production",
    "logo": "https://cdn.komiser.io/images/aws.png"
}
```

To get a cloud account stats, issue the following request:

```json
GET https://hiring.tailwarden.com/v1/accounts/{id}
```

The JSON response contains the following attributes:

```json
{
    "bill": 1479.22,
    "servers": 135,
    "regions": 3,
    "alarms": 2
}
```

To get a cloud account costs grouped by service for the last 6 months, use the following endpoint:

```json
GET https://hiring.tailwarden.com/v1/accounts/{id}/history
```

The JSON response contains an array of datapoints. Each datapoint contains the following attributes:

```json
{
    "date": "2021-04-01T00:00:00.000Z",
    "groups": [
        {
            "key": "Compute",
            "amount": 53.33
        },
        {
            "key": "Storage",
            "amount": 146.1
        },
        {
            "key": "Network",
            "amount": 72.35
        }
    ]
}
```

### Submission

Create a new repo into your favorite git platform (GitHub, Gitlab, etc) with a README file containing list of instructions to run the project.

After you've finished, you can share the repository URL with us.

### Review

After you delivered the completed assignment to us, we will review it as soon as we can, generally within 48 hours. **We pay special attention to:**

- [ ] Coding skills (testable code, usage of HTML & CSS properly)
- [ ] Adopting a component-based structure with a clean modern look.
- [ ] Code organization (modularity, dependencies between modules, naming, etc)
- [ ] Overall code quality (edge cases, usage of tools, performance, best practices)

### Good luck,
