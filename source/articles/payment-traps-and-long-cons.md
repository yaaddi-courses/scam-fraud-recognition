# Payment traps and long cons

**Covers:** Wire transfer, Ponzi scheme, Pig-butchering scam

## Why the money step matters most {#overview}
Every scam ends with a payment, and how you pay often decides whether you can ever get anything back. Scammers know this, so they steer you toward routes that are fast and hard to reverse. Some scams are over in minutes and others take months, but they all depend on you moving money in a way you cannot easily undo. In this article we look at one of those routes and two of the slower schemes.

## Wire transfer {#wire-transfer}
A wire transfer sends money directly from one bank to another. It is fast, often done the same day, and it is built to be final. That is exactly what you want when buying a house, and exactly what a scammer wants too.

Compare it with a card payment, where you can often dispute a charge. With a wire, once the receiving bank has paid out, the money is usually gone. If you realize within hours that you were tricked, call your bank right away and ask for a recall, because a quick call is your only chance. So be suspicious of anyone who insists on a wire, especially for a small business deal, a prize fee, or a "safe account" you are told to move your savings into. Banks never ask you to do that.

## Ponzi scheme {#ponzi-scheme}
A Ponzi scheme is a fake investment that pays its early investors with money from newer ones, and not from real profits. The name comes from Charles Ponzi, who in 1920 promised Boston investors a 50 percent return in 45 days.

For a long time it looks like a success, because early investors receive what they were promised and tell their friends. But think about what has to happen: the scheme needs a constant flow of new money. When recruitment slows, or many people try to withdraw at once, it collapses, and the late investors lose everything. Bernard Madoff's scheme, uncovered in 2008, showed the same pattern on a very large scale.

Watch for returns that are high and steady whatever the market does, secrecy about how the money is made, pressure to bring in friends, and trouble getting your money back.

## Pig-butchering scam {#pig-butchering-scam}
This one is a long con, and it works on your feelings before your wallet. The scammer builds a friendship or a romance over weeks, often by sending a "wrong number" text and then chatting every day. Once trust is high, they mention a profitable investment, usually in crypto, and guide the victim to a fake website that shows rising profits. The victim adds more and more money, until a withdrawal is "blocked" by a new fee.

The name is a translation from Chinese. It compares the victim to a pig being fattened before slaughter. The early, kind phase is the fattening, and the investment is the butchering.

How do you defend yourself? Be careful with strangers who contact you by accident and quickly become close. Never move money on the advice of someone you have not met in person. And check any investment site with an official regulator.

## A worked example {#example}
Let's see with numbers why a Ponzi scheme has to keep growing. Investors put in 10,000 dollars at the start. Each month, the scheme promises a 10 percent payout on everything invested. It recruits 2,000 dollars of new money a month for three months, and then recruiting stops. The program below tracks the cash the scheme holds and the total it owes investors.

```python
cash = 10_000
owed = 10_000
for month in range(1, 7):
    new = 2_000 if month <= 3 else 0
    cash += new
    owed += new
    cash -= owed * 0.10
    print(month, round(cash), round(owed))
# 1 10800 12000
# 2 11400 14000
# 3 11800 16000
# 4 10200 16000
# 5 8600 16000
# 6 7000 16000
```

Here is how to read it.

1. While new money arrives (months 1 to 3), cash stays near 11,000 and everything looks healthy.
2. In month 4, recruiting stops, but the promised payouts of 1,600 a month continue.
3. Cash falls by 1,600 a month: 10,200, then 8,600, then 7,000.
4. By month 6, the scheme holds 7,000 and owes investors 16,000. It can never repay everyone, so the last investors lose their money.

Real schemes are messier, but the shape is the same: the payouts come out of new deposits.

## A common mistake {#mistake}
A common slip is judging an investment by the payments it has already made. Early payments prove nothing, since a scheme can pay for a while with new deposits. Ask where the profit comes from, and whether you can withdraw all your money easily. Another slip is staying quiet because you feel embarrassed. Telling your bank quickly and reporting the scam can limit the loss.

## Key points {#key-points}
- A wire transfer is hard to reverse, so be suspicious when someone demands it.
- A Ponzi scheme pays old investors with new investors' money and collapses when the money stops.
- A pig-butchering scam builds trust for weeks before steering you to a fake investment.
- Ask where the profit comes from, and never move money for someone you have only met online.
