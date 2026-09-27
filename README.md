
# Suspected E-Commerce Phishing Email — Incident Analysis

## Overview

This repository documents the defensive investigation of a suspicious e-commerce email that initially appeared consistent with a phishing/social-engineering attempt.

The investigation examines:

- Email metadata
- Sender authentication
- Social-engineering indicators
- URL structure
- HTTP redirects
- Destination infrastructure
- Threat-intelligence results
- Investigation limitations

## Incident Summary

An unsolicited email was received claiming that the recipient's Shopee account was scheduled for permanent deletion due to inactivity.

The message used urgency and a direct login prompt to encourage the recipient to interact with an embedded hyperlink.

Initial investigation focused on determining whether the message and associated URL were malicious.

## Current Assessment

The email contains characteristics commonly associated with phishing and social engineering.

However, technical analysis identified legitimate Shopee infrastructure in the email metadata and URL redirect chain.

The available evidence does not currently establish that the destination was a credential-harvesting page.

Further analysis of the complete email authentication headers and delivery path is required.

## Investigation

The URL was analyzed in an isolated Linux environment using:

```bash
curl -sIL "[REDACTED_URL]"
```
