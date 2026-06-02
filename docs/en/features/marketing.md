---
title: Campaigns
description: Send marketing emails efficiently to your audience with LiteStartup's campaign tools.
---

# Campaigns

> Send marketing emails efficiently without code.

Navigate to **Emails > Campaigns** from the sidebar.

Campaigns allow you to send email blasts to your customers using a no-code editor on LiteStartup, or from our [Marketing API](api/marketing-create.md).

You can use this to send email blasts such as:

* Newsletters
* Product Launches
* Investor Updates
* Promotions
* Changelogs

## Sending a Marketing Emails from LiteStartup

Our Marketing feature was made to enable your entire team to send email campaigns without having to ask for help from developers.

### No-Code Editor



### Markdown Support

You can also write your emails using Markdown. This works with headings, lists, italic, bold, links, and quotes.

You can easily copy and paste content from applications like Notion, Google Docs, iA Writter and many others maintaining formatting consistency.



### Custom Styling

You can customize the look and feel of your email by changing **global styles** such as the background color, link color, and container size, allowing you to create emails aligned with your brand identity.

To do this, click on **Styles** at the top left of the Broadcast editor. You can edit specific images or lines of texts by selecting or highlighting them prior to clicking on **Styles**.


You can also edit individual styles for each component, including the font size, font weight, and text alignment. You can also set custom properties for each component, such as image alt, button links, and social links,


### Personalize your content

When creating broadcasts, you can include dynamic audience data to personalize the email content.

* `{{FIRST_NAME}}`
* `{{LAST_NAME}}`
* `{{EMAIL}}`

When you include the `{{UNSUBSCRIBE}}` placeholder, LiteStartup includes an unsubscribe link in the email to automatically handle unsubscribe requests.

### Testing & Sending

Once you're finished writing your email, you can preview it in your personal inbox or send it to your team for feedback.

To do this, click on **Test Email** on the top right of your screen. Enter in the email address you'd like to send your email to, and then click on **Send Test Email** to complete.

Once you're ready to send your email to your Audience, click on **Send**, and slide to confirm.

**Note**: Test emails do not include any custom Reply-To address that may have been configured. This behavior is limited to test mode and does not affect actual email sends.

## Sending a Marketing Email from the API

We also offer the option to send your Marketing Email from our [Marketing API](api/marketing-create.md).

The Marketing API offers 6 endpoints for programmatically creating, updating, and sending marketing emails.

## Understand marketing email statuses

Here are all the statuses that can be associated with a marketing email:

* `draft` - The marketing email is a draft.
* `review` - The campaign is pending AI pre-review before sending.
* `scheduled` - The marketing email is scheduled for a future send time.
* `ready` - The marketing email is ready to send.
* `queued` - The marketing email is queued for delivery.
* `sent` - The marketing email was sent.
