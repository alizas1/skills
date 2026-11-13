---
name: user-test-plan
description: >-
  Write a test plan for a product, feature, service, document or process: one
  that tests how its real users will use it, which is never only the expected
  way, as well as whether it works. Covers choosing the users and how each one
  behaves, what to test them on, writing down what should happen before
  anything runs, agents that play the users, cost and safety rules, when to
  stop, and a write-up that records every step, confusion and wrong turn. Plans
  only: nothing runs until the requester approves. Use for "test plan", "plan a
  test", "how should we test this", "test this with different users", "user
  test plan".
---

# User test plan creation

Writes a plan for testing a subject with the people who will really use it. The plan is the output. Nothing in it runs until the requester approves it.

The plan covers two kinds of test:
- **Does it work:** each step a user takes is checked against what the docs, the design or the spec say should happen.
- **How people really use it:** a separate agent plays each kind of user, with that user's own temperament, and uses the subject the way that person would, including the wrong ways. Most findings come from this part.

The plan sets out:
- what the test is for, in the requester's words
- the facts gathered first: what's already been tested, how the subject actually works, what each try costs, and what a new user meets first
- who the users are, where each one comes from, and how each one behaves
- what each user is given to try, including some cases where the answer is already known
- what should happen at each step, written down before anything runs
- who plays whom, the budget, the safety rules, the order, and when to stop
- what the test can't tell

When the test runs, it produces:
- a step log for each session: every step in order, with every error, confusion point and wrong turn
- a chain log for each person a result gets passed on to
- a friction log across all sessions
- a report: findings with a severity, accuracy, and each user's verdict
- a list of fixes, none applied without the requester's approval

## Language

| Word | What it means here |
|------|--------------------|
| **Requester** | The person asking for the test plan |
| **User** | Someone the subject is for. Users come from the requester's materials |
| **Subject** | Whatever is being tested: a product, a feature, a service, an app, a document or a process |
| **Tester** | Whoever runs the test and checks the results. Usually the agent using this skill |
| **User agent** | A separate agent that plays one user |
| **Session** | One user's go at the subject, from the first look to what they do with the result |
| **Case** | What a user is given to try in a session: an input, a scenario, an environment or some content |

## How to use this skill

Ask for a test plan and say what's being tested. Point to anything that describes its users: personas, research, interview notes, support tickets, analytics. The skill works out what the test is for, gathers the facts, chooses the users and what to test them on, and writes a plan to review.

## 1. Find out what the test is for

People want test plans for different reasons:
- to check that something works before a release
- to see how new users get on
- to compare how different kinds of users use it
- to find where people misuse it or get stuck
- to check that a fix worked

Each one leads to a different plan. Write down in one or two sentences what this test is meant to find out. Show it to the requester before designing anything.

Two kinds of test often get mixed up:
- **Does it work:** the expected path, checked step by step.
- **How will people really use it:** the tester becomes each kind of user and uses it the way that person would. That is never only the way the docs or the design expect, and the off-path uses are where most findings are.

When it isn't clear which one the requester wants, or the request can be read more than one way, lay out the readings in plain words and ask. Don't pick one. When they explain further, rebuild the plan around what they said, in their words. Don't patch the old design.

## 2. Gather the facts before the plan

Check before assuming. Each fact goes into the plan with where it came from and when it was checked.

- **What's already been tested.** List it, so the new test covers new ground.
- **How the subject actually works.** If the source, code or configuration can be read, read it. Predictions in the plan should come from it. Example: "There is no field for the user type, so who the user is can only change what they put in."
- **What each try costs** and what is free. Example: tries that are rejected straight away aren't charged.
- **What a new user meets first.** Open the real starting point the way a stranger would: the website, the signup, the first screen, the first page of the docs. Problems found here are findings before the test begins.
- **Anything still unknown that changes the design.** Name it, and make finding it out the first step of the order.

## 3. Choose the users

- **Take them from what the requester already has:** personas, research, a customer list, interview notes. Don't invent them. Say where each one came from. If there's nothing, ask before making any up, and mark any made-up user as made up.
- **Base each user's temperament on what they're measured on, what they care about and ignore, and how much time they have.** Don't add a random quirk. For each user, write:
  - what they read or do first
  - when they stop
  - what makes them trust a result
  - what makes them stop trusting it
- **Don't flatten anyone into a cartoon.** "Wants numbers" is a cartoon. "Cares about the big problems and ignores small ones a helper would fix on the spot" is a person. When unsure what a user cares about, ask the requester.
- **Spread the temperaments:** impatient, detail-oriented, skeptical, not technical, short on time, literal. Each one should come from a real kind of user.
- **Don't treat some users as more important,** for example "the buyers", unless something has proven it. A guess built into the test can't be tested by it. Let behavior show who matters instead (section 7).
- **Say plainly that the temperaments are guesses** until someone checks them with real people.

## 4. Choose what to test them on

- **Give each user a different case to try:** a different kind of input, scenario, environment or content. Prefer kinds that have never been tested.
- **Include some cases where the answer is already known,** such as a real problem someone has already found. Whether the test finds it is the strongest check on accuracy, for the thing being tested and for whoever plays the user.
- **Check that every case exists and can be reached** before the plan names it.

## 5. Plan the checks before anything runs

- **For every move a user might make, write down beforehand what should happen,** according to the docs, the design or the spec. Afterwards:
  - a different result is a finding
  - sources that disagree with each other are a finding
  - a result that matches but leaves the user unsure what to do next is a friction point
- **The list of likely off-path moves is for the tester, not for the user agents.** They never see it. If they did, they'd act out the list instead of finding their own way.
- **After each session, compare:**
  - moves the user made that aren't on the list are what the test is for
  - listed moves nobody made, the tester tries afterwards and marks as the tester's, not the user's
- **Check a sample of the results against the truth.** For example, check 3 findings per session against the source and mark each true or false.
- **Measure the noise before comparing.** If results can vary between identical runs, run the same thing twice first. Two users' results only differ meaningfully if they differ by more than that.

## 6. Who plays whom

- **The tester (lead)** sets up each session, writes the expected results, checks every response, and writes up the results.
- **One separate agent per user,** when agents play the users. Each gets only:
  - its user card
  - what the requester's materials say about that user
  - the starting point
  - the safety rules

  It doesn't get the plan, the expected results, the known answers, or other sessions. If one agent plays everyone, they all think alike and agree with the tester.
- **The model is the requester's decision.** Show the options with pros and cons:
  - **A strong model:** stuck points come from the subject.
  - **A cheaper model:** lower cost, but some stuck points may be the model's.
  - **A weaker model on purpose:** for a user who really is a weaker agent or a less capable tool.

  Playing a user is judgment work, not routine work.

## 7. What users do after the result

The test doesn't end when a result comes back. Plan for what each user does with it: share it, try again, argue with it, ignore it, or stop reading.

When a user would pass it on, the person they'd pass it to reads it next, as their own agent, and can pass it on again. Who ends up holding the result is evidence of who needs it.

## 8. Cost, safety and stopping

- **Budget:** the total cost, a limit per user, and what to check before starting (balance, nothing else running).
- **Secrets:** refer to them by name only. If a user would paste a secret somewhere, they paste a made-up one.
- **Nothing that reaches the outside world without the requester's approval:** no purchases, no account changes, no contacting anyone, no sending results to outside services. Notifications go only to an address the requester names.
- **Order:**
  1. the cheapest session with a known answer
  2. the other known-answer sessions
  3. the rest
  4. sessions that need their own setup
- **When to stop:**
  - the same failure twice in a row
  - the budget runs out
  - a user agent breaks a rule
  - something takes far longer than earlier runs

  Then stop and check with the requester.

## 9. The write-up

Treat the test like an inspection of the subject.

1. **A step log for each session.** One table, in the order things happened, from the first look to what the user did with the result.
   - Columns: Step, Topic, Action, Result (Success or Fail only), Detail
   - Step numbers always go up. A retry gets a new number.
   - Every action and response in full, every wait, every error, every confusion point (even ones the user worked out), every wrong turn, and where they stopped and why
   - A list of friction points at the top
2. **A chain log** for each person a result was passed to, with the chain of who passed it to whom.
3. **A friction log** across all sessions, with columns for:
   - session and step
   - who hit it
   - what should have happened and what did
   - cleared or not
   - how many sessions it came up in

   Findings from before the test go in too.
4. **A report:**
   - findings with a severity
   - known problems found or missed
   - accuracy
   - the noise check
   - uses nobody expected
   - each user's verdict: use it again, pay for it, pass it on and to whom
5. **A list of fixes,** one per finding. Nothing in it is applied without the requester's approval.

Say where each file goes.

## 10. Shape of the plan

1. Title, date, and what the test is for, in two or three sentences
2. Decisions so far: each question and the requester's answer, with the date, updated as they answer
3. What's already been tested, and is left out
4. What was found before the test
5. Who does what
6. Rules for the user agents
7. The sessions: one card per user, with their likely off-path moves and what should happen
8. Side checks, such as the noise check
9. How each session is checked
10. The write-up and where it goes
11. Cost
12. Order
13. When to stop
14. What this test can't tell

Put each open decision where it comes up, with its options and their pros and cons.

## 11. Before handing over the plan

- [ ] What the test is for is in the requester's words, not a narrower reading of them
- [ ] Every fact was checked, with a source and a date
- [ ] The users come from the requester's materials, and their temperaments from what each one cares about
- [ ] No user is treated as more important without proof
- [ ] The off-path moves are kept from the user agents
- [ ] The expected results are written before anything runs
- [ ] There is at least one known-answer case, and a noise check if results can vary
- [ ] The model, budget, outward actions and safety rules are shown to the requester as decisions, not chosen quietly
- [ ] What happens after the result is part of the test
- [ ] The write-up records every step, confusion and wrong turn
- [ ] What the test can't tell is written down
