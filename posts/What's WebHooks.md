---
title: What's WebHooks
date: '2012-12-07'
description: just copy and paste
tags: webhook
---
<p>WebHooks are a way to tell Shopify to call a script on one of your own web servers whenever a given event occurs and react in any way you want. They can be thought of as push notifications or event listeners.</p>
<p>Some possible uses for this feature include:</p>
<ul>
<li>Notify your IM client or your pager when you are offline</li>
<li>Collect data for data-warehousing</li>
<li>Integrate your accounting software</li>
<li>Filter the order items and inform various drop shippers about the order</li>
<li>Create license keys for software sales</li>
<li>Remove customer data from your database when they uninstall your app</li>
</ul>
<p>Please do note that you should not depend on webhooks for real-time push. The data you receive in a webhook may be delayed and out of date. For an authoritative snapshot of Shopify state, use the Shopify API.</p>