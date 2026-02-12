# Calendly Integration Setup Guide

## Overview
The "Schedule a Demo" buttons on the website are configured to open a Calendly booking widget, allowing visitors to schedule demo meetings directly.

## How It Works

1. **User clicks "Schedule a Demo"** button
2. **Calendly popup opens** with your booking calendar
3. **User selects a time** that works for them
4. **Confirmation emails** are sent to both parties
5. **Calendar invites** are automatically created

## Setup Required

### Step 1: Create a Calendly Account (One-time setup)

1. Go to [https://calendly.com](https://calendly.com)
2. Sign up for a free account (or use an existing one)
3. Use your Inspiware email address (e.g., sales@inspiware.co.uk or your personal work email)

### Step 2: Create an Event Type

1. Log in to your Calendly dashboard
2. Click "Create" → "Event Type"
3. Choose "One-on-One" meeting type
4. Configure the event:
   - **Event name**: "TeX Platform Demo" or "Product Demo"
   - **Duration**: 30 minutes (or your preferred length)
   - **Location**: Add Zoom, Google Meet, Microsoft Teams, or phone
   - **Description**: Add details about what the demo will cover

### Step 3: Get Your Calendly URL

1. After creating the event, you'll get a URL like:
   - `https://calendly.com/your-username/demo`
   - Or `https://calendly.com/inspiware/demo`

2. Copy this URL

### Step 4: Update the Website

The website is currently configured with a placeholder URL: `https://calendly.com/inspiware/demo`

To update it with your actual Calendly URL:

1. Open `index.html`
2. Find the two instances (around lines 772 and 1575):
   ```html
   onclick="Calendly.initPopupWidget({url: 'https://calendly.com/inspiware/demo'});return false;"
   ```
3. Replace `https://calendly.com/inspiware/demo` with your actual Calendly URL

### Step 5: Configure Calendly Settings

In your Calendly dashboard, configure:

**Availability**
- Set your working hours
- Add buffer time between meetings
- Set minimum scheduling notice (e.g., 24 hours)

**Notifications**
- Email confirmations to you and the invitee
- Email reminders before the meeting
- SMS reminders (optional, paid feature)

**Questions**
- Add custom questions to collect information:
  - Company name
  - Number of employees
  - Specific interests (AI features, banking compliance, etc.)
  - Current integration challenges

**Branding** (Paid feature)
- Add Inspiware logo
- Customize colors to match brand
- Remove Calendly branding

## Features

✅ **Automatic scheduling** - No back-and-forth emails  
✅ **Calendar sync** - Integrates with Google, Outlook, Office 365  
✅ **Time zone detection** - Automatically shows correct times  
✅ **Email confirmations** - Sent to both parties  
✅ **Reminders** - Reduces no-shows  
✅ **Rescheduling** - Easy for invitees to reschedule  
✅ **Cancellation** - Automated cancellation handling  
✅ **Popup widget** - Smooth user experience without leaving the page  

## Free Tier Limits

Calendly's free tier includes:
- 1 event type
- Unlimited meetings
- Calendar integrations
- Email notifications
- Basic customization

For more features (multiple event types, team scheduling, custom branding), upgrade to a paid plan.

## Customization Options

You can customize the popup behavior by modifying the JavaScript:

```javascript
// Basic popup
Calendly.initPopupWidget({url: 'https://calendly.com/inspiware/demo'});

// With prefilled information
Calendly.initPopupWidget({
  url: 'https://calendly.com/inspiware/demo',
  prefill: {
    name: 'John Doe',
    email: 'john@example.com',
    customAnswers: {
      a1: 'Enterprise'
    }
  }
});

// With UTM parameters for tracking
Calendly.initPopupWidget({
  url: 'https://calendly.com/inspiware/demo',
  utm: {
    utmSource: 'website',
    utmMedium: 'cta_button',
    utmCampaign: 'tex_platform'
  }
});
```

## Testing

To test the integration:
1. Open `index.html` in a browser
2. Click "Schedule a Demo" button
3. Verify the Calendly popup opens
4. Try booking a test meeting
5. Check that confirmation emails are received

## Troubleshooting

**Popup not opening?**
- Check browser console for JavaScript errors
- Verify Calendly scripts are loading (check Network tab)
- Ensure popup blockers are disabled

**Wrong calendar showing?**
- Verify the Calendly URL is correct
- Check that the event type is active in Calendly dashboard

**Not receiving notifications?**
- Check spam folder
- Verify notification settings in Calendly
- Ensure email address is verified

## Alternative: Inline Embed

If you prefer an embedded calendar instead of a popup, you can use:

```html
<!-- Add to your page -->
<div class="calendly-inline-widget" 
     data-url="https://calendly.com/inspiware/demo" 
     style="min-width:320px;height:630px;">
</div>
```

## Support

For Calendly support: [https://help.calendly.com](https://help.calendly.com)

## Current Implementation

The website has two "Schedule a Demo" buttons:
1. **Hero section** (top of page) - Primary CTA
2. **Contact section** (bottom of page) - Secondary CTA

Both open the same Calendly booking widget for consistency.

