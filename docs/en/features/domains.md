---
title: Domains
description: Configure and verify your sending domains for email delivery with LiteStartup.
---

# Domains

> Configure and verify your sending domains for email delivery.

Domains are essential for sending emails from your own addresses like `hello@yourdomain.com`. LiteStartup requires domain verification to ensure email deliverability and protect your sender reputation.

## Getting Started

1. Go to **Domains** from the sidebar
2. Click **Add Domain** to add your domain
3. Configure DNS records
4. Verify your domain
5. Create domain emails to start sending

## Adding a Domain

### Step 1: Add Domain

1. Click **Add Domain**
2. Enter your domain name (e.g., `yourdomain.com` or `mail.yourdomain.com`)
3. Click **Add**

### Step 2: Configure DNS Records

After adding a domain, the system will generate the specific DNS records you need to configure. Go to your domain detail page to view them.

Typical records include:

| Type | Purpose |
|------|---------|
| MX | Receive emails (inbound) |
| MX | Bounce/complaint handling (feedback) |
| TXT (SPF) | SPF authentication |
| TXT (DKIM) | DKIM signing (`litestartup._domainkey`) |
| TXT (DMARC) | DMARC policy |

> **Note**: The exact record names and values are unique to your domain. Copy them from the domain detail page in LiteStartup.

### Step 3: Verify Domain

1. Add all DNS records to your domain provider
2. Wait for DNS propagation (5-15 minutes)
3. Click **Verify** in LiteStartup
4. Domain status changes to **Verified** when complete

## Cloudflare Automatic Setup

If you use Cloudflare for DNS, you can use automatic setup:

1. Go to your domain detail page
2. Create a Cloudflare API Token with **Edit zone DNS** permission
3. Paste the token in the domain setup page
4. Click **Setup Automatically**
5. DNS records are added automatically

## Domain Status

| Status | Description |
|--------|-------------|
| Pending | Domain added, awaiting DNS configuration |
| Verifying | DNS records detected, verification in progress |
| Verified | Domain verified, ready to send emails |
| Failed | Verification failed, check DNS records |

## Managing Domains

### View Domain Details

Click on a domain to see:

- Verification status
- DNS records
- Associated domain emails
- Configuration options

### Update Domain Settings

1. Click on a domain
2. Update settings as needed
3. Click **Save**

### Delete Domain

1. Click **Delete** on a domain
2. Confirm deletion

> **Warning**: Deleting a domain will also delete all associated domain emails.

## Domain Limits

| Plan | Domain Limit |
|------|--------------|
| Free | 1 domain |
| Pro | 10 domains |
| Enterprise | Unlimited |

## Troubleshooting

### Domain Not Verifying

1. **Check DNS records** - Ensure all records are added correctly
2. **Wait for propagation** - DNS changes can take up to 48 hours
3. **Check for typos** - Verify record names and values exactly match
4. **Check TTL** - Lower TTL values propagate faster

### Common DNS Issues

| Issue | Solution |
|-------|----------|
| SPF record conflict | Merge with existing SPF record |
| DKIM not found | Check `litestartup._domainkey` record |
| MX record missing | Add MX record for receiving emails |

## API Access

Manage domains programmatically via the [Domains API](api/domains-list.md):

- [List Domains](api/domains-list.md)
- [Add Domain](api/domains-add.md)
- [Get Domain](api/domains-get.md)
- [Verify Domain](api/domains-verify.md)
- [Verify Polling](api/domains-verify-polling.md)
- [Config Domain](api/domains-config.md)
- [Update Domain](api/domains-update.md)
- [Delete Domain](api/domains-delete.md)

## Best Practices

- **Use a subdomain** - Consider `mail.yourdomain.com` to separate email infrastructure
- **Set up all records** - SPF, DKIM, and DMARC improve deliverability
- **Monitor status** - Check domain health regularly
- **Keep DNS updated** - Update records if LiteStartup provides new values