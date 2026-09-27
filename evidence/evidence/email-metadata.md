# Email Metadata

## Visible Sender Information

The email displayed the following sender-related information:

| Header / Field | Observed Value           |
| -------------- | ------------------------ |
| `From`         | `info@mail.shopee.co.id` |
| `Reply-To`     | `info@mail.shopee.co.id` |
| `Mailed-by`    | `mail.shopee.co.id`      |
| `Signed-by`    | `mail.shopee.co.id`      |

## Redaction

The following information has been omitted from the public repository:

* Recipient email address
* Message ID
* Unique tracking identifiers
* Personal identifiers
* Other values that could uniquely identify the original message or recipient

## Investigation Context

The visible sender and Gmail metadata appeared consistent with Shopee-related infrastructure.

However, these fields alone are insufficient to determine whether the email was legitimate or malicious.

The complete `Authentication-Results` header and underlying authentication details are required to properly evaluate SPF, DKIM, and DMARC.

## Evidence Handling

The original email remains separate from the publicly published evidence.

Only sanitized information relevant to the defensive investigation is included in this repository.
