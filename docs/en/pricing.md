---
title: Pricing & Plans
description: Simple, transparent pricing designed for startups. Pay per email sent, not per contact — and pay for AI only by actual usage.
---

# Pricing & Plans

> Simple, transparent pricing designed for startups. Pay only for what you use.

## Pricing Model

LiteStartup uses a **pay-per-email** model instead of per-contact pricing. This means you can import unlimited contacts and only pay for the emails you actually send.

### Why Pay-Per-Email?

- **Save Money**: Import 100K contacts, pay only for emails sent
- **No Surprises**: Predictable costs based on actual usage
- **Scale Freely**: Grow your contact list without increasing costs
- **Fair Pricing**: Only pay for what you use

## Plan Comparison

| Feature | Free | Pro | Enterprise |
|---------|------|-----|------------|
| Price | $0 | $20/month or $200/year | Custom |
| Sent emails / month | 5,000 | 50,000 | Unlimited |
| Sent emails / day | 200 | Unlimited | Unlimited |
| Received emails / month | 5,000 | Unlimited | Unlimited |
| Overage Rate | N/A | $0.40 / 1,000 sent | Included |
| Contacts | 3,000 | Unlimited | Unlimited |
| Contact tag groups | 1 | Unlimited | Unlimited |
| Domains | 1 | 10 | Unlimited |
| Domain emails | 20 | 200 | Unlimited |
| Teams | 1 | 10 | Unlimited |
| Team members | 3 | Unlimited | Unlimited |
| Storage | 1 GB | 20 GB | Custom |
| Bandwidth | 1 GB | 10 GB | Custom |
| Data retention | 30 days | 100 days | Custom |
| AI trial credit (one-time) | $1 | $1 + $5 on first upgrade | Custom |
| AI Gateway usage | Pay-as-you-go | Pay-as-you-go | Pay-as-you-go |
| Email Templates | Basic | All | All + Custom |
| Automation | Basic | Advanced | Advanced + Custom |
| AI Content Assistant | Yes | Yes | Yes |
| AI Website Builder | Yes | Yes | Yes |
| Ticket & Live chat | Yes | Yes | Yes |
| Webhooks | Yes | Yes | Yes |
| API Access | Yes | Yes | Yes |
| Support | 5x8 | 7x24 | 7x24(Dedicated) |
| Uptime SLA | 99.9% | 99.9% | 99.99% |
| Custom Domain | Yes | Yes | Yes |

> **AI is billed separately from your plan.** Plan limits cover email, publishing, and
> collaboration. AI Gateway usage is charged in USD by actual consumption — see
> [AI Gateway Pricing](#ai-gateway-pricing) below.

## Plans

### Free Plan

**$0/month**

Perfect for getting started and testing the platform.

**Includes:**
- 5,000 sent emails per month (200 per day)
- 5,000 received emails per month
- 3,000 contacts
- 1 domain and 20 domain emails
- 1 team with 3 members
- 1 GB storage and 1 GB bandwidth
- Basic email templates
- Email tracking (opens & clicks)
- Basic automation
- API access
- AI Website Builder
- Ticket & Live chat
- AI Content Assistant
- $1 one-time AI trial credit for AI Gateway
- Community support

**Limitations:**
- 5,000 sent emails/month, 200/day
- 30-day data retention
- Basic features only
- Community support only

**Best for:**
- Startups just getting started
- Testing the platform
- Small newsletters

### Pro Plan

**$20/month**

For growing startups and small businesses.

**$20/month, or $200/year (save $40)**

**Includes:**
- 50,000 sent emails per month, unlimited per day
- Unlimited received emails
- Unlimited contacts and tag groups
- 10 domains and 200 domain emails
- 10 teams with unlimited members
- 20 GB storage and 10 GB bandwidth
- 100-day data retention
- All email templates
- Advanced email tracking
- Advanced automation & workflows
- Subscription forms
- Waitlist management
- AI Content Assistant
- An extra $5 one-time AI trial credit on your first upgrade
- Priority support
- Custom domain support
- API access
- Webhooks

**Additional:**
- $0.40 per 1,000 sent emails over limit
- Overage billing only when needed

**Best for:**
- Growing startups
- Active marketing campaigns
- Multiple team members

### Enterprise Plan

**Custom pricing**

For large-scale operations and enterprises.

**Includes:**
- Unlimited emails per month
- Unlimited contacts
- Unlimited workmail accounts
- Dedicated account manager
- Custom integrations
- SLA guarantee (99.99% uptime)
- Advanced security features
- Custom branding
- White-label options
- Priority support (24/7)
- Advanced analytics
- Custom workflows

**Best for:**
- Large enterprises
- High-volume senders
- Custom requirements

## Billing

### How Billing Works

1. **Monthly Cycle**: Billing period runs from the 1st to the last day of each month
2. **Base Charge**: Your plan's monthly fee is charged on the 1st of each month
3. **Overage Charges**: Additional charges for emails sent over your plan limit
4. **Invoice**: Detailed invoice sent at end of month
5. **Payment**: Charged to your credit card automatically

### Overage Pricing

**Pro Plan**: $0.40 per 1,000 sent emails over 50,000/month

**Examples:**
- 60,000 emails sent = $20 + $4 (10K overage) = $24
- 90,000 emails sent = $20 + $16 (40K overage) = $36
- 150,000 emails sent = $20 + $40 (100K overage) = $60

### Payment Methods

We accept:
- Credit cards (Visa, Mastercard, American Express)
- Debit cards
- PayPal
- Bank transfer (Enterprise only)

### Invoices

- Invoices are generated monthly
- Available in your dashboard
- Sent to your billing email
- Can be downloaded as PDF

### Refunds

- Monthly subscriptions: No refunds
- Upgrade: Prorated credit applied
- Downgrade: Prorated refund or credit applied

## AI Gateway Pricing

AI Gateway is billed **in USD by actual usage**, independently of your plan. There are
no AI quotas and no monthly AI allowance — you pay for exactly what you generate.

### Two wallets

| | Trial credit | Pay-as-you-go balance |
|---|---|---|
| **Where it comes from** | Granted automatically | You top it up |
| **Amount** | $1 on signup, plus $5 the first time you upgrade to Pro | Any amount |
| **Expires** | Never | Never |
| **Resets** | Never — it is a one-time trial fund | Never |
| **Covers** | AI Gateway only | AI Gateway, email overage, and other extras |
| **Lifetime cap** | $6 per account | None |

### How a request is charged

1. The cost of the request is deducted from your **trial credit** first.
2. When the trial credit is exhausted, the remainder is charged to your **balance**.
3. A single request may draw on both — if $0.10 of trial credit is left and the request
   costs $0.30, you are charged $0.10 of trial credit and $0.20 of balance.
4. If neither wallet can cover it, the request is rejected with `429` and you are
   prompted to top up.

### Rates

Every model publishes its own rate, billed per token, per image, per second, or per
request depending on the capability. See the
[model list](https://www.litestartup.com/models/list) for current rates, or call
`GET /ai/models` to read them programmatically.

> **Topping up is available on every plan, including Free.** You do not need to upgrade
> to Pro to keep using AI Gateway after the trial credit runs out.

## Frequently Asked Questions

### Billing & Pricing

**Q: Can I change my plan anytime?**
A: Yes! You can upgrade or downgrade your plan anytime. Changes take effect immediately.

**Q: What happens if I exceed my email limit?**
A: You'll be charged $0.40 per 1,000 additional sent emails. You can continue sending without interruption.

**Q: Is AI included in my plan?**
A: No. AI Gateway is billed by actual usage in USD, separately from your plan. Every account starts with a $1 trial credit, plus $5 the first time you upgrade to Pro. After that, AI usage is charged to your pay-as-you-go balance.

**Q: Does the AI trial credit reset every month?**
A: No. It is a one-time trial fund, not a monthly allowance. It never expires and is never topped back up — once spent, AI usage continues from your balance.

**Q: Can Free users pay for AI?**
A: Yes. Topping up your balance is available on every plan, so you can keep using AI Gateway without upgrading.

**Q: Do I pay for bounced emails?**
A: Yes, bounced emails count toward your monthly limit. We recommend maintaining a clean contact list.

**Q: Can I get a discount for annual billing?**
A: Contact our sales team for annual billing discounts and custom pricing.

**Q: Is there a setup fee?**
A: No, there are no setup fees or hidden charges. You only pay for the plan and emails sent.

**Q: Can I get an invoice?**
A: Yes, invoices are automatically generated and available in your dashboard.

### Free Plan

**Q: How long can I use the free plan?**
A: Indefinitely! The free plan has no time limit.

**Q: Can I upgrade from free to pro?**
A: Yes, you can upgrade anytime. Your account will be upgraded immediately.

**Q: What happens to my data if I don't upgrade?**
A: Your data remains safe. You can continue using the free plan or upgrade whenever you're ready.

**Q: Are there any limitations on the free plan?**
A: The free plan includes 5,000 sent emails per month (200 per day) and 5,000 received emails. Other features are limited to basic functionality.

### Pro Plan

**Q: What's included in the Pro plan?**
A: 50,000 sent emails/month, unlimited received emails, unlimited contacts, 10 domains, 200 domain emails, automation, AI Content Assistant, and more.

**Q: Can I add more domain emails?**
A: The Pro plan includes 200 domain emails across 10 domains. Contact support if you need more.

**Q: Is there a contract?**
A: No, all plans are month-to-month with no long-term commitment.

### Features

**Q: What's included in the AI Content Assistant?**
A: Subject line generation, email copy suggestions, A/B test variations, and tone adjustment.

**Q: Can I use custom domains?**
A: Yes, custom domains are available on Pro and Enterprise plans.

**Q: What automation features are included?**
A: Welcome series, re-engagement campaigns, win-back campaigns, abandoned cart recovery, and more.

**Q: Can I create custom workflows?**
A: Yes, you can create custom workflows with triggers, conditions, and actions.

### Technical

**Q: Is there an API rate limit?**
A: Yes, rate limits depend on your plan. Free: 60 req/min, Pro: 300 req/min.

**Q: Can I use webhooks?**
A: Webhooks are available on Pro and Enterprise plans.

**Q: What's the email delivery rate?**
A: We maintain a 99.9%+ delivery rate through infrastructure built by AWS & Google Cloud engineers.

**Q: Can I schedule emails?**
A: Yes, you can schedule emails to be sent at a specific time.

### Support

**Q: What support is included?**
A: Free plan: Community support. Pro: Priority email support. Enterprise: 24/7 dedicated support.

**Q: How fast is support response time?**
A: Pro plan: 24 hours. Enterprise: 1 hour for critical issues.

**Q: Is there a knowledge base?**
A: Yes, we have comprehensive documentation and code examples.

## Upgrade & Downgrade

### Upgrade Your Plan

1. Go to **Settings** → **Billing**
2. Click **"Upgrade Plan"**
3. Select new plan
4. Review pricing
5. Click **"Upgrade"**
6. Changes take effect immediately

### Downgrade Your Plan

1. Go to **Settings** → **Billing**
2. Click **"Downgrade Plan"**
3. Select new plan
4. Confirm downgrade
5. Changes take effect at end of billing cycle

### Prorated Billing

When you upgrade or downgrade mid-month:
- **Upgrade**: Pay difference for remaining days
- **Downgrade**: Receive credit for remaining days

## Enterprise & Custom Pricing

For organizations with specific needs:

- **High-volume senders**: Unlimited emails with custom pricing
- **Custom integrations**: Dedicated development support
- **White-label**: Rebrand LiteStartup as your own
- **SLA guarantee**: 99.99% uptime guarantee
- **Dedicated support**: 24/7 account manager

### Contact Sales

For enterprise inquiries:
- Email: sales@litestartup.com
- Phone: Available for enterprise customers
- Website: [LiteStartup.com](https://www.litestartup.com)

## Cost Calculator

### Estimate Your Monthly Cost

**Step 1: Estimate monthly emails**
- Average emails per month: ___________

**Step 2: Choose plan**
- Free: 5,000 sent emails/month = $0
- Pro: 50,000 sent emails/month = $20

**Step 3: Calculate overage (Pro plan)**
- Sent emails over 50,000 × $0.40 per 1,000 = Overage cost

**Step 4: Add AI usage (optional)**
- AI Gateway is billed separately by actual usage, after your one-time trial credit

**Example Calculations:**

**Scenario 1: Small startup**
- 4,000 emails/month
- Plan: Free ($0)
- Total: $0/month

**Scenario 2: Growing business**
- 45,000 emails/month
- Plan: Pro ($20)
- Overage: None
- Total: $20/month

**Scenario 3: Active marketing**
- 90,000 emails/month
- Plan: Pro ($20)
- Overage: 40,000 × $0.40/1K = $16
- Total: $36/month

**Scenario 4: High-volume sender**
- 500,000 emails/month
- Plan: Enterprise (Custom)
- Contact sales for pricing

## Money-Back Guarantee

We're confident you'll love LiteStartup. If you're not satisfied within 30 days of upgrading to Pro, we'll refund your money. No questions asked.

**Conditions:**
- Applies to first month of Pro plan only
- Must request within 30 days of upgrade
- Applies to plan fees only (not overages)

## Special Offers

### Startup Program

Eligible startups get:
- 80% off Pro plan for 6 months
- Priority support
- Free consultation

**Requirements:**
- Founded within last 1 year
- Annual income below $50,000
- Valid business registration

### Nonprofit Discount

Nonprofits receive:
- 50% off all plans
- Unlimited support
- Free custom domain


### Educational Discount

Students and educators get:
- Free Pro plan
- Valid .edu email required

You can apply for the Startup Program, Nonprofit Discount, or Educational Discount by contacting sales@litestartup.com.

## Billing Support

### Common Billing Issues

**Q: My credit card was declined**
A: Check your card details, expiration date, and billing address. Contact your bank if issues persist.

**Q: I want to cancel my subscription**
A: You can cancel anytime in Settings → Billing. Your access continues until end of billing period.

**Q: How do I update my billing information?**
A: Go to Settings → Billing → Payment Method to update your card details.

**Q: Can I get a receipt?**
A: Yes, receipts are available in your dashboard under Billing → Invoices.

### Contact Billing Support

- Email: billing@litestartup.com
- Response time: 24 hours
- Available: Monday-Friday, 9am-5pm UTC
