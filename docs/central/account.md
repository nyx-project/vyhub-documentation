# VyHub Balance and Pricing

This article is about the pricing of VyHub instances and how payments are settled.

## Pricing of VyHub

Every VyHub instance is free to use, but a small 3-6% commission is charged on your revenue. So you only pay for VyHub,
when you make money.

<sub>Local currencies are converted to EUR on a daily basis.</sub>

| Percentage | Monthly revenue through VyHub instance |
|------------|----------------------------------------|
| 6%         | 0€ - 250€                              |
| 5%         | 250€ - 2500€                           |
| 4%         | 2500€ - 5000€                          |
| 3%         | 5000€ -   ∞                            |

<sub>*Different conditions for major communities available. Please contact our sales team with a short overview about
your community.</sub>

### Example Revenues

You will not pay for VyHub, unless you make some money.  
The more you earn, the more you save on fees.

| Revenue generated through VyHub | Formula                                         | Total to pay | Comparable competitor* |
|---------------------------------|-------------------------------------------------|--------------|------------------------|
| 0€                              | -                                               | 0.00€        | 14.00€                 |
| 300€                            | 250€ * 6% + 50€ * 5%                            | 17.50€       | 29.00€                 |
| 7000€                           | 250€ * 6% + 2250 * 5% + 2500€ * 4% + 2000€ * 3% | 278.00€      | 364.00€                |

<sub>Comparable competitor with a 5% commission and extra cost for SSL-Certificate and domain.</sub>

## Optional Paid Add-Ons

Certain VyHub features like the [forum](../guide/forum.md) are paid.

The add-ons can be purchased in the central instance
dashboard [https://vyhub.net/dashboard](https://vyhub.net/dashboard). There you find all available add-ons and the
current prices.

### Cancel Add-Ons

Every add-on can be cancelled by you at the end of every billing cycle.   
Cancelling is as well done through the central instance
dashboard [https://vyhub.net/dashboard](https://vyhub.net/dashboard).

## Payment of your Instance

During the month, the revenue of your instance is collected and reflected on
your [VyHub balance](https://vyhub.net/account).  
At the end of the month, a invoice will be created which is either paid by your current balance (if positive) or charged
automatically through PayPal or Stripe.

### Recommended: Auto Charge

We recommend you setting up auto charge. With auto charge you will never forget to top up your balance.

At the beginning of each month you will receive an email about your outstanding balance. The balance will then be
collected through your payment method.

**Supported Payment Methods**

- PayPal
- Stripe

> The minium auto charge is 5€. Your positive balance will be used to settle the balance of the following months.

#### Example Charge Cycle

| Month   | Monthly Bill | Balance before charge | Charge Up | Balance after charge |
|---------|--------------|-----------------------|-----------|----------------------|
| Month 1 | -3€          | 0€                    | 5€        | 2€                   |
| Month 2 | -1€          | 2€                    | 0€        | 1€                   |
| Month 3 | -8€          | 1€                    | 7€        | 0€                   |

#### Setting up Auto Charge

Your VyHub Balance is positive (>=0€)? You can set-up Auto Charge **without** any set-up fee.

Your VyHub Balance is negative (<=0€)? You will be charged a set-up fee which reflects your current balance but is at
least 5€.

| Balance before Set-Up | Set-Up Fee | Balance after Set-Up |  
|-----------------------|------------|----------------------|
| 0€                    | 0€         | 0€                   | 
| 6€                    | 0€         | 0€                   | 
| -2€                   | 5€         | 3€                   | 
| -7€                   | 7€         | 0€                   | 

### Prepaid

You can manually top up your VyHub Balance.

> The minimum top up is 5€. Your positive balance will be used to settle the balance of the following months.

At the beginning of each month you will receive an email about your outstanding balance. The balance must be topped up,
otherwise the instance will be stopped.

**Supported Payment Methods**

- PayPal
- Stripe
- Paysafecard

### Outstanding Balance

If you have got outstanding payments and your VyHub balance is still negative, all your instances will be stopped. You can reactivate
them after you have settled the balance.

> We point out that accumulated debts must be settled in accordance with our terms and conditions in any case. <br>


#### Auto Charge

| Event                                                    | When?                                    |
|----------------------------------------------------------|------------------------------------------|
| Email: Balance Overview                                  | Beginning of next billing period         |
| Email: Payment Reminder with option to recharge manually | Automatic charge failed                  |
| Shutdown of Instance                                     | Balance still negative, user did not pay |

#### Prepaid:

| Event                   | When?                                    |
|-------------------------|------------------------------------------|
| Email: Balance Overview | Beginning of next billing period         |
| Email: Payment Reminder | Balance negative, no top-up detected     |
| Shutdown of Instance    | Balance still negative, user did not pay |

### Payout of VyHub Balance

A payout of your VyHub balance is not possible.


