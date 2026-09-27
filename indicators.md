# Indicators of Compromise

## Email Indicators

| Indicator                | Value                             | Status   |
| ------------------------ | --------------------------------- | -------- |
| Sender domain            | `mail.shopee.co.id`               | Observed |
| DKIM selector            | `smtp1`                           | Observed |
| Receiving infrastructure | `smtp3223-fr4.mail-messaging.com` | Observed |
| Sending IP               | `[REDACTED]`                      | Redacted |

## URL Indicators

Unique tracking and destination URLs have been redacted from the public repository to prevent exposing recipient-specific or potentially sensitive information.

## Header Indicators

The following header fields were observed during analysis:

* `Authentication-Results`
* `Return-Path`
* `Message-ID`
* `DKIM-Signature`
* `Received`
* `X-IB-WebHookData`
* `X-IB-WebHookData2`

Recipient-specific and unique identifiers have been redacted from the public evidence.

## Authentication Indicators

| Authentication Method | Result |
| --------------------- | ------ |
| SPF                   | Pass   |
| DKIM                  | Pass   |
| DMARC                 | Pass   |

Authentication results alone do not establish whether an email is malicious or legitimate. These indicators should be evaluated together with the message content, URLs, redirects, sender infrastructure, and other investigation findings.
