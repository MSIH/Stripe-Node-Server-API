# Stripe API Node Application
Node application to process [Stripe API](https://stripe.com/docs/api), also works as a serverless application using [WebTask.io](https://webtask.io/)

### Looking for contributors

## To install in webtask use the following:
1. npm install wt-cli -g
2. wt init
3. wt create filename.js --secret stripeSecretKey=StripeSecret (do not use quotes or brackets!)

## Stripe API Resourse as of 20170328 (completed by and when)
* Balance (MSIH 20170328)
* Charge (MSIH 20170328)
* Customers (MSIH 20170328)
* Disputes (MSIH 20170328)
* Events
* File Uploads
* Refunds
* Tokens
* Transfers
* Transfer Reverals
* Account
* Application Fee Refunds
* Application Fees
* Receipts
* Country Specs
* External Accounts
* Alipay
* Bank
* Cards (MSIH 20170328)
* Sources
* Orders
* Order items
* Returns
* Products
* SKUs
* Coupons
* Discounts
* Invoices
* Invoice items
* Plans
* Subscriptions (MSIH 20170328)
* Subscription items

# Usage

## Javascript AJAX

### Create Charge (https://stripe.com/docs/api/node#create_charge)
```javascript
$.ajax({
    type: 'POST',
    url: 'https://hostname/charge/create',    
    data: {
        amount: 2000, //required
        currency: USD, //required
        capture: true,
        description: "description",
        metadata: {key: "value"},
        receipt_email: "some@person.com",
        customer: "CustomerId", //one of these 
        source: "tok_1A39MDLH9uqNfEWzeK1CZenj", // obtained with Stripe.js  //are required
        statement_descriptor: "You just got a frog"
    },
    success: (response) => {
      console.log(JSON.stringify(response));
    },
    error: (error) => {
      console.log(JSON.stringify(error));
    }
  })
```  
### Create Customer
```javascript
$.ajax({
    type: 'POST',
    url: 'https://hostname/customer/create',    
    data: {
      source: "tok_1A39MDLH9uqNfEWzeK1CZenj", // obtained with Stripe.js
      business_vat_id: "123456789",
      coupon: CouponId,
      description: "You just got a frog",
      email: "some@person.com",
      metadata: {key: "value"}
    },
    success: (response) => {
      console.log(JSON.stringify(response));
    },
    error: (error) => {
      console.log(JSON.stringify(error));
    }
  })
```  

mark down cheat sheet (https://guides.github.com/features/mastering-markdown/)
