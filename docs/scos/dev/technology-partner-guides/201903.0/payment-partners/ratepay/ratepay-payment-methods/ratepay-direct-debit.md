---
title: RatePay - Direct Debit
description: Integrate direct debit payment through Ratepay into the Spryker-based shop.
last_updated: Jul 31, 2020
template: concept-topic-template
originalLink: https://documentation.spryker.com/v2/docs/ratepay-direct-debit
originalArticleId: 78d2d504-bf73-4aef-b5dd-85993d4e004b
redirect_from:
  - /v2/docs/ratepay-direct-debit
  - /v2/docs/en/ratepay-direct-debit
  - /docs/scos/user/technology-partners/201903.0/payment-partners/ratepay/ratepay-payment-methods/ratepay-direct-debit.html
related:
  - title: RatePay
    link: docs/scos/user/technology-partners/page.version/payment-partners/ratepay.html
  - title: RatePay - Payment Workflow
    link: docs/scos/dev/technology-partner-guides/page.version/payment-partners/ratepay/technical-details-and-howtos/ratepay-payment-workflow.html
  - title: RatePay - Facade
    link: docs/scos/dev/technology-partner-guides/page.version/payment-partners/ratepay/technical-details-and-howtos/ratepay-facade.html
  - title: Disabling address updates from the backend application for RatePay
    link: docs/scos/dev/technology-partner-guides/page.version/payment-partners/ratepay/technical-details-and-howtos/disabling-address-updates-from-the-backend-application-for-ratepay.html
  - title: RatePay - Invoice
    link: docs/scos/dev/technology-partner-guides/page.version/payment-partners/ratepay/ratepay-payment-methods/ratepay-invoice.html
  - title: RatePay- Core Module Structure Diagram
    link: docs/scos/dev/technology-partner-guides/page.version/payment-partners/ratepay/ratepay-core-module-structure-diagram.html
  - title: RatePay - Installment
    link: docs/scos/dev/technology-partner-guides/page.version/payment-partners/ratepay/ratepay-payment-methods/ratepay-installment.html
  - title: RatePay - Prepayment
    link: docs/scos/dev/technology-partner-guides/page.version/payment-partners/ratepay/ratepay-payment-methods/ratepay-prepayment.html
  - title: RatePay - State Machine Commands and Conditions
    link: docs/scos/dev/technology-partner-guides/page.version/payment-partners/ratepay/technical-details-and-howtos/ratepay-state-machine-commands-and-conditions.html
---

## Workflow Scenarios


### Payment Flow
![Click Me](https://spryker.s3.eu-central-1.amazonaws.com/docs/Technology+Partners/Payment+Partners/Ratepay/ratepay-ddelv-payment-flow.png)

### Cancellation Flow
![Click Me](https://spryker.s3.eu-central-1.amazonaws.com/docs/Technology+Partners/Payment+Partners/Ratepay/ratepay-ddelv-payment-flow.png)

### Partial Cancellation Flow
![Click Me](https://spryker.s3.eu-central-1.amazonaws.com/docs/Technology+Partners/Payment+Partners/Ratepay/ratepay-ddelv-partial-cancellation-flow.png)

### Refund Flow
![Click Me](https://spryker.s3.eu-central-1.amazonaws.com/docs/Technology+Partners/Payment+Partners/Ratepay/ratepay-ddelv-refund-flow.png)

## Integrating RatePay

Direct Debit Payment
In order to integrate direct debit payment, two simple steps are needed: set RatePAY Direct Debit payment configuration and call the facade functions.

### Set RatePay Direct Debit Configuration

The configuration to integrate Direct Debit payments using RatePAY is:

* `PROFILE_ID`: merchant's login (required).
* `SECURITY_CODE`: merchant's password (required).
* `SHOP_ID`: shop identifier (required).
* `SYSTEM_ID`: system identifier (required).
* `CLIENT_VERSION`: client system version.
* `CLIENT_NAME`: client name.
* `RATEPAY_REQUEST_VERSION`: request version.
* `RATEPAY_REQUEST_XMLNS_URN`: request XMLNS urn.
* `MODE`: the mode of the transaction, either test or live (required).
* `API_TEST_URL`: test mode API url.
* `API_LIVE_URL`: live mode API url.
* `DEBIT_PAY_TYPES`: debit pay types, can be DIRECT-DEBIT or BANK-TRANSFER.

## Performing Requests

In order to perform the needed requests, you can easily use the implemented state machine commands and conditions. The [RatePAY State Machine Commands and Conditions](/docs/scos/user/technology-partners/201903.0/payment-partners/ratepay/ratepay-state-machine-commands-and-conditions.html) section gives a summary of them. You can also use the facade methods directly which, however, are invoked by the state machine.