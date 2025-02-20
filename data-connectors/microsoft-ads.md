---
layout: default
title: Microsoft Ads
parent: Data Connectors
nav_order: 1
---

# Microsoft Ads API Integration
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
Growth Nirvana's Microsoft Ads API integration allows customers to **sync their advertising data** from Microsoft Ads into their **data warehouse of choice** (BigQuery, Snowflake, Redshift, etc.).

With this integration, you can:
- Automate **campaign, keyword, and conversion data extraction**
- Support **scheduled and real-time syncs**
- Manage **multiple accounts for agencies**
- Securely authenticate using **OAuth 2.0**

## Getting Started

### Step 1: Connect Microsoft Ads
1. In your Growth Nirvana account, click on **"ELT Connectors"** in the left sidebar
2. Click the **"Add New Connector"** button in the top right corner
3. Select **Microsoft Ads** from the available connectors
4. Click **"Connect"** to start the authentication process

### Step 2: Authorize Access
Growth Nirvana uses **OAuth 2.0** to securely connect to your Microsoft Ads account.
- When prompted, log in to your **Microsoft Ads** account
- Grant permissions for **"ads.manage"** (read access to campaign data)
- Growth Nirvana **does not modify any campaign settings**—it only retrieves performance data

## Data Synced

### Available Data Sources

| Data Type | Description |
|-----------|-------------|
| Ad Insights | Retrieves detailed ad performance metrics |
| Ad Groups | Retrieves ad group-level data |
| Campaigns | Pulls campaign-level performance metrics |
| Keywords | Fetches keyword performance, CPC, CTR |
| Conversions | Syncs conversion data for attribution |
| User Location | Pulls user location data |

### Data Sync Frequency
- **Default:** Every 12 hours
- **Custom:** Set up scheduled syncs via the Growth Nirvana dashboard

## Permissions & Security

### Required Permissions

Growth Nirvana follows the principle of least privilege, requesting only the minimum permissions required by the Microsoft Ads API:

- `ads.manage` – Access to campaign data
- `msads.manage` – Access to Microsoft Advertising accounts

{: .note }
While these permissions include write access, Growth Nirvana operates as a read-only platform and never modifies your advertising campaigns or account settings.

### Why does Growth Nirvana need these permissions?
These are the minimum permissions required by Microsoft's API to access advertising data. Although these permissions include write capabilities, Growth Nirvana's platform is architected to perform read-only operations—it **does not** make any changes to your campaigns or settings.

{: .note }
Growth Nirvana follows industry best practices for **data encryption** and **OAuth authentication**.

## Troubleshooting

### Common Issues & Fixes

#### Error: "Permission Denied"
- Ensure you are **logged into the correct Microsoft Ads account**
- Check that your **Microsoft Ads user role** allows API access
- If the issue persists, try **re-authenticating** by removing and re-adding the integration

#### Data Not Syncing?
- Check that your campaigns are **active** in Microsoft Ads
- Verify your **data sync schedule** in Growth Nirvana

For more help, contact [support@growthnirvana.com](mailto:support@growthnirvana.com)

## Contact Support
Need help? Reach out to **Growth Nirvana Support**:
- **Email:** [support@growthnirvana.com](mailto:support@growthnirvana.com) 