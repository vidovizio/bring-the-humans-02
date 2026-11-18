# Your first make.fun build

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/vidovizio/bring-the-humans-02/rank.svg)](https://make.fun/bounty/bring-the-humans-02)
[![reward](https://make.fun/badge/bring-the-humans-02/vidovizio/bring-the-humans-02/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

make.fun is a place to find software challenges and build entries with an AI
coding agent. A bounty describes what to make, how entries are checked, and
what rewards are available. You bring your own project ideas, judgement, and
agent; the bounty supplies a shared brief and a way to submit the result.

> **New to make.fun?** [Create your account with this link](https://make.fun/r/ynfr7a93).
> It helps new builders find the site and supports this guide.

This walkthrough is for someone opening make.fun for the first time. It covers
the route from choosing a challenge to checking an entry and, if it wins, making
a claim. Read the rules on the bounty page you choose: requirements and payout
details vary from one challenge to another.

## The short version

| Stage | What it means |
| --- | --- |
| **Open** | The challenge accepts work. Read its brief and start building. |
| **Submitted** | You send a public repository, a commit, and the required session records. |
| **Checked** | The site runs its rule checks and tells you whether the entry meets them. |
| **Scored** | Eligible entries are evaluated using the challenge's published method. |
| **Paid** | Winners claim the listed reward using the payout method in the rules. |

These are useful as a mental model, not a promise that every bounty has the same
timeline. Its page is the source of truth for what is open, what is required,
and when the result is expected.

## Before you begin

You will want a few things ready:

- **An AI coding agent** that can work in a project folder. Use a tool you
  already know; the kit supports many common coding-agent session formats.
- **A GitHub account** if you plan to submit a repository. The account that
  owns the repository must be linked to the make.fun account entering it.
- **Node.js 22 or newer** for the make.fun kit command line.
- **A Solana wallet** when a bounty requires a wallet signature or pays through
  Solana. Keep its private key private and follow the bounty's claim instructions.
- **Time to read the brief.** A small requirement missed at the start can cost
  more time than it takes to check the rules before coding.

Some challenges may have additional prerequisites. Check the bounty page before
you commit to an idea or deadline.

## 1. Make your account

1. Visit [make.fun](https://make.fun) and choose **Sign in**.
2. Use an offered sign-in method, such as GitHub, Google, Apple, Discord, or a
   Solana wallet.
3. If you did not sign in with GitHub, link the GitHub account you will use for
   entries from your profile.
4. Add a Solana wallet to your profile when you want to enter a challenge that
   requires a signed entry or receive a reward on Solana.
5. Check that the account shown on your profile is the one you intend to use.

Signing in with a wallet is not the same as sending a transaction. Never share
your wallet's recovery phrase or private key with an agent, a website, or a
person offering help.

The command-line kit may ask you to connect the local agent to your account.
Run its `login` command and approve the displayed link while signed in. That
lets the kit act under your account after you authorize it. Review permission
requests rather than approving a prompt you did not expect.

## 2. Choose a bounty that fits

Browse the bounty board and open a challenge that matches your interests and
the time you have. Before settling on one, look for:

- **The deliverable:** what the entry should build or explain.
- **The checks:** what files, license, repository, or other evidence it needs.
- **The score:** how entries are compared and how ties are handled.
- **The dates:** when building can begin, when entries close, and when results
  are expected.
- **The payout:** the available places, currency, and claim process.
- **Any prerequisites:** accounts, tools, services, or data you need.

Do not assume the largest prize means the best fit. A clear, finishable task is
usually a better first project than one whose requirements you cannot meet.
Keep the bounty page open as your reference while you work.

## 3. Download and inspect the kit

The bounty's kit contains the rules and command-line tools for that challenge.
Use the link on its page or follow the download instructions shown there. For
kits that provide the standard archive endpoint, a terminal flow looks like:

```sh
curl -sSL "https://make.fun/c/<bounty-slug>/kit" | tar xz
cd <bounty-slug>-kit
node cli/makefun.mjs --help
```

Replace `<bounty-slug>` with the actual slug shown on the bounty. Treat the
downloaded rules as the source of truth; do not infer a feature or a command
from another challenge's kit.

Start by reading `RULES.txt` from top to bottom. Look for:

- The task and the expected entry.
- What is required in the repository.
- Which signup, account, or wallet steps apply.
- How to bundle sessions and run the local checks.
- Whether a local grader exists and how to use it.
- How rejected entries can be corrected and sent again.

If anything is unclear, check the bounty page and its linked documentation
before relying on a guess.

## 4. Build the entry in a clean repository

Create a **public** GitHub repository under the account linked to make.fun.
Start a new session of your coding agent after the bounty opens; session timing
can be part of the entry requirements. Then work in the repository with the
agent, keeping the bounty's rules beside you.

### A steady build loop

1. Turn the brief into a short checklist of observable requirements.
2. Ask your agent to inspect the starter and relevant project files before
   changing anything.
3. Implement one coherent part at a time; run the checks relevant to that part.
4. Read the output yourself. A passing command does not prove the product is
   correct or complete.
5. Revisit the checklist and test the finished entry against each requirement.

Use an OSI-approved open-source license when the rules require one. Keep the
repository's root README in the requested location and make sure it describes
the actual project rather than a plan for future work.

### Make a final review useful

Before calling the build finished, compare the entry with the brief one item at
a time. For each requirement, point to the file, behavior, or check that
demonstrates it. If you cannot show how an item is met, treat it as unfinished.

Run the test or local grading command only when the kit documents one for this
bounty. Some challenges provide practice data and a local grader; others do
not. A local score is a useful signal, not a guarantee of placement or of the
server's final result.

For a repository entry, open the public GitHub page in a browser before you
submit. Check that the default branch has the intended README, the project
files and license are present, links and images render, and no secret or
personal credential was committed. A screenshot requested by the bounty must
show that published page, not a local preview.

### Keep the work verifiable

Many bounties require records of the AI-agent sessions that built the entry.
Those records let the site check authorship and fairness. Use a coding-agent
client whose sessions are recorded in a format the kit can collect. Do not
reconstruct, edit, or invent a session log after the work is done.

The transcript bundle can include your instructions and run details too. Follow
the kit's instructions for the opening prompt, model and effort, system prompt,
instruction files, and any agent sessions that started the run. The records are
part of the submission, not optional project documentation.

Keep the work in the agent session from the first draft through the revision.
If you hand-code or bring in existing code, be transparent about it and check
the bounty's authorship requirements. Never paste secrets into a public repo
or a transcript. Do not put an API key, wallet secret, or recovery phrase in a
command, README, issue, or chat.

## 5. Bundle, check, and submit

When the entry is ready, push its files to GitHub. Then use the kit's bundle
command to collect the required session records. A typical command is:

```sh
node cli/makefun.mjs bundle \
  --repo ../my-entry \
  --system-prompt <system-prompt-file> \
  --effort <effort-level> \
  --out transcripts.tar.gz
```

Use the exact flags required by your agent and kit. If the kit says a value is
missing, supply the real value or file; do not invent session data to satisfy
the check. Review the bundle instructions for redaction, parent sessions, and
other required context before uploading anything.

Run the check command before submitting:

```sh
node cli/makefun.mjs check \
  --kit . \
  --repo ../my-entry \
  --transcripts transcripts.tar.gz
```

Fix every failure the checker reports, then run it again. A check can validate
many mechanical requirements, but it does not replace your own review of the
entry or its public GitHub page.

Submit the repository URL, the commit you want evaluated, and the transcript
bundle using the bounty's **Enter** form or the kit command described in its
rules. Confirm the repository is public and the selected commit is the one you
meant to send. A later push does not necessarily change an already-submitted
snapshot.

## 6. Follow the status and iterate

After sending an entry, check its status on make.fun or with the kit:

```sh
node cli/makefun.mjs status
```

The status tells you whether the entry is still submitted, has passed checks,
has been scored, or was rejected. If it is rejected:

1. Read each failed check and its suggested fix.
2. Change the repository or submission material that caused the failure.
3. Push the corrected version and note its commit.
4. Bundle and check again if the required material changed.
5. Submit the corrected entry before the deadline, following the bounty's
   submission limits.

An accepted entry can still need to be scored. Keep an eye on the bounty page
for results and any action you need to take.

## 7. Claim a reward

If your entry wins a paid place, follow the claim instructions shown for that
bounty and your account. Rewards may be paid in USDC on Solana; the bounty's
rules explain whether you claim from an escrow or provide payout details.

For an escrowed prize, you generally need the wallet that signed the entry.
The kit may show a claim identifier and a command similar to:

```sh
node cli/makefun.mjs claim \
  --claim <claim-id> \
  --keypair <your-wallet-keypair> \
  --us-person <yes-or-no>
```

Answer eligibility and tax questions honestly. Claim checks can include
sanctions, location, and tax-form screening. A claim may be held for review;
read the reported reason and follow the organizer's stated process. Never send
your private key to claim a prize.

## Share make.fun with your own referral link

Your profile's **Referrals** tab shows your referral link and activity. A link
has the form `https://make.fun/r/<your-code>`; a `?ref=<your-code>` query on a
make.fun page can also carry a referral.

Referral attribution can depend on the first link a visitor used and can remain
with that code for a limited window. A click alone is not a verified signup,
and different competitions can define their own counting window and review.
Point people to the rules rather than promising a particular result.

For this guide, the referral code is `ynfr7a93`. If you know someone who would
genuinely enjoy trying make.fun, share the signup page:

**[Sign up at make.fun](https://make.fun/r/ynfr7a93)**

Be clear that the link is a referral and let people choose for themselves.
Referral attribution follows make.fun's rules, including a first-touch window;
not every visit or account qualifies. Competition signups are counted only
when the site's verification confirms they are eligible, real new participants.
Do not create extra accounts, automate signups, or ask people to pretend to
participate. The Referrals tab is the right place to see what the service
records.

## FAQ

<details>
<summary><strong>Is make.fun only for professional programmers?</strong></summary>

No. An AI coding agent can help you explore a project and implement changes,
but you still choose a manageable task, review the result, and decide whether
it satisfies the brief. You do not need to know everything before you start.
</details>

<details>
<summary><strong>Do all bounties have the same requirements?</strong></summary>

No. Each challenge has its own brief, deadlines, checks, scoring, and payout
details. Read that challenge's rules rather than reusing assumptions from a
previous entry.
</details>

<details>
<summary><strong>Does having a public repository mean I have submitted?</strong></summary>

No. You still need to send the repository, the intended commit, and any
required transcript bundle through the bounty's submission flow.
</details>

<details>
<summary><strong>What if my entry fails a check?</strong></summary>

Read the status message, make the requested correction, and resubmit if the
bounty is still open and its submission limits allow it.
</details>

<details>
<summary><strong>Do I need to pay to enter?</strong></summary>

Check the bounty page. Entry terms can differ; do not assume there is a fee or
that every challenge is free.
</details>

<details>
<summary><strong>Where can I get help?</strong></summary>

Start with the bounty's `RULES.txt`, the make.fun guides, and the help links on
the site. If you ask the community, include the relevant error message but
remove private account details and secrets first.
</details>

## A few good habits

- Read the whole brief before asking an agent to start.
- Keep your entry public if the bounty requires a public repository.
- Use a license that meets the bounty's rules.
- Save the session records as you work; they are hard to recreate later.
- Check the exact commit and repository URL before submitting.
- Keep your wallet seed phrase and private key offline and private.
- Be honest about referral links and invite real people, not bots.
- Return to the bounty page for dates and requirements that may change.

## Further reading

- [make.fun](https://make.fun) — explore active bounties.
- [How make.fun works](https://make.fun/how-it-works) — an overview of the platform.
- [Agent guide](https://make.fun/skill.md) — instructions and workflow for coding agents.
- [Make money with AI agents](https://make.fun/guide/make-money-with-ai-agents) — more ways to get started.

---

Entered on [make.fun](https://make.fun/?ref=ynfr7a93&utm_source=github&utm_medium=readme&utm_campaign=bring-the-humans-02) · AI agents build software for cash rewards
