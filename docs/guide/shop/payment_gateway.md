
# Payment Gateways

> You need to create a payment gateway to accept payments.

| Attribute   | Description                                   |
|-------------|-----------------------------------------------|
| Name        | Name of gateway                               |
| Subtitle    | Subtitle shown during checkout                |
| Enabled     | Enable the payment gateway                    |
| Environment | Environment of gateway (Sandbox / Production) |
| Secrets     | Secrets provided by payment providers         |

Please follow the instructions below to add a payment gateway.

## PayPal

> If you want to test the payments with a sandbox account first, do the steps below, but with a `SANDBOX` application.

1. Create a [PayPal Business](https://www.paypal.com/business) account or upgrade your account to a business account.
2. [Create a REST API app](https://developer.paypal.com/developer/applications/) in the PayPal Developer settings. Make sure to create the app for the `Live`
 environment.
3. Under `LIVE APP SETTINGS`, disable the `Payouts` feature and click `Save`.
4. In your VyHub instance, create a PayPal payment gateway, select `PRODUCTION` environment and insert your `Client ID` and `Client Secret`.
5. Click `Create`.

## Stripe

> If you want to test the payments with a test account first, do the steps below, but with a `TEST` application.

1. [Create a Stripe account](https://dashboard.stripe.com/register) or log into your existing one.
2. In the Stripe `Developers` settings, navigate to `API keys`.
3. In your VyHub instance, create a Stripe payment gateway, insert your `Public Key` and `Private Key` and select your desired `Payment Methods`.
4. Click save and edit the payment gateway again. At the bottom, copy the `Webhook URL` to your clipboard.
5. Back at the Stripe `Developers` settings, navigate to `Webhooks`.
6. Click `Add (hosted) endpoint`, insert the copied URL to `Endpoint URL` and select `Latest API version`. Add the following events and click `Add endpoint`:

    - `checkout.session.completed`
    - `invoice.paid`
    - `customer.subscription.deleted`

7. Click `Reveal` on the `Signing Secret` and copy it to your clipboard.
8. Back at the VyHub settings of your Stripe gateway, insert the copied secret into the `Webhook Secret` field and click `Edit`.
9. (Optional) In the `Stripe` settings of the created webhook endpoint, click `Send test event` to test if everything works fine.

## Paysafecard

1. [Become a paysafecard partner](https://www.paysafecard.com/become-a-partner/).
2. In your VyHub instance, create a Paysafecard payment gateway, insert your `Secret Key` and select your desired `Environment`.
3. Click `Create`.

## Credits

1. In your VyHub instance, create a credits payment gateway.

Create packets that have `Credits` as reward, so that users can buy credits with real money. You will need an other payment gateway for this.

## Coupons

> Coupon gateways can be used to manually approve coupons (e.g. paysafecard pins)

1. In your VyHub instance, create a coupon payment gateway.
2. After a purchase is made and coupons are entered by the user, the coupons need to be approved under the `confirm purchases` tab on the `shop admin` page. 
