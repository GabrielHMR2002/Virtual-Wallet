## Objective: Simplified PicPay

We have 2 types of users, regular users and merchants, both have a wallet with money and can transfer money between them. We will focus **only** on the transfer flow between two users.

Requirements:

- For both types of users, we need Full Name, CPF (Tax ID), email, and Password. CPF/CNPJ and emails must be unique in the system. Therefore, your system should only allow one registration with the same CPF or email address.

- Users can send money (make transfers) to merchants and between users.

- Merchants only **receive** transfers, they do not send money to anyone.

- Validate if the user has a balance before the transfer.

- Before completing the transfer, an external authorization service must be consulted, use this mock to simulate (https://run.mocky.io/v3/5794d450-d2e2-4412-8131-73d0293ac1cc).

- The transfer operation must be a transaction (i.e., reversed in any case of inconsistency), and the money must return to the wallet of the user who sends it.

- Upon receiving payment, the user or merchant needs to receive a notification (email, SMS) sent by a third-party service, and this service may eventually be unavailable/unstable. Use this mock to simulate the sending (https://run.mocky.io/v3/54dc2cf1-3add-45b5-b5a9-6bf7e7f1f4a6).

- This service should be RESTful.

### Payload

Propose a payload :heart: for the POST /transaction endpoint, or use the example below:

```json
{
    "value": 100.0,
    "payer": 4,
    "payee": 15
}
