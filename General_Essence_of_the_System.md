### General Essence of the System

This is a system where participants (miners) compete in the creation and evaluation of digital works (code, 3D-models, etc.). It is built on the principle of a "zero-sum game": if one participant wins points, the other loses them. This creates constant competition.

There are three types of participants:

1.  **Generators:** Create works according to the task.
2.  **Discriminators:** Evaluate anonymous works and vote for the superior one.
3.  **Validators:** Organize the entire process, create tasks and baseline works.

### Three Types of Tasks

The system uses three types of tasks to check miners from different sides.

**1. Synthetic Task**

*   **Goal:** To check whether miners can create works no worse than a high-quality baseline from the validator.
*   **Process:**
    1.  The validator creates a task and makes a baseline work itself.
    2.  One miner-Generator creates its own work.
    3.  The rest of the miner-Discriminators anonymously see both works and vote for the one that is better.
*   **Score Allocation (the most important part, "zero-sum game"):**
    *   The total sum of points for the task = 1.
    *   **Discriminators** who voted for the **validator's work** divide 1 point among themselves. Each receives `1 / n` (where `n` is the number of all discriminators).
    *   **Discriminators** who voted for the **generator miner's work** receive `0` points.
    *   The **Generator** receives all the points that *did not go* to the discriminators. The formula: `1 - sum(of_all_discriminators_scores)`.
    *   **In simple words:** If the discriminators recognized that the validator's work is better, they take almost all points, and the generator receives little. If the generator's work was so good that many discriminators voted for it, they receive 0, and the generator takes almost all points for itself. The Generator and the Discriminators are opponents.

**2. Organic Duel**

*   **Goal:** To create direct competition between two miners.
*   **Process:**
    1.  The validator gives a task to two miner-Generators.
    2.  Both create a work.
    3.  Discriminators vote for which work is better.
*   **Score Allocation:**
    *   **All Discriminators** divide 1 point among themselves. Each receives `1 / n`. They do not lose points; their task is simply to participate in the voting.
    *   **Generators** receive points depending on the number of votes they gathered. The Generator with the higher quality work will receive more votes and, consequently, more points.

**3. Control Round / Trap Round**

*   **Goal:** To punish inattentive, incompetent, or dishonest Discriminators. This is a check *of the discriminators*, not the generators.
*   **Process:**
    *   **Task Creation and Work Receipt:**
        1.  The validator creates a task and sends it to **two random Generators**.
        2.  Both Generators honestly execute the task and send their works. They do not know that this is a "trap" and try to do well.
    *   **Substitution of the Result by the Validator (key moment):**
        1.  **The validator receives both works from the Generators.**
        2.  **Then the validator intentionally spoils, distorts, or worsens ONE of these works.** It creates a knowingly bad, "negative" version.
        3.  Now the validator has:
            *   The original, good work from the first Generator.
            *   The spoiled, bad work, created by the validator itself based on the second Generator's work.
    *   **Voting:**
        *   The Discriminators are shown these two works for voting: one good (from the Generator) and one spoiled (created by the validator). The Discriminators do not know which work is whose and that one of them was substituted.
*   **Score Allocation (only penalties):**
    *   **For Discriminators:**
        *   A **Penalty (`-0.4` point)** is imposed on any Discriminator who votes for the **spoiled work**.
        *   Discriminators who voted for the good work receive neither points nor a penalty. They simply performed their work correctly.
    *   **For Generators:**
        *   **Both Generators** receive neither points nor a penalty for this task. Their work in this round is not evaluated for reward, because one of the works was distorted by the validator. The goal of the round is not their competition.

**Why This is Needed:**

This mechanism is like a "control purchase" or a "check for professional suitability" for Discriminators.

*   **Check of Attentiveness:** If a discriminator cannot distinguish an obviously bad work from a good one, they are incompetent and receive a penalty.
*   **Fight Against Blind Voting:** Some dishonest discriminators may collude to always vote for "their own" or, conversely, always vote against the validator. Here, the validator substitutes a knowingly bad work, and if a discriminator votes for it (for example, because they agreed to do so with their "partner"-generator), they are caught and penalized.

### Explanation of the Graphics

On the graphics, `n = 10` is the number of Discriminators who participated in the voting.

*   **First Graphic (left):**
    *   This is an example of a **Synthetic Task**.
    *   There is a **Generator** that received `0.3` points.
    *   There are **Discriminators** (`that voted validator` — those who voted for the validator). Each black circle is one vote. There are 9 votes for the validator.
    *   **Calculation:**
        *   Each of the 9 discriminators received `1 / 10 = 0.1` points. In total, they took `0.9` points.
        *   The Generator received `1 - 0.9 = 0.1` points. (*Note: on the graphic, the generator has `0.3` indicated, which could be an example of another scenario where there were fewer votes for the validator, for example, 7, and then the generator would have received `1 - 0.7 = 0.3`*).

*   **Second Graphic (right):**
    *   This is an example of an **Organic Duel**.
    *   There are two Generators: **A** and **B**.
    *   **Generator A** received `0.7` points because 7 discriminators voted for it (`7 * (1/10) = 0.7`).
    *   **Generator B** received `0.3` points because 3 discriminators voted for it (`3 * (1/10) = 0.3`).
    *   All 10 discriminators also received `0.1` points each for participation.

### Conclusion: Why All This is Needed?

1.  **Incentives for Quality:** Generators are forced to constantly improve their works to win votes and earn points.
2.  **Control of Honesty:** Discriminators must be attentive and objective. If they vote thoughtlessly or collude, they will be caught in the "Control Round" and penalized.
3.  **Fight Against Collusion:** The "zero-sum" system and random "traps" make it economically unprofitable to collude with each other. Honest and strong miners can always displace those who try to cheat.

The entire system works as a continuous competition where the best and honest participants receive rewards, and the bad or dishonest ones lose them.

