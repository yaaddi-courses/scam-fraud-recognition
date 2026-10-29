# Phishing in email, text messages and QR codes

**Covers:** Phishing, URL, Spoofing, SMS, Smishing, QR, Quishing

## One trick, many doors {#overview}
The oldest online scam is also the most common one: a message that pretends to come from someone you trust and asks you to do one small thing, such as click a link, open an attachment or type a password. Only the disguise changes with the channel. The same trick arrives by email, by text message and in a printed code. Once you know how each version works, the warning signs become much easier to see.

## Phishing {#phishing}
Phishing is a scam message, most often an email, made to look like it comes from a bank, a delivery company, your employer or a friend. Its job is to get you to click a link that leads to a fake page, or to give away details such as passwords and card numbers.

These messages share a recognizable shape: an urgent reason ("your account will be closed"), a link or attachment, and a request for details. Real companies rarely ask you to log in through an email link. So whenever you have doubts, close the message and open the company's site yourself, by typing the address or using a saved bookmark.

## URL {#url}
A URL is a web address, such as `https://www.example.com/login`. Learning to read one properly is your best defense against fake pages, because the important part is not where you would expect it.

Here is the trick: read the address from the end of the host name backward. In `https://paypal.com.account-verify.example/signin`, the real owner is the last two parts before the first slash, which is `account-verify.example`. The words "paypal.com" at the start are only a prefix the scammer chose. Watch for look-alike spellings too, such as `paypa1.com`, where the digit 1 stands in for the letter l.

## Spoofing {#spoofing}
Spoofing means faking who a message or call comes from, so that the sender name or number looks trustworthy while the real source is someone else. An email can show your bank's name in the sender field even though the actual address has nothing to do with it. Anyone can type a name into that field.

That is why a familiar name or logo proves nothing. Check the full address, not only the display name, and treat any request for money or passwords as suspicious, no matter who it seems to come from.

## SMS {#sms}
SMS is the plain text message service that phones use. Texts feel more personal than email, and people usually read them within minutes. That is exactly why scammers like them.

## Smishing {#smishing}
Smishing is phishing sent as a text message. The common versions are a fake delivery notice ("your package is held, pay a small fee"), a bank alert ("unusual sign-in, tap to confirm") and a toll or fine reminder. The link leads to a page that copies a real company.

Do not tap the link, and do not reply to unknown numbers. Open the official app or website on your own and see whether the problem exists there.

## QR {#qr}
A QR code is a square barcode that your phone camera reads, usually to open a web address. You cannot tell where it leads just by looking at it, and that is the reason scammers like it.

## Quishing {#quishing}
Quishing is phishing delivered through a QR code. A scammer sticks a fake code over a real one on a parking meter or a restaurant table, or emails a code to get past filters that look for bad links. Scanning it takes you to a fake payment or login page.

Before you scan, check that the sticker is not placed on top of another one. After scanning, read the address your phone shows before you open it, and never type a password or card number on a page you reached from an unknown code.

## A worked example {#example}
Let's check three links with a short program that splits each one and shows who really owns it. It uses a simple rule that works for common addresses: take the last two parts of the host name.

```python
from urllib.parse import urlparse

links = [
    "https://www.paypal.com/signin",
    "https://paypal.com.account-verify.example/signin",
    "https://paypa1.com/signin",
]

for link in links:
    host = urlparse(link).hostname
    owner = ".".join(host.split(".")[-2:])
    print(host, "->", owner)
# www.paypal.com -> paypal.com
# paypal.com.account-verify.example -> account-verify.example
# paypa1.com -> paypa1.com
```

Let's read the result.

1. The first link is the real one. The owner is `paypal.com`, and `www` is only a section of that site.
2. The second link contains the words `paypal.com`, but its owner is `account-verify.example`, a scammer's site. This is a typical trick.
3. The third looks right at a glance, but `paypa1.com` is a different domain that uses the digit 1.

The rule is simple on purpose. Some countries use endings with two parts, such as `.co.uk`, where the owner is the last three parts. So treat the program as a way to learn the idea, not as a real filter.

## A common mistake {#mistake}
A common slip is judging a message by how it looks. Logos, colors and even correct grammar are easy to copy. Judge it by what it asks you to do: act fast, click, and enter details. Another slip is trusting a link because a friend's account sent it, since accounts get hacked.

## Key points {#key-points}
- Phishing, smishing and quishing are the same trick through email, text and QR codes.
- Read a URL from the end of the host name backward to find its real owner.
- Spoofing fakes the sender, so a familiar name or logo proves nothing.
- Open the official site or app yourself instead of using a link or code you were sent.
