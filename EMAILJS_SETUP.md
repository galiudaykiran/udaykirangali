# EmailJS Setup Guide for Contact Form

## Overview
This portfolio website now includes EmailJS integration to send emails directly from the contact form to your email address (udaykirangali2@gmail.com) without requiring a backend server.

## Setup Instructions

### Step 1: Create EmailJS Account
1. Go to [EmailJS.com](https://www.emailjs.com/)
2. Sign up for a free account
3. Verify your email address

### Step 2: Create Email Service
1. In EmailJS dashboard, go to "Email Services"
2. Click "Add New Service"
3. Choose your email provider (Gmail, Outlook, etc.)
4. Follow the setup instructions for your provider
5. Note down your **Service ID** (e.g., "service_abc123")

### Step 3: Create Email Template
1. Go to "Email Templates"
2. Click "Create New Template"
3. Use this template content:

**Template ID**: `template_portfolio_contact`

**Subject**: `New Contact Form Message: {{subject}}`

**Content**:
```
Hello Udaykiran,

You have received a new message from your portfolio website:

Name: {{from_name}}
Email: {{from_email}}
Subject: {{subject}}

Message:
{{message}}

---
This message was sent from your portfolio contact form.
```

4. Save the template and note down the **Template ID**

### Step 4: Get Public Key
1. Go to "Account" → "General"
2. Copy your **Public Key** (e.g., "user_xyz789")

### Step 5: Update JavaScript Configuration
Open `script.js` and replace these placeholders:

```javascript
// Line 4: Replace with your Public Key
emailjs.init('YOUR_PUBLIC_KEY');

// Line 123: Replace with your Service ID and Template ID
emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', templateParams)
```

**Example:**
```javascript
emailjs.init('user_abc123def456');
emailjs.send('service_xyz789', 'template_portfolio_contact', templateParams)
```

### Step 6: Test the Contact Form
1. Open your portfolio website
2. Fill out the contact form
3. Submit the form
4. Check your email for the message

## Features Included

### ✅ **Email Functionality**
- Direct email sending from contact form
- Professional email templates
- Error handling and success notifications
- Loading states during email sending

### ✅ **User Experience**
- Real-time form validation
- Success/error notifications
- Loading spinner during submission
- Form reset after successful submission

### ✅ **Security**
- EmailJS handles security
- No sensitive data exposed
- Rate limiting included

## Troubleshooting

### Common Issues:

1. **"EmailJS is not defined" error**
   - Make sure EmailJS CDN is loaded
   - Check internet connection

2. **"Service not found" error**
   - Verify Service ID is correct
   - Ensure service is active in EmailJS dashboard

3. **"Template not found" error**
   - Verify Template ID is correct
   - Ensure template is published

4. **Emails not received**
   - Check spam folder
   - Verify email service configuration
   - Check EmailJS dashboard for logs

### Testing Steps:
1. Open browser developer tools (F12)
2. Go to Console tab
3. Submit contact form
4. Check for any error messages
5. Look for "SUCCESS!" or "FAILED..." messages

## EmailJS Limits (Free Plan)
- 200 emails per month
- 2 email services
- 2 email templates
- Perfect for portfolio websites

## Support
If you need help with EmailJS setup:
- EmailJS Documentation: https://www.emailjs.com/docs/
- EmailJS Support: support@emailjs.com

## Alternative: Mailto Fallback
If EmailJS doesn't work, the form will fall back to opening the user's email client with pre-filled content.

