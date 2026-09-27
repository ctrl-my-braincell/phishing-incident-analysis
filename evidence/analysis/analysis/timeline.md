# Incident Timeline

## Investigation Timeline

### 1. Email Received

An unsolicited email was received claiming that the recipient's Shopee account was scheduled for permanent deletion due to inactivity.

The message included an embedded login link and used urgency to encourage the recipient to interact with it.

### 2. Initial Triage

The email was treated as suspicious because of its account-deletion claim, urgency, and request to access an account through an embedded link.

No interaction with the link was performed from the normal user environment during initial triage.

### 3. Email Metadata Review

The available email metadata was reviewed, including:

* `From`
* `Reply-To`
* `Mailed-by`
* `Signed-by`

The visible sender and associated metadata appeared to reference Shopee infrastructure.

### 4. Authentication Analysis

The email's authentication headers were examined to determine the results of SPF, DKIM, and DMARC.

These results are being evaluated together with domain alignment and the complete delivery path rather than being treated as standalone evidence.

### 5. URL Analysis

The embedded URL was analyzed from an isolated Linux environment.

The request produced an HTTP `301` redirect and ultimately reached a Shopee Indonesia login endpoint returning `HTTP 200 OK`.

### 6. Infrastructure and Threat Intelligence

Additional investigation is being performed to correlate the observed domains, URLs, IP addresses, and infrastructure with available threat-intelligence information.

### 7. Current Assessment

The investigation remains classified as:

**Suspected phishing / social engineering — further analysis required.**

The available evidence does not currently establish that credentials were harvested or that the destination was malicious.
