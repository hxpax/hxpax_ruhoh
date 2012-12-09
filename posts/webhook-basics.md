---
title: About WebHook
date: '2012-12-08'
description:
categories:
---
<h4>Request Data</h4>
<p>In the POST parameters of the request Shopify passes along XML or JSON data with all of the order's details. Here is an example XML document that would be sent along with an order/* hook.<p>

<p>Don't assume this is exactly what is posted ... use the "test webhook" from the Shopify admin!</p>

<p>POST /your-path</p>
<p>Content-Type: application/xml</p>
<p><pre>
&lt?xml version="1.0" encoding="UTF-8"?&gt
&ltorder&gt
  &ltbuyer-accepts-marketing type="boolean"&gtfalse&lt/buyer-accepts-marketing&gt
  &ltcart-token nil="true"&gt&lt/cart-token&gt
  &ltclosed-at type="datetime" nil="true"&gt&lt/closed-at&gt
  &ltcreated-at type="datetime"&gt2005-07-31T15:57:11Z&lt/created-at&gt
  &ltcurrency&gtUSD&lt/currency&gt
  &ltemail&gtbob@customer.com&lt/email&gt
  &ltfinancial-status&gtpaid&lt/financial-status&gt
  &ltfulfillment-status nil="true"&gt&lt/fulfillment-status&gt
  &ltgateway&gtbogus&lt/gateway&gt
  &ltid type="integer"&gt516163746&lt/id&gt
  &ltnote nil="true"&gt&lt/note&gt
  &ltnumber type="integer"&gt1&lt/number&gt
  &ltshop-id type="integer"&gt820947126&lt/shop-id&gt
  &ltsubtotal-price type="integer"&gt10.00&lt/subtotal-price&gt
  &lttaxes-included type="boolean"&gtfalse&lt/taxes-included&gt
  &lttotal-discounts type="integer"&gt0.00&lt/total-discounts&gt
  &lttotal-line-items-price type="integer"&gt10.00&lt/total-line-items-price&gt
  &lttotal-price type="integer"&gt11.50&lt/total-price&gt
  &lttotal-tax type="integer"&gt1.50&lt/total-tax&gt
  &lttotal-weight type="integer"&gt0&lt/total-weight&gt
  &ltupdated-at type="datetime"&gt2005-08-01T15:57:11Z&lt/updated-at&gt
  &ltname&gt#1001&lt/name&gt
  &ltbilling-address&gt
    &ltaddress1&gt123 Amoebobacterieae St&lt/address1&gt
    &ltaddress2&gt&lt/address2&gt
    &ltcity&gtOttawa&lt/city&gt
    &ltcompany&gt&lt/company&gt
    &ltcountry&gtCanada&lt/country&gt
    &ltfirst-name&gtBob&lt/first-name&gt
    &ltid type="integer"&gt943494288&lt/id&gt
    &ltlast-name&gtBobsen&lt/last-name&gt
    &ltphone&gt(555)555-5555&lt/phone&gt
    &ltprovince&gtOntario&lt/province&gt
    &ltshop-id type="integer"&gt820947126&lt/shop-id&gt
    &ltzip&gtK2P0V6&lt/zip&gt
    &ltname&gtBob Bobsen&lt/name&gt
  &lt/billing-address&gt
  &ltshipping-address&gt
    &ltaddress1&gt123 Amoebobacterieae St&lt/address1&gt
    &ltaddress2&gt&lt/address2&gt
    &ltcity&gtOttawa&lt/city&gt
    &ltcompany&gt&lt/company&gt
    &ltcountry&gtCanada&lt/country&gt
    &ltfirst-name&gtBob&lt/first-name&gt
    &ltid type="integer"&gt943494288&lt/id&gt
    &ltlast-name&gtBobsen&lt/last-name&gt
    &ltphone&gt(555)555-5555&lt/phone&gt
    &ltprovince&gtOntario&lt/province&gt
    &ltshop-id type="integer"&gt820947126&lt/shop-id&gt
    &ltzip&gtK2P0V6&lt/zip&gt
    &ltname&gtBob Bobsen&lt/name&gt
  &lt/shipping-address&gt
  &ltline-items type="array"&gt
    &ltline-item&gt
      &ltfulfillment-service&gtmanual&lt/fulfillment-service&gt
      &ltgrams type="integer"&gt1500&lt/grams&gt
      &ltid type="integer"&gt642703538&lt/id&gt
      &ltprice type="integer"&gt10.00&lt/price&gt
      &ltquantity type="integer"&gt1&lt/quantity&gt
      &ltsku&gt1&lt/sku&gt
      &lttitle&gtDraft&lt/title&gt
      &ltvariant-id type="integer"&gt47052976&lt/variant-id&gt
      &ltvendor nil="true"&gt&lt/vendor&gt
      &ltname&gtDraft - 151cm&lt/name&gt
    &lt/line-item&gt
  &lt/line-items&gt
&lt/order&gt
</pre></p>

<h4>Headers</h4>
<p>Webhooks have some common headers that get sent out to help consumers:</p>
<ul>
<li>x-shopify-topic - Has the topic of the webhook (orders/create, products/create, etc.)</li>
<li>x-shopify-test - Set to true if the webhook was triggered by the test button in the admin</li>
<li>x-shopify-shop-domain - has the x.myshopify.com domain of the store where the webhook originated.</li>
</ul>
<p>Note that the application/uninstalled webhook does not send any data. You can get the shop it refers to from the appropriate header.</p>