# Boleia — concept v6

In Brazil, a lot of truck drivers get stuck at a loading/unloading point for days. When that happens, they go home riding with another truck driver who is heading that way, and leave their own truck behind. Nobody pays for these rides: it's a favor swap. I give you a ride today, you give me one tomorrow.

These rides are offered and requested in hundreds of small WhatsApp groups. Nobody can follow all of them, so people ask for a seat that was already taken in another group. Some drivers take far more rides than they give, and some never give any. And since giving a ride to a stranger is a known cargo-theft risk, many drivers only ride with people they already know.

**Boleia** fixes that. It is one place where verified truck drivers offer and find rides home, with a fair way to keep score of the favors.

## How it works for the driver

- The driver signs up with their driver's license (CNH), their ANTT registration (RNTRC) and a selfie. Only verified professional drivers get in. This is the safety promise WhatsApp groups can't make.
- **Friends:** drivers add the colleagues they know. On every ride you see "you have 3 friends in common with this driver". You only see friends you have in common, never the other person's full list.
- **Women only:** women drivers can post or search for rides with women only. Self-declared at signup, checked against the selfie during verification, and removed if reported.
- Everything works through a WhatsApp bot first (an app comes later). You post a ride once and it shows up everywhere. When the seats are filled, it's marked as full everywhere at once.
- The unit is the **km**. 1 km of ride = 1 km of credit. A 280 km ride costs 280 km. If 2 people ride with me for 280 km, I earn 560 km. Ride prices are calculated in advance and never change. A detour to drop someone off is not charged.
- When a seat is booked, the passenger's km are locked. They are released to the driver when both phones confirm (by GPS) that the pickup and drop-off happened. If there's no signal, the phone records the GPS proof and sends it when it's back online.
- **Ratings:** passengers and drivers rate each other after each ride. Ratings are shown on the profile but never change km balances or credit limits.
- **Cancellations:** free up to 3 hours before the ride. Less than 3 hours before, or a no-show, costs 10% of the ride, paid to the other person (not to Boleia). The same rule applies to drivers and passengers.

## The km balance (mutual credit)

Nobody gets free tokens. Everyone starts at **0 km** and can go below zero, down to a credit limit. Giving a ride raises your balance; taking a ride lowers it. The sum of all balances is always zero. km are created only when a real ride happens, so there is no inflation and nothing for fake accounts to farm.

**Credit limit: up to 1,000 km** (a typical ride is about 150 km, so that's about 6 rides on credit). That way drivers who can't give rides often are not left out. To keep it safe, the limit grows:

| How                                                   | Limit             |
| ----------------------------------------------------- | ----------------- |
| New verified driver                                   | −300 km (2 rides) |
| Each ride you give, or each 3 months with no problems | +100 km           |
| Each friend who vouches for you (max 3)               | +100 km           |
| Maximum                                               | −1,000 km         |

If you vouch for someone and they disappear with a negative balance, your own limit goes down. Vouching puts your reputation behind someone, just like in the WhatsApp groups today.

Someone who reached their limit has two options: give a ride, or buy km. Only **earned** km (a positive balance) can be sent or sold. Credit-limit km can only pay for rides.

### Locked km (km paid with credit)

If a passenger pays with credit (their balance is negative) and then disappears, the driver who sold those km to Boleia was paid in real money for km that will never be repaid. It's also the easiest fraud: a fake account rides on credit with a colluding driver, who cashes out. So:

- km paid by a passenger with a **negative balance** arrive **locked**. The driver can use them for rides right away, but can't sell or send them.
- They **unlock** once the passenger's balance gets back to zero or above (by giving rides or buying km).
- **Good reputation exception:** km paid by a passenger with a good reputation arrive unlocked. Good reputation means: account at least 6 months old, at least 5 rides given, never defaulted.
- **The lock follows the km.** If the driver pays someone else with locked km, they arrive locked for that person too. Otherwise one extra fake ride would get around the lock. When spending, locked km are used first, so the driver's free km stay free.
- **Sell early:** depends on who paid.

  | Who paid with credit | Can the driver sell those km early? |
  | --- | --- |
  | **Newcomer**: still on the starting −300 km limit (hasn't given a ride or completed 3 clean months yet) | **No.** They unlock only when the newcomer's balance is back to zero or above. |
  | **Established**: limit already raised, but not yet good reputation | **Yes**, at a flat **R$0.20 − 3%** instead of R$0.25 − 3%. The R$0.05 difference goes to the default reserve. |

  A driver is never stuck with more than 300 km from any single newcomer. A newcomer who wants to be accepted easily can **buy km and pay with them**: bought km are backed, so the driver receives them unlocked. The early sale is a lower buy-back price, not a loan or a receivables advance ("antecipação de recebíveis"), so it doesn't turn Boleia into a credit operation.
- If the passenger defaults (12 months inactive), the default reserve unlocks the km that came from them. Honest drivers don't lose. Accounts flagged for fake rides are excluded.

**Expiry.** km never lose value while you use the app. After **12 months with no activity at all** (no ride, trade or transfer), with warnings at month 9 and month 11:

- A positive balance goes to the **default reserve**.
- A negative balance counts as a default and is covered by that same reserve.

Because inactive surpluses pay for inactive debts, the system stays balanced. (Check with a lawyer whether km someone _bought_ with money can expire under consumer law, the CDC.)

## Carriers

- **Carriers buy km** at market price (no volume discount) and send them to their drivers, instead of paying bus tickets and losing days.
- **Company drivers give rides too**, including in a company truck going empty. The km always go to the driver, never to the carrier.
- Whether a driver is allowed to carry a passenger in their truck is the driver's responsibility. They accept this in the terms of use. Boleia doesn't check each company's policy.

## The market (where the money is)

conta.vc's license covers R$ ↔ **BRS** (their BRL stablecoin on Solana). Boleia runs only the **BRS ↔ km** part. The driver only sees "sell my km, receive R$ by Pix". The wallet and network fees are invisible, and Boleia pays the gas.

- **Drivers who give a lot** turn their surplus km into extra money.
- **Drivers who ride a lot** buy km and keep riding fairly, instead of free riding.
- **Family and friends:** earned km can be sent to anyone for free.

### Phase 1: Boleia buys and sells (launch)

At launch, Boleia is the **only counterparty**. It sells km at a fixed price and buys them back at a fixed price, like a company selling and buying back its own vouchers.

|                 | Price per km    | 150 km ride |
| --------------- | --------------- | ----------- |
| Driver buys km  | R$0.30 + 3% fee | R$46.35     |
| Driver sells km | R$0.25 − 3% fee | R$36.38     |

- The price is stable on day one, so there's no band to defend.
- Boleia's revenue is the 3% on each side plus the R$0.05 spread.
- **No reserve needs to exist up front for km that were bought.** When Boleia sells km, its own balance goes negative and it keeps the BRS. When it buys km back, it uses that BRS. Every km Boleia sold is backed by BRS it received.
- **The reserve is only needed when more people sell than buy** (givers cashing out while riders are still within their credit). See "Starting reserve" below.
- It's legally simpler: a merchant selling and buying back credits for its own service, not an exchange between third parties. Brazil's crypto law (Lei 14.478) excludes from "virtual asset" anything that only gives access to a specific service, like loyalty points. km are rides, so the argument is strong. **Confirm this with a lawyer.**

### Phase 2: open market (later)

Once there is volume and a legal opinion, drivers trade with each other inside a **R$0.20–0.30 band**, with a 3% fee for everyone. Then a driver can choose to sell above Boleia's buy-back price if someone is willing to pay.

### Starting reserve

The reserve needs BRS for the case where people want to sell km faster than other people buy them. Where it comes from, in order:

1. **Carrier pre-sale:** before launch, sign 2–3 carriers that prepay km (e.g. R$10k each). This puts BRS in the treasury before the first sale, and proves demand.
2. **Grants:** Solana Foundation, Superteam Brasil and similar ecosystem programs fund real-world-use projects like this.
3. **Fees:** part of every 3% fee goes to the reserve.

To make sure the reserve never runs dry:

- **Sell limit:** each driver can sell up to 1,000 km per month (about R$250).
- **Queue:** if the reserve is low, sell orders wait in line (first in, first out) and are paid as new purchases come in. The price never drops.

Rough size: 2,000 active drivers, 20% selling 500 km/month → 200,000 km × R$0.2425 ≈ **R$48k/month** of sell pressure before any buyers. In practice, buyers and carriers cover part of it, but plan for a seed reserve of **R$50–100k**. For the first 6 months, a lower sell limit (500 km/month) halves the pressure.

**Why not staking/yield:** paying users a yield from fees makes km look like an investment, which brings in the CVM (Brazil's securities regulator). It also confuses drivers, and putting the reserve in DeFi risks losing it. Simple is better here. The only acceptable yield is on the treasury's own reserve, in a low-risk CDI-linked product, if conta.vc offers one.

## How Boleia makes money

1. **3% fee** on every km purchase and sale (drivers and carriers). No fee on rides and no fee on family transfers. The fee is charged in BRS, so Boleia never piles up its own token.
2. **Buy/sell spread** in Phase 1: R$0.05 per km (R$0.10 on early sales of locked km from established drivers, with the extra R$0.05 going to the default reserve).
3. **Ramp revenue share** with conta.vc on R$ ↔ BRS.
4. **Carriers (B2B):** the big buyers. They push demand up and turn giving rides into real income for drivers.
5. **Later:** per-ride personal accident insurance (with an insurer), sponsorship from truck stops and fuel networks, return-load referrals to freight boards (with the driver's consent, under LGPD, Brazil's data-protection law).

**Why adoption = revenue.** Trading volume comes from imbalances between givers and riders, plus carriers. More drivers means more imbalances and more carriers, which means more volume. The free ride board is how we grow; the market is how we make money.

## Risks we must handle

- **Defaults:** someone uses up their credit limit and disappears. Worst case per user: 1,000 km × R$0.25 = R$250. Mitigations: a limit that grows over time, vouching, mandatory ID verification, and a default reserve funded by expired balances plus part of the fees.
- **Fake rides** between accounts. A fake 150 km ride is worth about R$36, so the incentive is real. Mitigations: locked km, GPS check at pickup and drop-off, the same pair repeating rides gets flagged, low limits for new accounts, the monthly sell limit.
- **Favor culture:** if it feels like a taxi, drivers may stop helping. The app talks about "km" and "favors", never "price" or "money". Selling is optional, off to the side.
- **Carrier policies:** a company driver could be punished by their employer for carrying a passenger. Covered by the terms of use, but it's worth being clear about it in onboarding.
- **Regulation:** get a lawyer's opinion on Phase 1 (Boleia buys and sells km for BRS) before launch, and on Phase 2 (open market) before turning it on.

## Security: replaying ride confirmations

This is the same bug as the ecomilhas pentest: capture the confirmations of ride A and ride B and resend them (A, B, A, B...), and every one is credited again. The fix has four layers, and the first one alone kills the bug.

1. **One-way ride states.** A ride goes `booked → started → completed` (or `cancelled`) and never goes back. The payment happens in the same database transaction as the state change, and the change only succeeds if the ride is in the expected state:
   ```sql
   UPDATE rides SET status = 'completed'
   WHERE id = $1 AND status = 'started';
   -- 0 rows affected → reject, nothing is paid
   ```
   A replay of A finds A already `completed` and does nothing. Because the check and the change are a single statement, it also holds up against many requests sent in parallel (race conditions), not only one after another.
2. **One payment per ride, enforced by the database.** The ledger has a unique constraint on `(ride_id, entry_type)`. Even if a bug in the code lets a duplicate through, the database refuses a second payment for the same ride.
3. **Signed proofs.** Each phone has a key pair (the same ed25519 key as its Solana wallet). Pickup and drop-off proofs are signed over `ride_id + event + GPS + timestamp + nonce`. The server rejects any nonce it has already seen, and completing a ride needs both signatures, from the two people actually booked on it. Intercepting traffic doesn't help, because the attacker can't forge the other phone's signature.
4. **On-chain escrow (when it moves to Solana).** Each ride has its own escrow account (a PDA derived from the ride id). Releasing the km **closes** that account, so a replayed release fails because the account no longer exists.

On top of that: rate limits per account and device, and alerts for impossible patterns (the same pair, overlapping rides, a speed impossible between GPS points).

## Validation before code

1. Join 15–20 groups and log for 2 weeks: posts per day, offers vs. requests, time until a ride fills, duplicates across groups, distance of each ride.
2. Interview about 20 drivers (self-employed and employed) about the km balance, the credit limit, vouching and selling km.
3. Talk to 3 carriers: how much do they spend moving drivers today? Would they prepay km?
4. MVP: WhatsApp bot + km ledger + friends. Turn on buying and selling km once there are real balances.

## Open questions

None right now. The next step is validation (above).
