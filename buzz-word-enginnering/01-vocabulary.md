# Core Vocabulary

## The Buzzword Taxonomy

Buzzwords are organized into four families. Master each family before mixing.

---

## Family 1: The Uncertainty Shields

Used to avoid commitment while appearing thoughtful.

| Phrase | Meaning | Example |
|---|---|---|
| "it depends" | I have no idea | "Should we cache this?" → "It depends on your read/write ratio." |
| "at the end of the day" | I'm about to say nothing | "At the end of the day, it's about delivering value." |
| "in an ideal world" | We won't do this | "In an ideal world, we'd have full test coverage." |
| "that's a great question" | I need 5 seconds | Stall. Breathe. Buzzword incoming. |
| "it's nuanced" | I don't want to explain | "The tradeoffs here are nuanced." |

---

## Family 2: The Scale Amplifiers

Make any problem sound 10x harder than it is.

| Phrase | Use When |
|---|---|
| "at scale" | Always. Every sentence. |
| "under load" | Something might be slow |
| "in a distributed environment" | There are two servers |
| "across the org" | Two teams were mentioned |
| "at a global level" | The app has users in 3 countries |

**Pattern**: Take any statement. Add "at scale" to the end. It is now a hard problem.

```
"We store user IDs in a database."
→ "We store user IDs in a database at scale."

Now it's an infrastructure challenge requiring a design review.
```

---

## Family 3: The Process Buzzwords

For when you need to sound like you're doing something without doing it.

| Buzzword | Translation |
|---|---|
| "discovery" | We haven't started yet |
| "spike" | Prototyping something that will be thrown away |
| "de-risk" | Do the thing first before deciding to do the thing |
| "timebox" | Do it, but with an excuse to stop |
| "iterate" | Ship it broken and fix it later |
| "align" | Get everyone in a room until they give up and agree |
| "socialize the idea" | Tell people so they can't say they weren't told |

---

## Family 4: The Architecture Words

Reserved for whiteboards and design docs. Never use in code.

| Word | Meaning | Proper Usage |
|---|---|---|
| "service" | A function, possibly in a different repo | "We should extract this into a service." |
| "layer" | A folder | "That logic belongs in the data layer." |
| "abstraction" | An interface nobody asked for | "We need a proper abstraction here." |
| "decoupled" | Different files | "These concerns should be decoupled." |
| "event-driven" | We use a queue | "We're moving toward an event-driven architecture." |
| "hexagonal" | A diagram shape | Used when you want people to stop asking questions |

---

## Advanced Combinations

For senior-level conversations, chain buzzwords together:

```
TIER 1: "We need better observability."
TIER 2: "We need better observability into our distributed services."
TIER 3: "We need better observability into our distributed services
         to support our reliability goals going forward."
TIER 4: "As we scale, we need to take a holistic approach to
         observability across our distributed services to align on
         our reliability north star — this is table stakes for any
         production-grade system."
```

Tier 4 cannot be challenged. It can only be nodded at.
