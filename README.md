Observed Behavior

The request returned an HTTP 301 redirect.

The redirect ultimately reached:

https://shopee.co.id/buyer/login/

The final response returned:

HTTP/2 200
Interpretation

The destination resolved to legitimate Shopee infrastructure.

The redirect chain therefore does not independently establish that the
destination was a phishing page.

Further investigation of the original email and authentication headers
is required.


That gives you a **real technical artifact**, rather than just screenshots.

---

# 6. Then make your IOC file

Create:

```text
iocs/iocs.md

Example:

# Indicators of Interest

| Type | Value | Assessment |
|---|---|---|
| Domain | shopee.co.id | Legitimate Shopee regional domain observed |
| URL path | /universal-link/buyer/login/ | Observed in email |
| Parameter | deep_and_web=1 | Observed |
| Sender domain | mail.shopee.co.id | Observed in email metadata |

> Note: Indicators are documented as observed artifacts and are not automatically
> classified as malicious.

The URL returned an HTTP 301 redirect and ultimately reached a Shopee Indonesia login endpoint returning HTTP 200 OK.

The email metadata also showed:

From: info@mail.shopee.co.id
Reply-To: info@mail.shopee.co.id
Mailed-by: mail.shopee.co.id
Signed-by: mail.shopee.co.id

These observations require further analysis of the original Authentication-Results headers before making a definitive authentication assessment.

Evidence

Screenshots and supporting evidence will be added to the evidence/ directory.

Sensitive information such as personal email addresses, unique tracking identifiers, message IDs, and other identifying information will be redacted before publication.

Limitations

This investigation does not currently establish that:

the sender was definitively malicious;
the destination was a phishing page;
credentials were harvested; or
the email was spoofed.

The investigation remains classified as:

Suspected phishing / social engineering — further analysis required.

Defensive Lessons

This investigation demonstrates the importance of correlating multiple sources of evidence rather than relying on a single indicator or automated verdict.

The investigation process includes:

Email context → Authentication → URL analysis → HTTP behavior → Infrastructure → Threat intelligence → Assessment
