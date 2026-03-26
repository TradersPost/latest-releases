# October 4th, 2022

## Improvements

Things have been a little quiet the last few months, but we've been actively working on some infrastructure improvements that are mostly invisible to the end user. We made some changes to separate our application onto subdomains to give us more future flexibility.

{% embed url="https://www.youtube.com/watch?v=t72FAOcTERo" %}
TradersPost Webhook URL Changes
{% endembed %}

### Webhook URL

Webhooks now live on the subdomain **webhooks.traderspost.io**. All you need to do to switch is change **traderspost.io** to **webhooks.traderspost.io** in your webhooks.

{% hint style="success" %}
Don't worry, the old URLs will still work until a date in the future which we will announce with plenty of time for you to change.
{% endhint %}

### **Application URL**

The main application has moved to be hosted on **app.traderspost.io**. No change is required for you and all links are updated and redirected to the new subdomain.
