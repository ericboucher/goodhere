[![Netlify Status](https://api.netlify.com/api/v1/badges/52ee35e4-6c7d-4fba-aad2-59e9ac81e88e/deploy-status)](https://app.netlify.com/sites/goodhere/deploys)
![](https://img.shields.io/badge/master-green)
![](https://img.shields.io/badge/made%20with-%E2%9D%A4-red)
![](https://img.shields.io/github/contributors/goodhere/goodhere)
[![issues](https://img.shields.io/github/issues/benrmatthews/goodhere)](https://github.com/goodhere/goodhere/issues)
[![sponsor](https://opencollective.com/goodhere/tiers/sponsor/badge.svg?label=sponsor&color=brightgreen)](https://opencollective.com/goodhere)

# Good Here

This is the source code behind [https://goodhere.org][goodhere], an open database of social impact organisations.

Good Here helps you discover impactful projects, connect with the changemakers behind them, and pursue new social impact opportunities.

Our mission is to focus more attention on the organizations making social impact, directing resource and support to teams on the front lines, and making it easier for organizations to find funding.

Our ultimate goal is to facilitate action: More people working on social impact solutions, more funding for social impact organizations, more personal action from individuals.

Beta website: https://goodhere.org/

![Good Here Homepage](https://user-images.githubusercontent.com/1328236/88677289-ffbe3d80-d0e4-11ea-97b3-8c52fc8caabd.png)

## Architecture

Our `site` is built with [Gatsby][gatsby], a static site generator that uses
[React][react] and [GraphQL][graphql] under the hood. Static site generators are
used to create static websites (i.e. plain HTML/CSS/JS) from dynamic data at
**build time**. Compare this to a traditional dynamic website that uses a
**runtime** (PHP, Ruby, Python, etc) to generate pages on-demand.

In place of a custom backend, we use [Airtable][airtable] as our content
management system and API layer. This allows us to iterate on our data schema
and admin workflows extremely quickly, without having to write any code. We use
a plugin called [gatsby-source-airtable][gatsby-source-airtable] to expose our
data to Gatsby's GraphQL layer.

We deploy to [Netlify][netlify], a simple low-cost static web host. Deploys
happen any time code is pushed to GitHub, whether to master or another branch.
Additionally, we use [Zapier][zapier] to deploy once per day in order to publish
new content even when code changes aren't happening.

## Where does Good Here data come from?

The Good Here database is an accumulation of contributions curated by a team of volunteer editors. We supplement contributions with publicly available data, allowing us to provide key facts about about each organization.

## Why is *X* category or *Y* organization on Good Here?

The topic of what does and doesn't qualify as "creating social impact" is filled with differing opinions. The reality is there is not a single right way to solve climate change, just a myriad of opportunities to have an impact. As a result we specifically avoid playing the role of arbiter and have a liberal acceptance policy.

In the future, we will provide ways for our users to weigh in on the impact of specific organizations.

## How can I support Good Here?

We're grateful to have the support of anyone who believes in what we're doing. Check out the [Contribute page](https://goodhere.org/contribute) on our website for more information on how you can help.

## Developer Setup

**Note:** you need to be invited to our Airtable project to run this project
locally. The process is really simple and we accept anyone who's interested in
helping out. Simply fill out the [GoodHere Contributor Application][contributor-app].

1. Follow these steps to get the project installed on your local dev machine.
   ```bash
   $ git clone https://github.com/benrmatthews/goodhere.git
   $ cd goodhere/site
   $ npm install
   ```
2. Copy your Airtable API key from this page: [Airtable account][airtable-account]
3. Create a `.env.development` file at the root of the project
   replacing `YOUR_KEY_HERE` by the key you copied in the previous step:
   ```bash
   $ cp .env.sample .env.development
   ```
4. Run the project like so:
   ```bash
   $ npm run develop
   ```

---

### Bulding

Before submitting your Pull Request you should test that the project builds.

With Gatsby, some code can work on development mode but requires some adaptation for the build. For example when using `window` that is not accessible in SSR (Server-Side Rendering) mode.

To build the project locally:

1.  Create a `.env.production` file at the root of the project
    replacing `YOUR_KEY_HERE` by the key you copied in the previous step:
    ```bash
    $ cp .env.development .env.production
    # OR
    $ cp .env.sample .env.production
    ```
2.  Build the project using the `npm run build` command.
3.  You can then run the website using the `serve public` command.

    Note: if you do not have the `serve` command you can install it using the `npm install -g serve` command



[goodhere]: https://goodhere.org/
[contributor-app]: https://airtable.com/shrftH1zyJPidLg8f
[airtable-account]: https://airtable.com/account
[gatsby]: https://www.gatsbyjs.org/
[react]: https://reactjs.org/
[graphql]: https://graphql.org/
[airtable]: https://airtable.com/
[zapier]: https://zapier.com/
[gatsby-source-airtable]: https://github.com/jbolda/gatsby-source-airtable
[netlify]: https://www.netlify.com/
[issues]: https://github.com/goodhere/goodhere/issues
[sponsor]: https://opencollective.com/goodhere
