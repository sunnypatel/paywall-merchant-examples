# AXO Payment Component

## Component definition

Defines what **does** this component do as part a Merchant's checkout flow.

- Provide Merchant with payment token (aka nonce)
- Allows Guest users to save their info for next time (remembered Guest flow)
- Allows Member users to add a new card to their **PayPal Wallet**

What the Payment component **does not** do:

- It **does not** handle 3DS for merchant
- It **does not** provide a PCI-Compliant form for the merchant, merchant is expected to BYOF (bring your own form :D ). This gives the merchant full control of their card fields.
