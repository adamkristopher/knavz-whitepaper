# The Knavz White Paper

**The knave: a coin earned only by play.** November 2026.

Knavz (knavz.com) is a puzzle game for people and their AI agents. Makers write puzzles, solvers race to crack them, and the first correct answer wins newly issued knaves, the game's coin. This paper sets out how knaves are issued, how the supply is capped, how they reach the blockchain, and the controls that keep those rules true.

Nothing here is an offer to sell anything, a promise of value, or investment advice. The token described in sections 7 to 11 isn't launched yet. Its rules may still be refined before it launches, and any change is announced on knavz.com first.

---

## 1. The idea

Knaves start as the coin of one puzzle game, earned by making and solving puzzles. In the longer run, we hope other games for the same players (tabletop, role-playing and indie games) will accept knaves too. That's an aim, not a promise: nothing is agreed with any other game.

In one line: **knaves are earned only by playing, there will only ever be a fixed number of them, and they're useful wherever the people who earned them play.**

## 2. Earned only by play

- **No sale, no premine, no launch mint.** Nobody buys their way in at the start. Knaves are issued only when puzzles are solved.
- **Makers and solvers:** makers publish puzzles, and solvers race to crack them. When a puzzle is solved, the solver wins a prize and the maker earns a payout. **An unsolved puzzle issues nothing.**
- **Like proof of work:** new coins come only from effort, never from an issuer selling them. Here the work is a puzzle solved.
- **Agents welcome:** players solve and write with their own bots and AI models. Puzzles that hold out against AI draw bigger crowds, and crowded puzzles pay more (section 6).
- **One player per X account:** every player verifies an X account with a paid blue or business check. That keeps one person from playing as a crowd.

## 3. Supply: 21,000,000 knaves

- **21,000,000 knaves in all, ever.**
- **The reserve:** every knave paid to a player is matched by one knave issued into a locked reserve, in the same transaction. So the reserve is half of everything issued, and **players' share tops out at 10,500,000**. The reserve can't be spent, sold or sent; it only ever goes into the token's liquidity pool (section 8).
- **Issued and on-chain are two different numbers:**
  - **Issued** means created in the game's ledger. A knave is issued when its payout is released, after a 24-hour hold, and the reserve's match is issued with it. **Issuance is what counts toward the 21,000,000 and the halvings,** whether or not a token exists yet.
  - **On-chain** means minted as the token. A player's knaves go on-chain only when they withdraw them, and the reserve's only when they go into the liquidity pool. The on-chain supply is always a part of what's been issued, never more.
  - **An example:** a solve releases 1 knave to the solver and 1 to the maker, and 2 to the reserve: 4 issued, none of them on-chain yet. The reserve's 2 go on-chain when they're paired with ETH in the pool; the solver and the maker may each withdraw at most a tenth of theirs in their first week (section 10).
- **Burns:** some in-game spending (cosmetic flair, when it opens) burns knaves. A burn takes knaves out of circulation; the cap still counts what was issued.

## 4. Rewards halve as the game grows

The halving is keyed on **knaves issued**, not on blocks, puzzles or solves. Puzzles can be taken down and payouts clawed back, so a count of them can drift; the total issued only ever goes up, and it makes the cap exact.

```
epoch k ends when the total issued reaches 21,000,000 × (1 − ½^(k+1))
reward in epoch k = epoch-0 reward × ½^k
```

| Epoch | Rewards | Ends when the total issued reaches |
| --- | --- | --- |
| 0 | today's rates (section 6) | 10,500,000 |
| 1 | ½ | 15,750,000 |
| 2 | ¼ | 18,375,000 |
| 3 | ⅛ | 19,687,500 |
| 4 | 1/16 | 20,343,750 |
| … | halved again each time | approaches 21,000,000 |

Each epoch issues half as much as the one before: 10,500,000, then 5,250,000, then 2,625,000, and so on.

- **What counts:** every knave released to a player (prizes, maker payouts and promotion bonuses) plus the reserve's match. A payout counts when it's **released**, after its 24-hour hold. A payout clawed back during the hold is never issued, so it never counts. A released payout is final.
- **The count starts at the open,** 6 PM CST on November 25, 2026 (00:00 UTC, November 26): every knave issued on knavz.com from the first payout counts. Test coins on the development server never count.
- **The rate is fixed when the puzzle is solved.** A payout's size is set at the solve, from the epoch the total is in at that moment, and it doesn't change during the hold, so the solver sees the exact prize. Near a threshold, a few held payouts can be issued at the old rate just after the line is crossed; the next epoch starts from wherever the total then stands.
- **Halved rewards round down to the knight** (section 5). A 1-knave prize in epoch 1 is exactly 0.5 knave, and any remainder below one knight is never issued. Rounding down can only issue less than the schedule, never more.
- **The hard stop:** the payout that would cross 21,000,000 is cut down to what fits, the reserve's match included. After that, solves issue nothing, and players keep making and solving for titles and flair. The token contract enforces the same cap (section 13).

## 5. Units: the knave and the knight

- **8 decimals:** 1 knave = **100,000,000 knights**. A knave is made up of knights; the name is shared with the top solver title, on purpose.
- The game's ledger already stores knaves in knights, so balances move to the token 1:1 with no conversion. The token contract uses 8 decimals too.
- The whole supply, 21,000,000 × 10⁸ knights, fits easily in the ledger and in the token.

## 6. Today's rewards (epoch 0)

- **The solver's prize:** 1 knave. A **Knight** wins more on a crowded puzzle: 1, 2, 4, 5, 10 or 15 knaves at 0, 30, 60, 100, 250 or 500 participants.
- **The maker's payout:** 1 knave for every 30 participants on a solved puzzle, at least 1. A puzzle that holds out long enough to draw a crowd pays its maker far more.
- **Titles and promotion bonuses:**
  - **Solvers** climb Page, Squire, Man-at-arms, Sergeant, Knight, moving up after 10 solves within 30 days of their last title change, with bonuses of 2, 4, 10 and 15 knaves (31 in all to reach Knight).
  - **Makers** climb Urchin to Knave by stumping solvers; a higher title lets them publish more puzzles a day (1 to 5).
  - Titles aren't lost for inactivity.
- **Fair play:** every payout is held 24 hours before it's released. Payouts with signs of collusion are held for review, and confirmed cheating is clawed back during the hold and can lead to suspension.
- **Plans:** playing is free (one puzzle and one guess a day). Paid plans give more guesses and puzzles, and are paid in ETH, never in knaves. Payments never issue knaves.
- Every reward above is multiplied by ½ in each later epoch (section 4).

## 7. The token

- An **ERC-20 on Base,** from an immutable contract, with 8 decimals.
- **Only the game's server can mint,** and only knaves already issued in the game: a player's withdrawal, or the reserve released to the pool.
- The contract enforces the **21,000,000 cap** and a **daily mint cap** itself (section 13).
- **The official token and pool are named only on knavz.com.** Any other address is not Knavz's.

## 8. Liquidity: the launch

- **The launch pool:** Knavz.com puts its launch ETH, **0.28903218 ETH**, into the pool with knaves from the reserve: **one reserve knave for each US dollar the ETH is worth on launch day.** If the ETH is worth $512 that day, 512 reserve knaves go in with it.
- **So the pool opens at about $1 a knave,** with about $1,000 in it in all (about $500 of ETH and about 500 knaves). **A pool this small will swing widely at first:** a single sizeable trade can move the price a long way. It deepens over time through the nightly releases (section 9) and anyone who adds liquidity.
- **When:** the reserve holds that many knaves once roughly twice as many have been issued, which comes soon after the open. The token launches once its contracts, withdrawals and on-chain records are built and checked, not before. If the reserve holds more by then, only the matching amount goes in; the rest waits in the reserve for the nightly releases (section 9).
- **The exchange: Uniswap v3 on Base.** Knavz.com's liquidity is one full-range position, held in a **locker contract**: it can't be pulled, and only its trading fees can be collected.
- **Anyone can provide liquidity.** Pools on Base are open: anyone can add to the official pool, bringing both knaves and ETH at the current price, and earns trading fees in proportion to their share. Outside providers can withdraw theirs at any time; only Knavz.com's liquidity is locked.

## 9. The nightly release

After the launch, every payout released in the game still issues its match into the reserve. Reserve knaves go on-chain only like this:

1. **Each day Knavz.com closes its books:** what its pool position earned in trading fees that day, in ETH and in knaves.
2. **If Knavz.com leaves that day's ETH fees in the pool,** they decide how many reserve knaves join the pool **that night at 00:00 UTC**: the ETH fees ÷ the pool's price, added together as liquidity, equal in value.
3. **The day's issuance doesn't change the night's release.** Reserve knaves the fees can't cover stay in the reserve and wait for a later night. Nothing goes in without matching ETH, so **a release never moves the price.**
4. **If Knavz.com takes the day's fees as income instead,** nothing is released that night.

- **It isn't a sale:** Knavz.com never sells newly issued knaves for anyone's ETH. It reinvests its own fees with its own reserve.
- **The knave half of the fees** becomes owner knaves (section 11).
- **It winds down by itself:** reserve issuance halves each epoch and stops at the cap, so the reserve can never hold more than 10,500,000 knaves. Once its backlog is cleared, fees beyond each night's match are Knavz.com's income; after the cap, all of them are.
- **For liquidity providers:** Knavz.com's nightly additions are always paired with ETH at the current price, so they deepen the pool without moving the price. The on-chain supply grows step by step, always with ETH beside it, and the ticker shows it (section 12).

## 10. Withdrawals

Knaves earned in the game move to the chain slowly and fairly, so nobody can earn knaves and sell them all at once.

- **When withdrawals open:** once the official pool holds at least **$5,000 of ETH** (counting every provider, not just Knavz.com), or **90 days after the token launches**, whichever comes first. Until then, knaves earned in the game stay there and keep counting. Either way, the daily cap below limits how fast withdrawals can reach the pool.
- **10% a week:** each week a player may withdraw up to 10% of their cash-out base: what they held when they started cashing out, plus anything earned since. A player who stops earning and cashes out everything takes **10 weeks**. Knaves already on-chain are the holder's to keep or trade; the limit is only on leaving the game.
- **A daily cap for everyone:** all players together may withdraw at most **2% of the pool's knaves a day**. If every knave withdrawn were sold the same day, that would move the price by about 4% at most, however much is being issued. As the pool deepens, the same 2% lets more knaves out.
- **The withdrawal line:** when more players ask to withdraw than the day's 2% covers, requests wait in line.
  - Requests are grouped by the UTC day they're made. Each night at 00:00 UTC, the 2% serves the oldest day first.
  - **Within one day, it's shared pro rata:** every request gets the same fraction of what it asked for, so being seconds faster, or awake at midnight, never wins a bigger share.
  - Whatever isn't filled stays in line and moves up the next night; nobody has to ask again. Asking for more than your 10% for the week gets nothing extra.
  - **Every request gets a receipt** at once, with the amount, its place in line and an **estimated** delivery date. The receipt says plainly that withdrawals are shared pro rata and that requests wait in line when withdrawal volume is high. The estimate moves earlier as the pool deepens and later if it shrinks; a status check shows the latest estimate and what's been delivered.

## 11. Owner knaves

- **The owner earns knaves only from fees:** the knave half of the trading fees Knavz.com's pool position earns. The owner never earns knaves by playing, and Knavz.com never issues any for the owner. Fee knaves are already on-chain, so they don't count again toward the 21,000,000.
- **Wallets that receive no payouts:** the owner's game wallet receives no payouts. When the owner's puzzle is solved, the solver still wins the prize, but no maker payout (and no reserve match for it) is issued; the owner's own solves and promotions issue nothing either. **Knavz.com's own wallet**, registered with @knavzgame, is the same: the first 50 puzzles at the open are written by Knavz.com's team and published from it, and its puzzles pay their solvers as usual. Nobody who knows the answers plays on knavz.com.
- **The first 50,000 owner knaves are locked until the token's first anniversary.** Every fee knave the owner collects goes into a locker contract until 50,000 are in it, and nothing in it can leave before one year after the token launches.
- **After that, owner knaves leave at most 10% a week,** the same limit as players' withdrawals, enforced by a vesting contract: the 50,000 once they unlock, and any fee knaves beyond them.
- **A published owner address,** so anyone can see what the owner holds.

## 12. The ticker

The site shows, live:
- **knaves issued:** everything created in the game, which counts toward the 21,000,000;
- **knaves left until the next halving,** with the current reward rate;
- **knaves on-chain:** the tokens anyone can buy outside the game (players' withdrawals plus the reserve released to the pool), once the token launches;
- **knaves waiting to withdraw:** the withdrawal line, once withdrawals open.

## 13. Security and controls

The rules above only matter if they're enforced. These are the controls behind them: in place for the game today, or built into the token before it launches.

### Minting

- **Only the game's server can mint,** and only for knaves already issued in the game ledger. Nobody mints knaves by hand.
- **The token contract enforces the caps itself:** 21,000,000 in total and a daily mint cap, so even a stolen server key couldn't mint past them.
- **The minting key and the keys that control it are separate.** The game server holds only the key that mints, within the caps. Who may mint is controlled by Knavz.com's Safe (below), and **any change of the minting key waits 7 days in public** before it takes effect. A compromised server can't raise the caps, and can be cut off by replacing its key.
- **Fixed in the contracts:** the 21,000,000 cap, the daily mint cap and the lockers' unlock dates can't be changed by anyone, the owner included.
- **Anyone can check it:** the on-chain supply can never exceed knaves issued, and the ticker shows both. A daily audit checks the game's ledger (balances against transfers, the reserve and issuance against payouts) and alerts on any drift.

### Releases and locks

- **Knavz.com's liquidity** is one Uniswap v3 position in a locker contract: it can't be pulled, and only its fees can be collected.
- **The nightly release** adds reserve knaves only together with that day's ETH fees, at the current price (section 9).
- **Owner knaves** sit in a published locker until the token's first anniversary, then in a vesting contract that releases at most 10% a week (section 11).
- **Players' withdrawals** follow the opening rule, the 10%-a-week limit, the 2% daily cap and the withdrawal line, each enforced by the server and backed by the contract's caps (section 10).
- **Every address is published on knavz.com:** the token, the pool position, the lockers, the owner address and the treasury.

### The treasury

- Knavz.com's ETH, including the launch ETH, and control of the minting key are held in a **2-of-3 Safe** on Base. Its keys are on separate devices: everyday signing needs two of them, and the third is kept offline as a backup. No single stolen or lost device can move funds or change who mints. **None of the Safe's keys is ever on a game server.**
- **Independent signers** will be added and named as Knavz.com grows.

### Operations

- **The ledger:** every movement of knaves is a single database transaction, guarded by checks in the database itself, and checks that guard value fail closed. Payouts are held 24 hours before they're released, suspicious ones are held for review, and a released payout is final.
- **Signed requests:** every game action is signed with the player's own key and runs once; the server signs its answers too.
- **Least privilege:** the app, deployments, database changes, backups and monitoring each run as their own user with only the access they need. Monitoring reads only the numbers it counts. Secrets live only on the servers; never in code, chat or the repository.
- **Change control:** every change goes through a reviewed pull request, and the automated tests must pass. Production is deployed only from a tested release, by a person, with the previous release kept for a quick rollback.
- **Offsite backups:** the production database is backed up every night, encrypted on the server, to cloud storage where each backup is locked for 30 days, so it can't be deleted or overwritten, even with stolen credentials. The decryption key never touches the server. Restoring from backup is rehearsed.
- **Monitoring and alerts:** the servers are checked every minute (speed, load, memory, disk, database, traffic, sign-ups and failed jobs), with immediate alerts for emergencies; an independent uptime check; and a protective network edge in front of the site, with rate limits on sign-ups and strict security headers.
- **Abuse and enforcement:** suspicious payouts are held for review, and every suspension, takedown and reversal is logged.
- **Incidents:** a written runbook covers taking the site offline, rolling back a release and restoring from backup.

### SOC 2

These controls follow SOC 2's Trust Services Criteria (security, availability, processing integrity and confidentiality). **Knavz.com is working toward SOC 2 compliance.** It hasn't been audited yet and doesn't claim SOC 2 compliance today.

## 14. What's built, and what comes next

- **At the open (6 PM CST, November 25, 2026; 00:00 UTC, November 26):** the game, its ledger and the reserve; the 21,000,000 count and the halving schedule, counting from the first payout; payout holds and review; the ticker's issued count and the knaves left until the next halving.
- **Before the token launches:** the token contract with its caps, the minting key's controls and the Safe; the locker for Knavz.com's liquidity; withdrawals, the withdrawal line and receipts; the owner's locker and vesting contract; and the ticker's on-chain and withdrawal-line counts.
- **Any change to these rules** is announced on knavz.com before it takes effect.
