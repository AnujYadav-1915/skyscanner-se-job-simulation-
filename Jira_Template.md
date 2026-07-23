# JIRA USER STORIES & TICKETS DOCUMENT

**Project Name:** Skyscanner Advertising Portal Redesign  
**Project Key:** SKY  
**Reporter:** Anuj Yadav  
**Date:** July 23, 2026  
**Status:** Approved for Engineering Implementation  

---

## Ticket #1: Ad Creation Interface Redesign

* **Issue Key:** SKY-101
* **Issue Type:** Story
* **Project:** Skyscanner
* **Summary / Title:** Implement External Partner Ad Creation Interface with Modular Card Selectors
* **Reporter:** Anuj Yadav
* **Assignee:** Front-End Development Team
* **Priority:** High

### Description
> **As a developer, I would like to** build a modern, self-serve ad creation interface for external Skyscanner advertising partners so that external clients can intuitively create Text, Image & Text, and Video advertisements with minimal training.

#### Background & Product Goals
The legacy internal ad tool was designed for power users, creating high usability friction for new external partners. This story implements the new 3-card ad type selection flow (Text Ad, Image & Text Ad, Video Ad) along with input fields for campaign metadata, target URL, and budget estimation.

#### Component & UI Specifications
1. **Ad Type Selector Cards (`BpkCardView`):**
   - Three equal-width selection cards:
     - **Text Ad:** Icon, description, and "Select" CTA.
     - **Image & Text Ad:** Icon, description, and "Select" CTA.
     - **Video Ad:** Icon, description, and "Select" CTA.
   - Hover & Active states: Sky Blue (`#0062E3`) border and subtle elevation shadow on selection.
2. **Campaign Details Section:**
   - **Campaign Title:** Single-line text input field (`e.g., Summer Getaway Offer`).
   - **Target URL:** URL input field with validation.
   - **Daily Budget:** Currency input selector (`$ USD`) with live daily reach estimator tooltip (`10k - 15k views`).
3. **Action Buttons:**
   - **Save & Continue:** Primary Skyscanner Sky Blue button (`#0062E3`).
   - **Save Draft:** Secondary text action button.

#### Value & Usability Risk Mitigation
- **Usability:** Card-based visual hierarchy eliminates complex form menus, enabling external advertisers to launch campaigns with zero onboarding support.
- **Feasibility:** Reuses standard Skyscanner Backpack UI components (`BpkCardView`, `BpkButton`, `BpkText`).

#### Acceptance Criteria
- [ ] User can click any of the 3 ad type cards to set the active ad mode.
- [ ] Selecting an ad type dynamically highlights the active card and displays corresponding input fields.
- [ ] Target URL field performs client-side URL validation.
- [ ] Daily budget input dynamically calculates and displays estimated daily reach.
- [ ] Form state persists when clicking "Save Draft".

---

## Ticket #2: Performance Tracking & Analytics Dashboard

* **Issue Key:** SKY-102
* **Issue Type:** Story
* **Project:** Skyscanner
* **Summary / Title:** Implement Real-Time Ad Performance Tracking & Analytics Dashboard
* **Reporter:** Anuj Yadav
* **Assignee:** Front-End Development Team
* **Priority:** High

### Description
> **As a developer, I would like to** build an intuitive analytics dashboard for external partners so that advertisers can monitor real-time campaign performance metrics, click-through rates (CTR), conversions, and total ad spend across all ad types.

#### Background & Product Goals
To address the value risk (proving ROI to external partners), this dashboard provides clear, visual telemetry on how active campaigns perform over custom date ranges.

#### Component & UI Specifications
1. **Left Navigation & Campaign List Sidebar:**
   - Navigation links: *Dashboard, Campaigns, Creatives, Reports, Settings*.
   - **My Campaigns List:** Quick status badges (`Active` green, `Paused` orange) for active campaigns (*Summer Getaways*, *Beach Resorts*, *City Breaks*).
2. **Top Metric Summary Cards (KPI Bar):**
   - **Total Impressions:** e.g., `1.2M` (+5.2% trend badge).
   - **Click-Through Rate (CTR):** e.g., `3.8%` (+0.5% trend badge).
   - **Conversions:** e.g., `4,500` (+8.1% trend badge).
   - **Total Spend:** e.g., `$12,400` (+3.7% trend badge).
3. **Main Analytics Visualizations:**
   - **Performance Overview Line Chart:** Interactive timeline comparing Impressions vs. Clicks over time with hover tooltips.
   - **Campaign Performance Comparison Bar Chart:** Comparative breakdown of Clicks, Conversions, and Spend grouped by Ad Type (Text Ad, Image & Text Ad, Video Ad).

#### Acceptance Criteria
- [ ] Metric summary cards display live aggregate statistics updated via API polling/WebSocket.
- [ ] Date picker dropdown filters line chart and bar chart data points dynamically.
- [ ] Hovering over chart data points displays interactive tooltip with exact impression/click figures.
- [ ] Clicking a campaign in the left sidebar filters the main dashboard metrics for that specific campaign.

---

## Ticket #3: Partner UX Feedback & Survey Portal

* **Issue Key:** SKY-103
* **Issue Type:** Story
* **Project:** Skyscanner
* **Summary / Title:** Implement Partner Feedback & Product Survey Interface
* **Reporter:** Anuj Yadav
* **Assignee:** Front-End Development Team
* **Priority:** Medium

### Description
> **As a developer, I would like to** create an embedded feedback and survey page within the partner portal so that product managers can gather direct UX feedback and identify feature improvement opportunities.

#### Background & Product Goals
Continuous feedback collection ensures long-term usability and feature feasibility alignment. This page presents 5 structured questions matching Skyscanner's brand aesthetic.

#### Component & UI Specifications
1. **Survey Structure (5 Questions):**
   - **Q1 (Satisfaction):** *"Overall, how satisfied are you with the Skyscanner Partner Portal?"* -> Interactive 1-5 Star Rating widget.
   - **Q2 (Ease of Navigation):** *"How easy is it to navigate and find the information you need?"* -> Interactive 1-5 Star Rating widget.
   - **Q3 (Most Used Section):** *"Which specific section of the portal do you use most frequently?"* -> Single-select pills (*Dashboard, Reporting, Booking Management, API Integration, Other*).
   - **Q4 (Desired Features):** *"What features or improvements would you like to see in future updates?"* -> Multi-select pills (*Faster Data Sync, Advanced Analytics, Better Documentation, More APIs, Other*).
   - **Q5 (Open Feedback):** *"Please share any additional comments or suggestions below."* -> Multi-line text area with 500-character limit.
2. **Submission Footer:**
   - Primary blue button: **Submit Feedback**.
   - Confirmation toast notification upon successful POST API submission.

#### Acceptance Criteria
- [ ] Star rating widgets handle hover and click selection states cleanly.
- [ ] Option pills highlight in active Sky Blue (`#0062E3`) when selected.
- [ ] Form submission validates required questions before sending payload.
- [ ] Submitting feedback posts JSON payload to `/api/v1/feedback` and displays success confirmation banner.
