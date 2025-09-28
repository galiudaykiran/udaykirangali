# QUICK EMAILJS SETUP - Get Emails Working in 5 Minutes!

## 🚀 Step-by-Step Setup:

### Step 1: Create EmailJS Account
1. Go to: https://www.emailjs.com/
2. Click "Sign Up" (it's free)
3. Use your email: udaykirangali2@gmail.com
4. Verify your email address

### Step 2: Add Email Service
1. In EmailJS dashboard, click "Email Services"
2. Click "Add New Service"
3. Choose "Gmail" (or your email provider)
4. Click "Connect Account"
5. Sign in with udaykirangali2@gmail.com
6. Copy the Service ID (looks like: service_abc123)

### Step 3: Create Email Template
1. Click "Email Templates"
2. Click "Create New Template"
3. Use these settings:

**Template Name**: Portfolio Contact Form
**Subject**: New Message from Portfolio: {{subject}}
**Content**:
```
Hello Udaykiran,

You received a new message from your portfolio website:

Name: {{from_name}}
Email: {{from_email}}
Subject: {{subject}}

Message:
{{message}}

---
Sent from your portfolio contact form.
```

4. Click "Save"
5. Copy the Template ID (looks like: template_xyz789)

### Step 4: Get Public Key
1. Go to "Account" → "General"
2. Copy your Public Key (looks like: user_def456)

### Step 5: Update Your Code
Open `script.js` and replace these lines:

**Line 4:**
```javascript
emailjs.init('YOUR_PUBLIC_KEY');
```
Replace with:
```javascript
emailjs.init('user_def456'); // Your actual public key
```

**Line 123:**
```javascript
emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', templateParams)
```
Replace with:
```javascript
emailjs.send('service_abc123', 'template_xyz789', templateParams)
```

### Step 6: Test
1. Open your portfolio website
2. Fill out contact form
3. Submit
4. Check your email!

## 🔧 Alternative: Use Formspree (Even Easier!)

If EmailJS seems complicated, I can set up Formspree instead - it's even simpler!

## 🆘 Need Help?
If you're still having issues, let me know and I'll:
1. Set up Formspree instead (easier)
2. Create a PHP backend solution
3. Use Netlify Forms
4. Help debug the EmailJS setup

## Current Status:
❌ EmailJS not configured (placeholders still in code)
✅ Code is ready to work once configured
✅ Fallback mailto is working

