---
title: Bun protocol
prev_section: communication.html
next_section: dashboard.html
---

The Bun Protocol
================

The Bun protocol is a lightweight, decentralised request routing protocol. It is designed to be the simplest possible way to handle requests that are shared by a distributed group of people. We use it mostly to handle incoming client requests.

> We introduced this at Organa after seeing how effective it was at Nomad8.

The metaphor
------------

![Sia's Home baked Kanelbulle! Yum!](../assets/Bun.jpg "Sia's Home baked Kanelbulle! Yum!")

When a bun (= issue or request) comes in, it's warm, juicy and soft. If it sits around for a day it gets a little cold, perhaps a little dry. If it sits around several days it becomes dry, hard and stale. You can warm up an old bun in the microwave oven as long as it hasn't become too dry.

So, a bun should be eaten fairly quickly or thrown away. No use stuffing it in a box. If you can't eat it yourself, offer it to someone else - before it gets cold, dry and hard!

Sample buns
-----------

-   You get an email "Hey there, interested in Agile product coaching at company X. What will it cost and when can you come?". You have a bun.
-   You meet someone at conference who says "I want to join your company". You have a bun.

How the protocol works
----------------------

A bun is born when someone asks you for something and you decide that "hey, this is a bun". 

**A bun always has an owner** - the person who received the bun. Or more specifically, the person responsible for the communication channel through which the bun appeared, eg: you're responsible for any emails sent directly to you.

**When you have a bun, you are responsible for taking care of it before it gets too dry.** Preferably within 1 working day, definitely within 2.

You have 3 options:

-   **Eat it yourself.** eg: "Sure, I'd love to offer some agile product coaching". The bun is now consumed; it has found a home and will not be routed anywhere.
-   **Give it to somebody else.** eg: to a colleague who is more suitable than you, or even another  company if you want. If you don't know exactly who should take it, broadcast it out over our Slack channel: "Hey peeps, anyone interested in taking this bun?". Note that the bun remains yours until someone else takes it. This is a really important rule that we follow. Allow a day at least so that Members have time to react, but if that takes more than a couple of days you need to keep the bun warm (eg: go back to the potential client and let them know you're searching for someone who can help). Importantly, you can't push the bun to someone, you can only offer it. The receiver has to pull the bun from you.
-   **Throw it away.** eg: someone emails me "Can you come and teach a product pricing course?". I answer "No" (politely of course). Or I answer "No, we don't do product pricing courses, but I recommend you speak to Ms ProductPricingPeep, she's amazing and knows this area". That still counts as throwing away the bun, since I let it go and won't follow it up. Someone else might take it out of my garbage, but I don't need to know or care if that happens :o)

The one thing you should NOT do is just let the bun sit and dry. Better to explicitly throw it away in that case (ie tell the sender kindly that we can't help).

So initially a buns appears through a "push" protocol; the initial recipient gets the bun whether he wants to or not. After that, however, everything is "pull"-based.

Summary of the rules
--------------------

-   **As receiver of a bun you are responsible** until it is eaten by you, taken by someone else, or thrown away. If several people are interested, sync with them.
-   **A bun should not get more than 1-2 days old** without being eaten by somebody, thrown away, or reheated (by talking to the customer/sender).
-   **You can't push a bun onto someone else, they have to pull**. The bun is yours until someone else explicitly takes it. You can of course recommend (or even try to convince) someone else to take it from you. This goes both ways - if someone offers you a bun, you don't have to respond if you aren't interested.
-   When in doubt:
    -   Broadcast a message to everybody who might be interested or involved in this bun.
    -   Send the bun to "upwards" to someone on the Board (eg: if the bun seems to be strategic and might lead to a big dinner).
-   **When broadcasting to find interested bun-takers, give your colleagues one day** to indicate interest in the bun. Don't just let the first one that answers have the bun. There might be others interested. Letting the first one that answers having the bun leads to race conditions and might cause tension between colleagues.

We don't always succeed in following these rules, especially the 1-2 day age limit. But we really try our best, and we're at least aware of when we fail.

Why it works
------------

We're still new with this but Crisp and Nomad8 have used the protocol for years and it works well. Here are some reasons:

-   **Nice metaphor** - buns are good :o)
-   **Simple**, anybody can learn it in 5 minutes.
-   **Can be extended** as needed. New rules can be added, tool support can be added. But try not to; keep it simple and add stuff only if you really need it.
-   **Doesn't require specific artefacts** or documents that need to be maintained (unless you add that layer yourself).
-   **Decentralised** - uses "wisdom of the crowds" to ensure that buns reach the right destination in the shortest possible time with the least possible effort. 
-   **Client focused** - clients normally get a response within a reasonable time.
-   It **promotes trust and collaboration**, and avoids bottlenecks and command & control.
-   It is **Lean** - we minimise work in progress and maximise flow by ensuring that buns are handled quickly and don't pile up in queues. Woohoo, that's minimising waste and stress in the system.
-   We **still have the option to centralise & escalate** on a case-by-case basis. If someone bumps into a bun that needs to be escalated to some central authority then that can be done immediately.

FAQ
---

### Does this work for all types of requests?

We don't know. But it has worked well enough so far, and we haven't come up with any kind of request where it wouldn't work.

### What if several people want the same bun?

If several people are interested in the same bun, they talk to each other and sort it out.

Strictly speaking, the first person to take the bun has it, so in theory we do have a race condition. In practice, however, when a potential conflict arises the involved people talk to each other and decide on who should take the bun, based on who can serve the client best, who needs the bun most, and other relevant factors.

So being the bun holder doesn't really mean "this is MY client", it means more like "I'll make sure this gets taken care of".

The [conflict handling process](conflict-handling.html) helps solve edge cases.

### But what if I accidentally throw away an important bun!?

Example: Client X calls you and says they needs agile coaching. You respond "Very sorry, but I can't help right now." But you didn't know that Sarah is available and could have taken this client, and you didn't know that Customer X was an important strategic customer. Ouch.

You shouldn't have thrown away that bun. 

Many clients are forgiving so you can always get back in touch with them as fast as you can, apologise and speak honestly about what happened. You never know!

Breathe. Don't go chucking things out too quickly. Always consider the Slack channel first. Live & learn.


### Why not forbid people to throw away buns?

Sure, we could do that if we were scared of potentially losing clients or scared our Members won't do the right thing. But fear comes with a price tag. Remember we practice trust, we're competent and if we designed processes for every edge case, we'd be just like those organisations we once worked for. 

### What about traceability?

Buns have a home in the Organa Client Funnel Trello board.

### How do we avoid buns falling through the cracks

Be clear in your communication. Short, clear phrases like:

-   "Who will take this bun?"
-   "I'm taking the bun."
-   "I will throw this bun away if nobody takes it by Tuesday".


### What are the potential disadvantages of the bun protocol?

-   Requires discipline and trust from everyone involved. But we want that anyway.
-   No built-in traceability and visibility. Hence the Trello board.
-   Slightly silly metaphor :)
