# Overview

Our SMS API allows you to send text messages to users around the globe through simple RESTful APIs.

- Programmatically send and receive high volume of SMS anywhere in the world.
- Build apps that scale with the web technologies that you are already using.
- Send SMS with low latency and high delivery rates.
- Receive SMS for free using SMS-enabled local numbers in countries around the world.
- Only pay for what you use, nothing more.

#### Available HTTP methods

Our API uses HTTP verbs to understand if you want to read (`GET`), delete (`DELETE`) or create (`POST`) an object. When your web application cannot do a `POST` or `DELETE`, we provide the ability to set the method through the query parameter `_method`.

#### Number format

Numbers are a key concept to understand when working with the API. The following points should be considered before developing your Application.

All phone numbers in the APIs use E.164 format. This means that numbers:

- Omit both a leading `+` and the international access code such as `00`.
- Contain no special characters, such as a space, `()` or `-`

For example, a US number would have the format `14155550101`. A UK number would have the format `447700900123`.

#### Sender ID

All text messages carry a sender ID. When you send a text message through API, you could use any of the approved sender IDs for your account.

In case you have not created a sender ID, you can always create one through our application. Once the Sender ID is approved, you can start sending messages.

#### Message Templates

Message Templates are message formats for common reusable messages a business may want to send. Businesses must use Message Templates for sending notifications to customers.

## SMS Length Summary

#### Standard GSM Characters

| No.of SMS | No.of Characters          |
| --------- | ------------------------- |
| 1         | 160 characters.           |
| 2         | (2 x 153) 306 characters. |
| 3         | (3 x 153) 459 characters. |

#### Unicode Characters

| No.of SMS | No.of Characters         |
| --------- | ------------------------ |
| 1         | 70 characters.           |
| 2         | (2 x 67) 134 characters. |
| 3         | (3 x 67) 201 characters. |
