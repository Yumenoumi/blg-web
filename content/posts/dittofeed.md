---
title: dittofeed
date: 2024-10-26T12:19:57+08:00
draft: False
featuredImage: https://images.unsplash.com/photo-1726293993561-ae9901d8c6d0?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3Mjk5MTYzNTJ8&ixlib=rb-4.0.3
featuredImagePreview: https://images.unsplash.com/photo-1726293993561-ae9901d8c6d0?ixid=M3w0NjAwMjJ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3Mjk5MTYzNTJ8&ixlib=rb-4.0.3
---

# [dittofeed/dittofeed](https://github.com/dittofeed/dittofeed)

<p align="center">
  <a href="https://dittofeed.com">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/dittofeed/dittofeed/main/packages/docs/logo/dark.png">
      <img alt="dittofeed logo" src="https://raw.githubusercontent.com/dittofeed/dittofeed/main/packages/docs/logo/light.png">
    </picture>
  </a>
</p>

---

<h2 align="center">Open-source customer engagement</h3>

<p align="center">
  <a href="https://docs.dittofeed.com/introduction">Docs</a> | <a href="https://discord.gg/HajPkCG4Mm">Discord</a> | <a href="https://demo.dittofeed.com/dashboard">Demo App</a> | <a href="https://docs.dittofeed.com/contributing/running-locally">Contributing</a>
</p>

[Dittofeed](https://dittofeed.com) is an omni-channel customer engagement platform. Create automated user journeys to message users along any channel: email, mobile push notifications, SMS, WhatsApp, Slack, and more. We're an open source, dev-friendly alternative to platforms like OneSignal, Customer.io, and Segment Engage.

- 1️⃣ Connect user data via Segment, Reverse ETL, or the Dittofeed API ⛓️
- 2️⃣ Create highly customizable user segments with multiple operators 🧍🏽‍♀️🧍🏻‍♂️🧍🏾
- 3️⃣ Design messaging templates using HTML, MJML, or Markdown 👨🏻‍🎨
- 4️⃣ Automate user journeys with a powerful, easy-to-use GUI interface 🛩️
- 5️⃣ Integrate with major ESPs like Sendgrid and Amazon SES 🏰
- 6️⃣ Track and analyze message performance from the dashboard 🎯

<br>

<a href="https://dittofeed.com/">
  <img src="packages/docs/images/github-readme-banner.png" alt="Dittofeed Admin Panel Banner" />
</a>

<br>

### Dashboard Views

<details>
  <summary><b>Journey Builder</b></summary>
  <img alt="Customer Journeys" src="packages/docs/images/journeys_github.png">
</details>
<details>
  <summary><b>Segmentation</b></summary>
  <img alt="User Segmentation" src="packages/docs/images/segments_github.png">
</details>
<details>
  <summary><b>Template Editor</b></summary>
  <img alt="Messaging Templates" src="packages/docs/images/templates_github.png">
</details>

### Architecture

<details>
  <summary><b>Visual Diagram</b></summary>
  <img alt="Architecture" src="packages/docs/images/architecture-readme.png">
</details>

For the full dashboard experience, play around with the [demo app](https://demo.dittofeed.com/dashboard).

## Quick Deployment

Click Deploy to Render below and follow the prompts to deploy Dittofeed on Render. See the "Self-Host with Render" [docs for more info](https://docs.dittofeed.com/deployment/self-hosted/render).

<a href="https://render.com/deploy?repo=https://github.com/dittofeed/dittofeed" target="_blank" rel="nofollow"><img src="https://render.com/images/deploy-to-render-button.svg" alt="Deploy To Render"></a>

## Roadmap

☑️ = in development | ✅ = in production


### Q3: July 1 to Sept 30

| Feature                       | Purpose                                                                                                               | Status  |
|-------------------------------|-----------------------------------------------------------------------------------------------------------------------|---------|
| Low code template builder     | Allows members to build email templates in a low-code interface without manual encoding in MJML.                      | - ✅  |
| Embeddable Components        | Enables embedding of Journey Builder, Segment Builder, Template Builder, etc., into third-party apps.                  | - ✅   |

---

### Q4: Oct 1 to Dec 31

| Feature                      | Purpose                                                                                               | Status  |
|------------------------------|-------------------------------------------------------------------------------------------------------|---------|
| LLM Integration              | Drives the generation of journeys, segments, and templates.                                           | - \[ ]   |
| Identity resolution           | Enables joining of users based on traits or behavior, important for identifying anonymous users post sign-up/sign-in. | - ☑️   |
| User grouping                 | Provides a way to represent a collection of users (e.g., club, company, team) for segment membership conditions.      | - ☑️   |

---



## Developer-centric

Beyond having industry-standard GUI tools, we focus on developer happiness with first-in-class dev-focused features:

- Branch-based git workflows that support messaging campaign version control.
- Write email templates in your favorite editor, checked into git - not in an unversioned web based IDE.
- Testing SDK to test your messaging campaigns in CI. No more manually QAing them in production.
- Self-hostable. Protect your sensitive PII inside of your own VPC. Avoid volume-based pricing.
- Journey monitoring and alerting.

More to come...

## Support

If you're interested in trying us out, please get in touch!

* [Discord community](https://discord.gg/HajPkCG4Mm)
* [Email support](mailto:support@dittofeed.com)
* [Open an issue](https://github.com/dittofeed/dittofeed/issues/new)
* [Book a meeting](https://calendly.com/d/zy7-8d5-jdq/dittofeed-demo-founders)

## Contributing

For instructions on how to run Dittofeed locally and contribute to this project, see Dittofeed's [contributing docs](https://docs.dittofeed.com/contributing/).

## License

[MIT licensed](/LICENSE), and free forever.
