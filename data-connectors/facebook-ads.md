---
layout: default
title: Facebook Ads
parent: Data Connectors
nav_order: 2
---

# Facebook Ads API Integration
{: .no_toc }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

## Overview
Growth Nirvana's Facebook Ads API integration allows customers to **sync their advertising data** from Facebook Ads into their **data warehouse of choice** (BigQuery, Snowflake, Redshift, etc.).

With this integration, you can:
- Automate **campaign, ad set, and conversion data extraction**
- Support **scheduled and real-time syncs**
- Manage **multiple accounts for agencies**
- Securely authenticate using **OAuth 2.0**

## Getting Started

### Step 1: Connect Facebook Ads
1. In your Growth Nirvana account, click on **"ELT Connectors"** in the left sidebar
2. Click **"Add New Connection"**
3. Select **Facebook Ads** from the available connectors
4. Click **"Connect"** to start the authentication process

### Step 2: Authorize Access
Growth Nirvana uses **OAuth 2.0** to securely connect to your Facebook Ads account.
- When prompted, log in to your **Facebook** account
- Grant permissions for **"ads_management"** (read access to campaign data)
- Growth Nirvana **does not modify any campaign settings**—it only retrieves performance data

## Data Synced

### Available Data Sources

| Data Type | Description |
|-----------|-------------|
| Campaigns | Pulls campaign-level performance metrics |
| Ad Sets | Retrieves ad set-level data |
| Ads | Fetches individual ad performance data |
| Conversions | Syncs conversion data for attribution |
| Audiences | Pulls audience insights and metrics |

### Data Sync Frequency
- **Default:** Daily
- **Custom:** Set up real-time or scheduled syncs via the Growth Nirvana dashboard

## Permissions & Security

### Required Permissions
- `ads_management` – Read access to campaign data
- `ads_read` – Read access to Facebook Ads accounts

### Why does Growth Nirvana need these permissions?
Growth Nirvana **only reads campaign performance data**—it **does not** make any changes to your campaigns.

{: .note }
Growth Nirvana follows industry best practices for **data encryption** and **OAuth authentication**.

## Troubleshooting

### Common Issues & Fixes

#### Error: "Permission Denied"
- Ensure you are **logged into the correct Facebook account**
- Check that your **Facebook Ads user role** allows API access
- If the issue persists, try **re-authenticating** by removing and re-adding the integration

#### Data Not Syncing?
- Check that your campaigns are **active** in Facebook Ads
- Verify your **data sync schedule** in Growth Nirvana

For more help, contact [support@growthnirvana.com](mailto:support@growthnirvana.com)

## Contact Support
Need help? Reach out to **Growth Nirvana Support**:
- **Email:** [support@growthnirvana.com](mailto:support@growthnirvana.com)