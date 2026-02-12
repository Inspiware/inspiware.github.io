# Contact Form Setup Guide

## Overview
The contact form on `contact.html` is configured to send submissions to **sales@inspiware.co.uk** using Formspree, a free form backend service for static websites.

## How It Works

1. **Form Submission**: When a user fills out the contact form and clicks "Send Message", the form data is submitted to Formspree
2. **Email Delivery**: Formspree processes the submission and forwards it to sales@inspiware.co.uk
3. **User Feedback**: The user sees a success or error message on the page

## Setup Required

### Step 1: Create a Formspree Account (One-time setup)

1. Go to [https://formspree.io](https://formspree.io)
2. Sign up for a free account using the **sales@inspiware.co.uk** email address
3. Verify your email address

### Step 2: Create a New Form

1. Log in to your Formspree dashboard
2. Click "New Form" or "Create Form"
3. Give it a name like "Inspiware Contact Form"
4. You'll receive a unique form endpoint that looks like: `https://formspree.io/f/xwpkwbka`

### Step 3: Update the Form Action (if needed)

The current form is configured with a placeholder endpoint. Once you have your actual Formspree endpoint:

1. Open `contact.html`
2. Find line 110: `<form id="contactForm" action="https://formspree.io/f/xwpkwbka" method="POST">`
3. Replace `xwpkwbka` with your actual form ID from Formspree

### Step 4: Configure Email Settings in Formspree

In your Formspree dashboard, you can configure:
- **Email notifications**: Ensure sales@inspiware.co.uk receives notifications
- **Auto-reply**: Set up an automatic reply to users who submit the form
- **Spam protection**: Enable reCAPTCHA if needed
- **Submission storage**: View all submissions in the dashboard

## Form Fields

The contact form collects:
- **Full Name** (required)
- **Email Address** (required)
- **Company** (optional)
- **Inquiry Type** (dropdown: Product Demo, Pricing, Support, Partnership, General)
- **Message** (required)

## Features

✅ **Email forwarding** to sales@inspiware.co.uk
✅ **User-friendly feedback** with success/error messages
✅ **Form validation** for required fields
✅ **Responsive design** works on all devices
✅ **Loading state** shows "Sending..." while submitting
✅ **Spam protection** via Formspree's built-in filters

## Free Tier Limits

Formspree's free tier includes:
- 50 submissions per month
- Unlimited forms
- Email notifications
- Spam filtering
- Submission archive

If you need more submissions, you can upgrade to a paid plan.

## Alternative Solutions

If you prefer not to use Formspree, here are alternatives:

1. **Web3Forms** - Similar service, also free tier available
2. **EmailJS** - Client-side email service
3. **Netlify Forms** - If you migrate to Netlify hosting
4. **Custom Backend** - Build your own API endpoint

## Testing

To test the form:
1. Open `contact.html` in a browser
2. Fill out all required fields
3. Click "Send Message"
4. Check sales@inspiware.co.uk for the email
5. Verify the success message appears on the page

## Troubleshooting

**Form not sending?**
- Check that the Formspree endpoint is correct
- Verify your Formspree account is active
- Check browser console for errors

**Not receiving emails?**
- Check spam folder
- Verify email address in Formspree dashboard
- Ensure email notifications are enabled in Formspree settings

**Error message showing?**
- Check internet connection
- Verify Formspree service is online
- Check browser console for specific error details

## Support

For Formspree support: [https://help.formspree.io](https://help.formspree.io)

