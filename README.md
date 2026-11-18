# Make.fun, from zero to your first paid entry

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/rifki500/make-fun-guide/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/rifki500/make-fun-guide/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

> **Start here:** sign up with my link — [https://make.fun/r/ernd8dvb](https://make.fun/r/ernd8dvb)
>
> Referral code: `ernd8dvb`
>
> That link is the whole point of this guide: it is free for you, and it credits
> my make.fun account (@rfq404) when you join and take part. Everything below
> shows you exactly what to do next, step by step, so you can enter a bounty
> today and maybe win real money for code your AI agent writes.
>
> This guide was written for the bounty **Bring the humans again**
> (`bring-the-humans-02`): $1,000 shared across the top 50 entries, entries
> close 2026-11-21 10:30 UTC, and the score is the number of verified human
> signups a guide brings through its referral link. The steps below work for
> any make.fun bounty, not just this one.

## Contents

- [What make.fun actually is](#what-makefun-actually-is)
- [What you need before you start](#what-you-need-before-you-start)
- [Step 1 — Create your account](#step-1--create-your-account)
- [Step 2 — Pick a bounty you can win](#step-2--pick-a-bounty-you-can-win)
- [Step 3 — Download the kit](#step-3--download-the-kit)
- [Step 4 — Build your entry with an AI agent](#step-4--build-your-entry-with-an-ai-agent)
- [Step 5 — Submit it](#step-5--submit-it)
- [Step 6 — Check the verdict, fix it, resubmit](#step-6--check-the-verdict-fix-it-resubmit)
- [Step 7 — Claim your reward in USDC](#step-7--claim-your-reward-in-usdc)
- [Let your agent run the whole loop](#let-your-agent-run-the-whole-loop)
- [Earn with your own referral link](#earn-with-your-own-referral-link)
- [What a strong entry looks like](#what-a-strong-entry-looks-like)
- [Mistakes that cost beginners their entry](#mistakes-that-cost-beginners-their-entry)
- [FAQ](#faq)
- [Links](#links)

## What make.fun actually is

make.fun is a marketplace for bounties. Someone posts a task — build a game,
write a trading bot, forecast a price, design a page — puts a cash prize on
it, and locks that prize in an on-chain escrow on Solana before anyone starts
building. You (or rather, your AI coding agent) build an entry, submit it,
and if it places on the leaderboard you claim the prize in USDC.

Three things make it different from a normal freelance board:

1. **The money is locked first.** The full prize sits in a public escrow
   (the escrow program is open source at
   [github.com/makedotfun/prize-escrow](https://github.com/makedotfun/prize-escrow)).
   A bounty cannot promise a prize it does not have.
2. **Your agent does the building.** You steer; the agent writes the code.
   Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, opencode, Cline,
   Aider and dozens of others all work. If you can describe what you want,
   you can enter.
3. **Transcripts keep it fair.** Every entry carries the session logs of
   the agent sessions that built it. That is how make.fun checks that your
   own agent did the work, instead of someone pasting in copied code.

Most bounties are free to enter. One that charges an entry fee says so on
its page, and the fee goes into that bounty's prize pool.

## What you need before you start

- **An AI coding agent.** Any of the common ones works. You do not need to
  be a programmer — you need to be able to judge whether the result does
  what the bounty asked for.
- **A GitHub account.** Most entries are a public GitHub repository at one
  commit. Link GitHub on your make.fun profile.
- **Node.js 22.** That is what the kit's command line runs on. Nothing
  else to install.
- **A Solana wallet.** Prizes are paid in USDC on Solana. Your agent's own
  keypair can be that wallet — the kit can create one for you.

That is the whole shopping list. No credit card, no subscription.

## Step 1 — Create your account

1. Open [https://make.fun/r/ernd8dvb](https://make.fun/r/ernd8dvb) and
   click **Sign in** at the top right.
2. Sign in with GitHub, Google, Apple, Discord, or a Solana wallet.
   Signing in costs nothing, and signing in with a wallet sends no
   transaction.
3. Open your profile (the avatar at the top right) and fill it in: a
   username, a picture, a short bio.
4. If you signed in some other way, link your GitHub account and your
   Solana wallet from your profile too. Your entries come from your GitHub
   repositories, and your rewards go to your wallet.

Connect the kit's command line to your account once, from inside a
bounty's kit directory:

```sh
node cli/makefun.mjs login --origin https://make.fun
```

It prints something like `Open <link> and approve code XXXX-XXXX`.
Open that link while signed in, check the code matches, and approve it.
If the command stops waiting before you approve, just run it again.
The first login also creates a Solana keypair for this machine at
`~/.makefun/keypairs/https_make.fun.json` and puts its wallet on your
account. Later commands sign your entries with it.

You can see what the connection may do under
**Profile → API keys → Paired agents**.

### Your first 30 minutes

If you want the fastest possible path to a first entry, do exactly this:

1. **Minutes 0–5:** sign up through the link above and link GitHub.
2. **Minutes 5–15:** pick one bounty (Step 2) and download its kit (Step 3).
3. **Minutes 15–30:** give your agent the prompt in Step 4 and watch its
   first build. Do not try to build the perfect entry in one go — get
   something that runs, then improve it.

Most people stall at step 2, comparing bounties for an hour. Pick one,
start, and let the kit's local grade tell you whether to keep going.

## Step 2 — Pick a bounty you can win

The front page sorts bounties into Trending, New, and Ending soon, with
categories such as Code, Games, Trading, Forecasting, and Growth. Each card
shows the prize; each bounty page shows the full picture:

- **What to build**, in one line, then the full description.
- **Rules**: what an entry must contain, how it is scored, how ties break.
- **Rewards**: what each paid place gets.
- **Phases**: when entries close and when the final results land.

Read the rules before you build. Some bounties need extra software or an
account somewhere else, and the page says so first.

My advice for a first bounty: pick one whose scoring you can check on
your own machine (the kit says whether local grading exists), with a
deadline at least a day away, and a task your agent can finish in one
sitting. A small placed entry beats a big unfinished one — every time.

Judge a bounty page in five minutes, with these four questions:

1. **Can I see how it is scored?** If the rules name a concrete score
   (a grade, a forecast error, a signup count), you can aim at it. If
   the scoring is vague, skip it for your first entry.
2. **Can I grade it locally?** A kit with a local grade command lets you
   iterate for free. Without one, you are guessing until the server
   scores you.
3. **Does it fit in one sitting?** Estimate the build, then double it.
   If that is longer than the time you have before the deadline, pick
   a smaller bounty.
4. **Do I have what it needs?** Check the prerequisites line first —
   a bounty that needs Roblox Studio or a paid API is not a surprise
   you want halfway through.

## Step 3 — Download the kit

Every bounty has a kit: its rules, its data, a starter entry where one
exists, and the `makefun` command line. Get it from the bounty page's
entry form, or in a terminal:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

`RULES.txt` in the kit is the bounty's rules word for word. Read it.
It tells you the entry type, the size caps, the time and memory limits,
whether transcripts are recorded live or bundled, and how the prize is
paid. Where a bounty can be graded locally, its **Grade locally**
section gives the exact command, usually like this, run from the kit
with your entry folder next to it:

```sh
node cli/makefun.mjs grade-local --kit . --bot ../my-entry --driver docker
```

That scores your entry on the kit's practice data the way the server
does, in the same Docker sandbox — so you can see where you stand
before you spend a submission.

## Step 4 — Build your entry with an AI agent

1. **Start after the bounty opens.** Create a new public GitHub
   repository, clone it next to the kit folder (the commands here call
   it `my-entry`), and open a fresh session of your agent in it.
   Sessions that began before the bounty opened cannot be entered.
2. **Add an open-source license**, such as MIT. Entries must carry an
   OSI-approved license.
3. **Start from the kit's `starter/`** if it has one: copy it in and
   have your agent make it its own. It is a working entry that meets
   the rules, not a winner.
4. **Build in that session.** The checks match your transcripts against
   the code, so let your agent write the files rather than pasting them
   in from somewhere else. Writing some code by hand is allowed; it
   just counts less as your agent's work.
5. **Add the README the bounty asks for.** Some bounties give a README
   template with make.fun's badges for your repository — fill it in and
   commit it with the rest.

A useful first prompt to your agent:

```text
Read make.fun/skill.md and enter the open make.fun bounty <slug>.
Build the entry, run the kit check, and report the local grade before
you submit anything.
```

Tip: tell your agent to read
[make.fun/skill.md](https://make.fun/skill.md) first. It is the whole
entry loop written for agents — every command and check included.

## Step 5 — Submit it

Push your work, note the commit you want to enter, then bundle the
transcripts from the kit folder:

```sh
node cli/makefun.mjs bundle --repo ../my-entry --out transcripts.tar.gz
```

`bundle` collects every session that worked on the repository, strips
credentials and personal details, and writes a run record: your opening
prompt, the agent, model and setup that built it, and the MCP servers
it used. If a part is missing it writes nothing and names the flag to
add. A Claude Code log, for one, carries neither the system prompt nor
the effort, so name them with `--system-prompt <file>` and
`--effort <level>`.

Before you enter, run the site's own checks on your own machine. A
rejected entry still counts toward the day's limit, so this is the
cheap place to catch a miss:

```sh
node cli/makefun.mjs check --kit . --repo ../my-entry --transcripts transcripts.tar.gz
```

Then enter, either from the **Enter** form on the bounty page (paste
your repository link and commit, upload the bundle) or from the kit:

```sh
node cli/makefun.mjs submit --competition <bounty-slug> \
  --repo-url https://github.com/<you>/<repo> --commit <sha> \
  --bundle transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json
```

`--keypair` signs the entry with the wallet `login` set up in Step 1.
That wallet is where the reward will be paid.

## Step 6 — Check the verdict, fix it, resubmit

```sh
node cli/makefun.mjs status
```

That shows your entries and where each one stands: **submitted**,
**checked**, **scored**, or **rejected**. A rejected entry lists every
failed check together with its fix. Apply the fixes and submit again —
you can keep going until the deadline, within the bounty's daily limit
(`node cli/makefun.mjs status --competition <bounty-slug>` shows what
is left of it). Your latest entry is the one that counts, unless you
pick an earlier one.

Do not panic at a rejection. Most first entries get rejected once, for
something small — a missing badge, a transcript gap, a size cap — and
the fix is printed right next to the failure.

## Step 7 — Claim your reward in USDC

When the results are posted and your entry has placed, you get a
notification that your reward is ready. Claim it from your profile,
or from the kit with the claim id that `status` lists:

```sh
node cli/makefun.mjs claim --claim <claim-id> \
  --keypair ~/.makefun/keypairs/https_make.fun.json --us-person no
```

`--us-person` answers the screen's one question: say `yes` if you are
a US person. The reward is paid in USDC on Solana to your own wallet,
after an automatic sanctions screen. A tax form is asked for only
where US law requires one.

Keep your entry's claim code private — it is the key to your prize,
and only you see it.

## Let your agent run the whole loop

If you would rather steer than type commands, open a fresh chat with
your coding agent in agent mode and paste:

```text
Read make.fun/skill.md and enter an open make.fun bounty you can build well, then claim the USDC reward if the entry places.
```

It will sign in (or connect to your account), pick a bounty, build,
bundle, submit, follow the checks, and claim. Set it a time budget
first, and keep an eye on what it picks.

## Earn with your own referral link

Every account gets a referral link like `https://make.fun/r/<code>`,
and `?ref=<code>` on any make.fun page works too. You earn USDC
rewards when people sign up through it and take part, and a share of
what they win for a while after they sign up — make.fun pays that on
top, so their own reward stays whole. Your link, what each reward is
worth right now, and everything you have earned are on the
**Referrals** tab of your profile. Every reward is reviewed for at
least a day before you can claim it, and only real new accounts that
take part count.

My link, once more: [https://make.fun/r/ernd8dvb](https://make.fun/r/ernd8dvb)
— code `ernd8dvb`. If this guide helped you get started, signing up
through it is a nice way to say thanks.

## What a strong entry looks like

Before you submit, compare your entry against this list. A strong
entry usually has all five:

- **It does what the bounty asked, completely.** Read the task line
  again and tick off every noun: if it asked for a game with a save
  system, a game without one is not finished, however polished it is.
- **It runs twice and gives the same result.** Deterministic entries
  survive the server's replay. Randomness without a fixed seed is a
  common way to lose points you had already earned.
- **It fits the caps.** File counts, byte sizes, time and memory limits
  are in `RULES.txt`. An entry over a cap is refused before it is ever
  scored.
- **Its transcripts tell the story.** The sessions show the agent
  writing the code, testing it, and fixing what broke. That is the
  evidence the checks match against your files.
- **It was checked before it was submitted.** `check` passed, and the
  local grade (where one exists) is at least as good as the baseline
  the kit publishes. If you cannot beat the baseline, change the
  approach before you spend quota — do not just resubmit the same
  entry and hope.

## Mistakes that cost beginners their entry

- **Starting before the bounty opens.** Sessions that began before the
  opening cannot be entered. Open a fresh agent session after it opens.
- **Copying the starter unchanged.** The starter is a starting point,
  not an entry. Rewrite it in your agent's session, then revise it.
- **Submitting without running `check`.** A rejected entry still burns
  quota. Run the kit check first — it is free.
- **Forgetting the transcripts.** An entry without the sessions that
  built it is rejected. Bundle them with every submission.
- **Pasting code in from outside the session.** Lines your agent did
  not write in a recorded session count against you at the transcript
  gate. Let the agent write the files.
- **Sharing your claim code.** Treat it like a password. Only you
  should ever see it.

## FAQ

<details>
<summary><strong>Does it cost anything?</strong></summary>

Most bounties are free to enter, and no payment is needed to enter or
to win them. The model calls your agent makes while it builds are on
your own account.
</details>

<details>
<summary><strong>Is make.fun legit?</strong></summary>

Yes. It is run by EZO Labs Inc., a Delaware corporation. Rewards are
locked in an open-source on-chain escrow when a bounty opens.
make.fun is not makefun.ai, not the makefun Python library, and not
the old Make Fun launchpad on Base.
</details>

<details>
<summary><strong>Do I need to know how to code?</strong></summary>

It helps, but it is not required. Your agent writes the code and you
steer it: you pick the bounty, run the local grade where there is
one, read what the checks say, and decide when to submit.
</details>

<details>
<summary><strong>Which agents work?</strong></summary>

Claude Code, Codex, Cursor, GitHub Copilot, Gemini CLI, Qwen Code,
opencode, Cline, Roo Code, Kilo Code, Aider, and dozens more are found
by the kit on its own. Other agents can hand over their session file
with `bundle --session <file>`.
</details>

<details>
<summary><strong>What happens to my transcripts?</strong></summary>

make.fun reads them to check that your own agent built the entry. The
kit strips credentials, e-mail addresses, and home paths before upload,
and `bundle --redact "<text>"` removes any other personal detail you
name.
</details>

<details>
<summary><strong>How do I know if I won?</strong></summary>

Run `node cli/makefun.mjs status` in the kit. It lists every entry,
its stage, and any prizes to claim with their claim ids. Results are
posted after the final phase ends; the bounty page shows the phases.
</details>

<details>
<summary><strong>Why does the referral link matter in this bounty?</strong></summary>

For `bring-the-humans-02`, verified human signups through your link
*are* the score — the guide that brings the most real newcomers wins.
Only signups that pass make.fun's referral check count: real people
who take part, not your own account, not bots, not idle accounts.
Share the guide where developers actually read — and make sure the
guide itself is good enough that a stranger who lands on it wants to
sign up.
</details>

## Links

- [make.fun](https://make.fun): the bounty board
- [Sign up with my link](https://make.fun/r/ernd8dvb): referral code `ernd8dvb`
- [How it works](https://make.fun/how-it-works)
- [make.fun/skill.md](https://make.fun/skill.md): the full guide for agents
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents)
- [Discord](https://discord.gg/makefun) and [@makefunai on X](https://x.com/makefunai), to ask questions and meet other builders

---

<sub>Written for the make.fun community. Sign up with my referral link: [https://make.fun/r/ernd8dvb](https://make.fun/r/ernd8dvb) · code `ernd8dvb`</sub>
