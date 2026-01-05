# EmailJS Setup Guide

## Why the Gmail API Error?

The error "412Gmail_API: Request had insufficient authentication scopes" occurs when trying to use Gmail API directly. EmailJS works differently - it uses its own email service or SMTP, not Gmail API.

## Setup Steps

### 1. Create EmailJS Account
1. Go to https://www.emailjs.com/
2. Sign up for a free account
3. Verify your email address

### 2. Add Email Service (NOT Gmail API)

**Option A: Use EmailJS Email Service (Recommended - Easiest)**
1. Go to **Email Services** in your EmailJS dashboard
2. Click **Add New Service**
3. Select **EmailJS** (not Gmail API)
4. This gives you a free email service with 200 emails/month
5. Copy your **Service ID**

**Option B: Use SMTP (Gmail, Outlook, etc.)**
1. Go to **Email Services** → **Add New Service**
2. Select **Gmail** (SMTP, not Gmail API)
3. Enter your Gmail credentials
4. This uses SMTP, not OAuth, so no scope issues
5. Copy your **Service ID**

### 3. Create Email Template
1. Go to **Email Templates** in EmailJS dashboard
2. Click **Create New Template**
3. Use this template structure:

**Subject:** New Assessment Request from {{from_name}}

**Content:**
```
Name: {{from_name}}
Email: {{from_email}}
Company: {{company}}
Service Interest: {{service_interest}}

Message:
{{message}}
```

4. Save and copy your **Template ID**

### 4. Get Your Public Key
1. Go to **Account** → **General**
2. Find your **Public Key**
3. Copy it

### 5. Update the Code

Replace these placeholders in `index.html`:

1. **Line ~28:** Replace `YOUR_PUBLIC_KEY` with your EmailJS Public Key
2. **Line ~2227:** Replace `YOUR_SERVICE_ID` with your Service ID
3. **Line ~2227:** Replace `YOUR_TEMPLATE_ID` with your Template ID

Example:
```javascript
emailjs.init("abc123xyz"); // Your Public Key

// In the send function:
emailjs.send('service_abc123', 'template_xyz789', templateParams)
```

## Important Notes

- **Don't use Gmail API** - Use EmailJS service or SMTP instead
- **Free tier:** 200 emails/month
- **Public Key is safe** - It's meant to be public in your frontend code
- **Service ID and Template ID** are also safe to expose in frontend code

## Testing

1. Fill out the contact form on your site
2. Submit it
3. Check your email (the email address you configured in the service)
4. Check EmailJS dashboard → **Logs** to see if emails were sent

## Troubleshooting

- **Still getting errors?** Make sure you're using EmailJS service or SMTP, not Gmail API
- **Emails not arriving?** Check EmailJS dashboard logs
- **Rate limits?** Free tier is 200 emails/month

