# 🧠 Attention-Based Dynamic Chunking System (ABDC)

## 🎯 Purpose

This system replaces fixed “chunk size processing” with a **dynamic attention-driven selection mechanism** that decides:

* what information matters right now
* how much of it should be processed
* at what depth it should be processed

Instead of slicing data into fixed chunks, it continuously selects a **working set of events** from a stream.

---

# 🧩 1. Inputs

The system receives a continuous stream of events:

```text id="in1"
Event Stream = {
    sensory events (vision, audio, etc.),
    memory events,
    internal thoughts,
    system signals
}
```

Each event has minimal structure:

* content (what happened)
* source (vision, memory, etc.)
* timestamp (implicit or explicit)
* metadata (optional)

---

# ⚙️ 2. Attention Scoring Layer

Each event is evaluated continuously and assigned a score:

```text id="sc1"
attention_score(event) =
    relevance_to_current_context
  + goal_alignment
  + emotional_weight
  + novelty
  + recency_factor
  + prediction_error
```

### Meaning of components:

* **relevance** → how useful it is right now
* **goal_alignment** → supports current objective
* **emotional_weight** → urgency / importance
* **novelty** → unexpected or new information
* **recency** → recent events get boost
* **prediction_error** → how “surprising” it is

---

# 🧠 3. Dynamic Selection (instead of chunking)

Instead of choosing a fixed number of events, the system selects based on **attention budget**.

### Core idea:

> There is a limited “processing capacity”, not a fixed chunk size.

```text id="sel1"
working_set = select(events) where:
    sum(attention_weight) ≤ compute_budget
```

So selection is:

* adaptive
* importance-driven
* context-sensitive

NOT fixed-size.

---

# ⚖️ 4. Compute Budget Controller

This replaces “chunk size”.

It decides **how much can be processed right now**.

```text id="bud1"
compute_budget =
    base_capacity
  × complexity_factor
  × urgency_factor
  × system_state_modifier
```

### Behavior:

* low complexity → large working set (shallow processing)
* high complexity → small working set (deep processing)
* high urgency → prioritize fewer but important events

---

# 🔍 5. Working Set Formation

The result of attention selection:

```text id="ws1"
Working_Set = {
    top-N weighted events (dynamic N),
    ordered by importance score
}
```

Important:

* this is NOT a “chunk”
* this is a **temporary cognitive focus field**

It exists only for processing.

---

# 🧠 6. Depth Control (optional refinement step)

Each event in the working set can be processed at different depths:

```text id="depth1"
processing_depth(event) =
    attention_score × available_budget
```

### Meaning:

* high importance → deep analysis (memory + reasoning + planning)
* low importance → shallow awareness only

---

# 🔁 7. Continuous Update Loop

This system runs continuously:

```text id="loop1"
1. receive event stream
2. score all events
3. compute budget
4. select working set
5. process selected events
6. update memory + state
7. repeat
```

No discrete “chunks” exist anymore — only rolling selection.

---

# 🧠 8. Role of Memory in this system

Memory participates in two ways:

### ✔ As input:

* recalled events enter stream
* influenced by relevance and decay

### ✔ As scoring influence:

Memory affects:

* relevance score
* emotional weight
* prediction error

So memory is NOT separate — it is embedded into attention dynamics.

---

# ⚡ 9. Key properties of this system

## ✔ Adaptive

Processing adjusts automatically based on situation.

## ✔ Continuous

No hard boundaries between “chunks”.

## ✔ Priority-driven

Important information naturally dominates processing.

## ✔ Scalable

Works for:

* simple tasks (few events)
* complex tasks (dense streams)

---

# 🧠 10. Simple conceptual summary

If you want the simplest mental model:

> The system does not divide information into chunks.
> Instead, it assigns importance to everything and processes only what fits within available cognitive capacity.

---

# 🚀 11. Where this fits in your full architecture

This module sits here:

```text id="arch2"
Event Stream
      ↓
🧠 Attention-Based Dynamic Selection
      ↓
Working Set (variable)
      ↓
Memory / Planning / Action Systems
```

It is the **bridge between raw experience and cognition**.
