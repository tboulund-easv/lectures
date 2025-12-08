---
theme: neversink
transition: fade
routerMode: hash
lineNumbers: true
record: true
---

# Code Reviews

## Beyond the Bare Minimum

---

# The "LGTM" Trap

The emoji representing "looks good to me" (LGTM) is familiar, but receiving it can carry a negative connotation.
If received too quickly, it suggests the reviewer wants to "just get it over with".
Eventually, seeing this quick approval without reason becomes a problem.

We must look at code reviews through two lenses: the **reviewer** (who approves the code) and the **author** (who prepares the changes).

<center>
<AutoFitText :max="200" :min="100" modelValue="👍🏻"/>
</center>

---

# Reviewer Failures: What We Are Doing Wrong

Ineffective reviews often stem from focusing on the developer rather than the code.

**Key Mistakes**

* Leaving ego out of the door
* Focusing on the developer
* Skimming reviews
* Writing ineffective comments
	* Subjective
	* Unclear
	* Lacking an outcome

<!--
*   **Leaving Ego Out of the Door:** Seniority or expertise can lead reviewers to give a more scrutinous eye to junior developers, which is "absolutely wrong".
*   **Focusing on the Developer:** Allowing the person making the change to influence the review process. Studies show that using second-person pronouns (e.g., "you did X, Y, and Z") makes comments more likely to be impolite.
*   **Skimming Reviews:** Due diligence is skipped when reviewers have too many PRs or feel bottlenecked. This often happens when PRs are "gargantuan," making proper review impossible.
*   **Writing Ineffective Comments:** These are frustrating for authors and prolong the review process due to back-and-forth communication. Ineffective comments are typically:
    *   **Subjective:** "Return the result in array instead. *Why?*".
    *   **Unclear:** "This could be better. *Why?*".
    *   **Lacking an Outcome:** "I think there's something wrong here".
-->

---

# Fixing the Review Process

To improve, reviewers must focus on the code and not the person. If conflict exists with the developer, that is a separate issue that should not be brought into the PR.

## Principles for Effective Reviews

*   **Focus on the Code:** Comments should focus on the technical aspects and the pull request itself, which are more likely to be labeled non-toxic.
*   **Proper Reviews:** Review code in focused bursts of 25 to 45 minutes to maintain attention.
*   **Obtain Full Context:** Take the conversation offline if necessary, especially if three or four comments online aren't resolving the discussion.

## The Goal: Write Effective Comments

Effective comments are **objective**, as **specific** as possible, and have a **focused outcome**.

When asking for a change, ask yourself *why* you are making that request; this mental introspection helps you articulate your needs better or determine if the change is necessary at all.

---

# Introducing the Triple-R Pattern

The triple-R pattern is a structured approach to writing effective comments and requests. Studies on code review comments found that the most useful comments often contain a verb that denotes transformation, such as "rework," "reorganize," "move," or "rename".

The pattern ensures that feedback is objective, specific, and drives a clear result.

---

# Triple-R Components

The **Request** is a sentence that explicitly explains the action the reviewer wants the author to take.

The **Rationale** consists of the facts and reasoning justifying the requested change. It provides the context as to why the change is being requested.

The **Result** is a measurable end state that the author should achieve after implementing the change.

---

# Triple-R Example: Moving a Method

**Request**
"Please move the `authenticate user` method into our utilities library."
The required action.

**Rationale**
"There are similar methods we have, and we use this a few times, so this warrants its place in the library. Our team working agreement advises us to put these kinds of methods in that particular library." 
Justification based on usage and team policy.

**Result**
"After this change, the `authenticate user` method should be in the authentication utilities library rather than stand alone."
The explicit, measurable outcome.

---

# Why Triple-R Makes Sense

Using the Triple-R pattern shifts comments away from being subjective, unclear, or lacking a defined outcome.

## Benefits of Structured Feedback:

1.  **Improves Reviewer Articulation:** Asking yourself for the rationale behind a request helps you "better articulate" *why* you are asking for the change.
2.  **Prevents Miscommunication:** By writing an effective comment, the conversation is likely to be more productive, avoiding the need for back-and-forth discussions where meaning can be "lost in translation".
3.  **Drives Clarity:** The pattern forces reviewers to be clear about what needs to be done and define the explicit goal, reducing ambiguity for the author.
4.  **Reduces Prolonged Processes:** Effective comments prevent conversations that otherwise "prolong the code review process".