<img src="banner.jpeg"/>

## Frontend Engineer - Coding challenge

This test is a part of our hiring process at Tailwarden for the Frontend Engineer position. It should take you up to 3 hours depending on your experience.

At Tailwarden, our frontend stack consists of the following:
- React with Next.js (currently on version 12, to be upgraded to version 13 with the app directory)
- Typescript
- TailwindCSS
- Storybook
- Jest & React Testing Library

> Feel free to use any modern framework of your choice, as long as you are using Typescript to write type safe code and documenting your components on Storybook.

## Goal

For this assignment, you are supposed to build a simple dashboard for developers to monitor their cloud costs and usage. 

To give you an idea, here's how the app should look like:

![Mokckup](mockup.png)

In a nutshell: users can toggle the accounts to display their data inside the widgets.
Unless you want to, there's no need to spend too much time in the visuals or the responsiveness of this page. We have a great design system to back you up in the future! ;)

> In case you need recommendation of a chart lib to assist you on the journey, we can recommend [Nivo](https://nivo.rocks/) as it provides a great developer experience with React.

### API documentation

To fetch the list of cloud accounts, you’ll need to make a request to a publicly-available API to get JSON content:

```
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

```
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

```
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

Create a new repo into your favorite git platform (GitHub, Gitlab, etc) with a README file containing a list of instructions to run the project. Bonus points if you deploy your solution.

Once you are finished, you can share the repository URL with us.

### Review

After you delivered the completed assignment to us, we will review it as soon as we can, generally within 48 hours. **We pay special attention to:**

- [ ] Code organization & good code splitting
- [ ] Declarative and explicit naming for files, functions, consts etc
- [ ] Adopting a component-based structure with Storybook
- [ ] Overall code quality

### Good luck! 🚀
