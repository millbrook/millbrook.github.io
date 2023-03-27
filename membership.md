---
layout: page
in_menu: true
title: Membership
---

Our community dues are **$25** per household annually, due on or before **March 1st** of each year. With the support of your dues, the civic association can accomplish many business requirements but in particular, your family benefits from the following:

-   SUMMER CONCERT
-   MAINTAIN OUR WEBSITE
-   ANNUAL BLOCK PARTY
-   MAINTAIN COMMUNITY GARDENS
-   STREET RE-PAVING
-   FUND SOUTH HS SCHOLARSHIP
-   LIAISE WITH MALL MANAGEMENT
-   PARTNER WITH LOCAL POLICE AND GOVERNMENT

Please feel free to click the **"Pay Dues"** button below to pay your dues using **PayPal**.

If you have any questions, please [Contact Us]({{ site.baseurl }}{% link contact-us.html %}) and address it to the Executive Board committee.

Thank you for your generosity. We appreciate your support!

{% raw %}

<div id="smart-button-container">
<div style="text-align: center;">
<div id="paypal-button-container"></div>
</div>
</div>
<script src="https://www.paypal.com/sdk/js?client-id=sb&enable-funding=venmo&currency=USD" data-sdk-integration-source="button-factory"></script>
<script>
function initPayPalButton() {
paypal.Buttons({
style: {
shape: 'rect',
color: 'blue',
layout: 'horizontal',
label: 'pay',

},

createOrder: function(data, actions) {
return actions.order.create({
purchase_units: [{"description":"Annual Membership Dues","amount":{"currency_code":"USD","value":25}}]
});
},

onApprove: function(data, actions) {
return actions.order.capture().then(function(orderData) {

// Full available details
console.log('Capture result', orderData, JSON.stringify(orderData, null, 2));

// Show a success message within this page, e.g.
const element = document.getElementById('paypal-button-container');
element.innerHTML = '';
element.innerHTML = '<h3>Thank you for your payment!</h3>';

// Or go to another URL:  actions.redirect('thank_you.html');

});
},

onError: function(err) {
console.log(err);
}
}).render('#paypal-button-container');
}
initPayPalButton();
</script>

{% endraw %}
