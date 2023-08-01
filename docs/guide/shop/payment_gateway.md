# Payment Gateways

> You need to create a payment gateway to accept payments.

| Attribute   | Description                                                                          |
|-------------|--------------------------------------------------------------------------------------|
| Name        | Name of gateway                                                                      |
| Subtitle    | Subtitle shown during checkout                                                       |
| Image URL   | [Optional] Image URL of the payment gateway. When no image is set, defaults are used |  
| Enabled     | Enable the payment gateway                                                           |
| Environment | Environment of gateway (Sandbox / Production)                                        |
| Secrets     | Secrets provided by payment providers                                                |

Please follow the instructions below to add a payment gateway.

## PayPal

`Supports recurring payments: yes`

> If you want to test the payments with a sandbox account first, do the steps below, but with a `SANDBOX` application.

1. Create a [PayPal Business](https://www.paypal.com/business) account or upgrade your account to a business account.
2. [Create a REST API app](https://developer.paypal.com/developer/applications/) in the PayPal Developer settings. Make
   sure to create the app for the `Live`
   environment.
3. Under `LIVE APP SETTINGS`, enable `Transaction Search`, disable the `Payouts` feature and click `Save`.
4. In your VyHub instance, create a PayPal payment gateway, select `PRODUCTION` environment and insert your `Client ID`
   and `Client Secret`.
5. Click `Create` and edit the payment gateway again. At the bottom, copy the `Webhook URL` to your clipboard.
6. Back in the `PayPal Developer` portal, click `Add Webhook` under `LIVE WEBHOOKS` and paste the copied URL.
7. Select `All events`, scroll down and click `Save`.
8. Copy the `Webhook ID` of the created webhook into the form and click `Edit`.

## Stripe

```
Supports recurring payments: yes
Supported Stripe API version: 2022-11-15 and older
```

> If you want to test the payments with a test account first, do the steps below, but with a `TEST` application.

1. [Create a Stripe account](https://dashboard.stripe.com/register) or log into your existing one.
2. In the Stripe `Developers` settings, navigate to `API keys`.
3. In your VyHub instance, create a Stripe payment gateway, insert your `Public Key` and `Private Key` and select your
   desired `Payment Methods`.
4. Click `Create` and edit the payment gateway again. At the bottom, copy the `Webhook URL` to your clipboard.
5. Back at the Stripe `Developers` settings, navigate to `Webhooks`.
6. Click `Add (hosted) endpoint` abd insert the copied URL to `Endpoint URL`. Add the following events and
   click `Add endpoint`:

    - `checkout.session.completed`
    - `invoice.paid`
    - `customer.subscription.deleted`

7. Click `Reveal` on the `Signing Secret` and copy it to your clipboard.
8. Back at the VyHub settings of your Stripe gateway, insert the copied secret into the `Webhook Secret` field and
   click `Edit`.
9. (Optional) In the `Stripe` settings of the created webhook endpoint, click `Send test event` to test if everything
   works fine.
10. (Optional) In the settings of the payment gateway, enable `Accept pending payments` to enable fast payment
    processing for the Stripe payment gateways that take several hours/days until a payment is finished.

## Paysafecard

`Supports recurring payments: no`

> This are the instructions to become an official paysafecard partner. You can also create a payment gateway with manual
> code confirmation with a `Coupon` gateway (see below).

1. [Become a paysafecard partner](https://www.paysafecard.com/become-a-partner/).
2. In your VyHub instance, create a Paysafecard payment gateway, insert your `API Key` and select your
   desired `Environment`.
3. Click `Create`.
4. As no IP addresses can be whitelisted, ask paysafecard to give you a cryptographic certificate for authentification.
   The private key (`Client Key`) and certificate (`Client Certificate`) can be set in the payment gateway settings.
   The `Client Certificate` is usually in a file named something
   like `001_manXXXXXXXXXX_XXXXXXXX_distributor_paysafecard_com.crt`.

## Credits

`Supports recurring payments: no`

1. In your VyHub instance, create a credits payment gateway.

Create packets that have `Credits` as reward, so that users can buy credits with real money. You will need another
payment gateway for this.

> Credits can be renamed with a name that matches your community (gulden, diamonds, ...). Rename in the `general-shop` settings.

## Coupon

`Supports recurring payments: no`

> Coupon gateways can be used to manually approve coupons (e.g. paysafecard pins)

1. In your VyHub instance, create a coupon payment gateway.
2. After a purchase is made and coupons are entered by the user, the coupons need to be approved under
   the `confirm purchases` tab on the `shop admin` page.

## Free

`Supports recurring payments: no`

The `Free` payment gateway is an internal construct. It always exists, can't be deleted and no other payment gateways
can be created with this type.

The `Free` payment gateway appears as payment option whenever the total amount to pay is zero. This can happen if a 100%
discount has been applied.
