# Merchant using their own card fields

Shows an example of a merchant who wants to use their own PCI compliant Card fields and our AXO Payment component.

## Roles & Responsibilities

AXO Payment component - Responsible for returning a BT nonce to Merchant. Merchant will use this nonce to process the transaction in their backend.

## Usage

Merchants' usage of our AXO Payment component

```javascript
<html>
  <head>
    <title>Adorama - Checkout</title>

    <!-- Script load AXO components from somewhere -->
    <script
      type="module"
      src="https://{some-paypal-cdn}/components/bundle.min.js"
    ></script>
  </head>

  <body>
    <section name="payment">
      <paypal-payment id="paypalPaymentComp" token="some-buyer-access-token">
        <slot name="card-fields">
            <form action="/" id="my-sample-form" method="post">
                <label for="card-number">Card Number</label>
                <div id="card-number"></div>

                <label for="cvv">CVV</label>
                <div id="cvv"></div>

                <label for="expiration-date">Expiration Date</label>
                <div id="expiration-date"></div>
                <input type="submit" value="Pay" disabled />
            </form>
        </slot>
      </paypal-payment>
    </section>
  </body>

  <script>
    const paymentComponent = document.querySelector('paypalPaymentComp');

    paymentComponent.addEventListener('onPaymentToken', ({ paymentToken, errors }) => {
      /**
       * Merchant code here.
       * Merchant should first check if we returned them any errors,
       * if no errors then did we pass them a paymentToken,
       * if so then use paymentToken to process on their backend
       */
    });
  </script>
</html>
```

## Questions
