# Phishing Email Investigation Report

## 1. Executive Summary

This investigation analyzes a suspected phishing email using message headers, authentication results, delivery infrastructure, URLs, and other available indicators.

The analysis found that SPF, DKIM, and DMARC authentication all passed. However, successful email authentication does not independently establish that the message content or intent is legitimate.

The authentication results were therefore evaluated alongside other available evidence to determine the characteristics of the message and identify indicators relevant to the investigation.

## 2. Evidence Sources

The investigation was based on:

* Gmail "Show original" message headers
* Authentication-Results headers
* SPF, DKIM, and DMARC results
* Email delivery information
* Sender and receiving infrastructure
* URLs and redirect behavior
* Message content
* Other observable indicators

Sensitive and recipient-specific information has been redacted from the public repository.

## 3. Authentication Analysis

The receiving Gmail server reported:

```text
DKIM: pass
SPF: pass
DMARC: pass
```

SPF indicated that the sending IP was authorized by the SPF policy for the envelope sender domain.

DKIM validation succeeded, and the signing domain was:

```text
mail.shopee.co.id
```

The DKIM selector was:

```text
smtp1
```

DMARC also passed, with the authenticated `From:` domain reported as:

```text
mail.shopee.co.id
```

These results indicate successful authentication and domain alignment for the message.

## 4. Delivery Evidence

The message was received by Gmail from:

```text
smtp3223-fr4.mail-messaging.com
```

The connection used TLS 1.3.

The sending IP has been redacted from the public repository.

## 5. Indicators

Observed indicators include:

* Sender domain: `mail.shopee.co.id`
* DKIM selector: `smtp1`
* Receiving infrastructure: `smtp3223-fr4.mail-messaging.com`
* SPF: Pass
* DKIM: Pass
* DMARC: Pass

Recipient-specific identifiers and unique tracking information have been redacted.

## 6. Limitations

Email authentication results should not be treated as proof that the message itself is safe or that the sender's business intent is legitimate.

A domain can successfully authenticate a message while the message itself may still contain suspicious content, malicious links, deceptive requests, or other phishing characteristics.

The conclusions of this investigation should therefore be based on the combined evidence rather than authentication results alone.

## 7. Conclusion

The analyzed message successfully passed SPF, DKIM, and DMARC authentication.

The available authentication evidence indicates that the message was authorized and authenticated through the domains represented in the headers. However, authentication alone cannot determine whether the message is benign or malicious.

Further assessment should consider the message content, URL destinations, redirect behavior, infrastructure, and other indicators documented throughout the investigation.
