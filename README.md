# Accessibility Toolbar (Custom Version)

A customized version of the [MicAccessTool Accessibility Toolbar](https://github.com/mickidum/acc_toolbar) with added support for Greek and automatic language detection based on the website’s `<html lang="">` attribute.

Hosted and maintained by [@captaingreek](https://github.com/captaingreek).

---

## ✨ Features

- ✅ Supports English (`en-US`) and Greek (`el-GR`)
- 🌐 Automatically selects language based on the site’s language (`<html lang="...">`)
- 📁 Self-hosted — no reliance on external CDNs
- 🧩 Easy to integrate into any website

---

## 🚀 Installation

Include the modified script on your site:

```html
<script src="https://yourdomain.com/toolbox/acctoolbar.min.js"></script>
<script>
  window.onload = function() {
    const siteLangRaw = document.documentElement.lang || navigator.language || 'en';
    const siteLang = siteLangRaw.toLowerCase();

    const langMap = {
      'en': 'en-US',
      'he': 'he-IL',
      'el': 'el-GR'
    };

    const forceLang = langMap[siteLang] || 'en-US';

    window.micAccessTool = new MicAccessTool({
      link: 'https://yourdomain.com/accessibility-declaration.pdf',
      contact: 'mailto:your@email.com',
      buttonPosition: 'right',
      forceLang: forceLang
    });
  };
</script>
