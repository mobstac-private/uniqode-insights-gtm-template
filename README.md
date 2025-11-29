# Uniqode Insights Pixel – Google Tag Manager Template

This repository contains the official **Google Tag Manager (GTM) Custom Template** for **Uniqode Insights Pixel**, enabling you to track post-scan engagement and conversions from Uniqode QR Code campaigns.

The template provides a secure and sandboxed way to load the Uniqode Insights SDK and initialize tracking using Google Tag Manager.

---

## 🔧 Features

- One-click installation via Google Tag Manager Community Gallery
- Secure loading of the Uniqode Insights SDK
- Automatic initialization using your Pixel (Insight) ID
- Event queuing until the SDK is fully loaded
- Fully sandboxed using the GTM Template API
- Minimal and clearly scoped permissions

---

## 🚀 How It Works

When the tag fires:

1. The template checks for an existing `window.insights` object
2. If not present, a stub is created and API calls are queued
3. The Uniqode Insights SDK is loaded from Uniqode’s CDN
4. The SDK is initialized using your **Pixel ID**
5. Any queued events are processed once the SDK is ready

If the SDK fails to load, the tag fails gracefully without breaking your GTM container.

---

## 📦 Installation

1. Open **Google Tag Manager**
2. Go to **Templates → Search Gallery**
3. Search for **Uniqode Pixel**
4. Add the template to your container
5. Create a new tag using the template
6. Enter your **Pixel ID**
7. Configure a trigger (e.g., All Pages)
8. Publish your container

---

## ⚙️ Configuration

### Pixel ID (Insight ID)

This is your unique Uniqode Insights identifier used to associate events and engagement data with your Uniqode account.

You can find this ID in your Uniqode dashboard -> Insight section.

---

## 🔐 Permissions & Security

This template requires the following permissions:

### Inject Scripts
- **Domain:** `https://cdn.uniqode.com`
- **Reason:** Required to load the Uniqode Insights JavaScript SDK used for analytics and engagement tracking.

### Access Global Variables
- **Variable:** `window.insights`
- **Access:** Read & Write
- **Reason:** The SDK exposes a global `insights` object used for initialization and event tracking.

**No other global variables are accessed.**  
**No remote code execution or dynamic script URLs are used.**

---

## 📊 Data Collected

Depending on your Uniqode Insights configuration, the SDK may collect and send:

- Pixel (Insight) ID
- Event names and metadata
- Device and browser information
- Engagement and conversion signals

This template itself does **not** store cookies or persist personal data directly.

---

## 🔒 Privacy & Compliance

You are responsible for ensuring that your use of this template complies with applicable privacy regulations such as **GDPR**, **CCPA**, and local data-protection laws.

If required, obtain user consent before firing this tag.

---

## 🛠 Repository Contents

- `template.tpl` — GTM custom template definition
- `metadata.yaml` — Required metadata for Community Gallery submission
- `gallery/`
  - `icon.png` — 512×512 template icon
  - `screenshot.png` — Tag configuration screenshot
- `README.md` — Documentation
- `LICENSE` — Apache 2.0

---

## 🧪 Testing

This template includes automated GTM template tests covering:
- Successful SDK loading
- SDK load failure handling
- Reuse of an existing `window.insights` object

---

## 📄 License

Apache License 2.0

---

## 📝 Community Template Gallery Submission

This template is designed to meet the requirements of the **Google Tag Manager Community Template Gallery**.

Submission guide:  
https://tagmanager.google.com/gallery/getting-started

---

## 📬 Support

For product support or questions related to Uniqode Insights, please contact Uniqode support through our dashboard at https://dashboard.uniqode.com or directly mail us at [support@uniqode.com](mailto:support@uniqode.com).

> This GitHub repository serves as the official homepage and documentation for this template.
