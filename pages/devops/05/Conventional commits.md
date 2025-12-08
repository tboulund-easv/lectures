---
theme: seriph
transition: fade
routerMode: hash
lineNumbers: true
record: true
---

# Conventional commits

A specification for adding human and machine readable meaning to commit messages.

---
layout: full
---

# Bad commits
<style scoped>
  blockquote {
    margin-bottom: 20px;
  }
</style>

The following commits are from the whatthecommit.com tool that generates commit messages randomly.

<v-clicks>

> Pro Tip: Use Copilot more

> Revert "just testing, remember to revert"

> fixed shit that havent been fixed in last commit

> Haiyaa

> added security.

> It's getting hard to keep up with the crap I've trashed

> REALLY FUCKING FIXED

</v-clicks>

---
layout: center
---

# Why they don't work

- ❌ Are emotionally charged or unprofessional
- ❌ Provide almost no technical detail
- ❌ Give no insight into what changed
- ❌ Are inconsistent and unpredictable
- ❌ Not useful for changelogs
- ❌ Slow down troubleshooting, onboarding, and auditing

---
layout: center
---

# Conventional commits to the rescue

This specification suggests a basic structure for commit messages:

> &lt;type&gt;[optional scope][optional breaking mark]: &lt;short description&gt;

Let's consider each of the elements (type, scope, description) one by one before looking at some examples.

---
layout: full
---

<style scoped>
  td, th { padding: 6px 6px; margin: 6px 6px; }
</style>

# Types

<table>
  <thead>
    <tr>
      <th><strong>Type</strong></th>
      <th><strong>Description</strong></th>
    </tr>
  </thead>
  <tbody>
    <v-click><tr>
      <td><span v-mark="{ at: 10, color: 'orange', type: 'circle' }">fix</span></td>
      <td>patches a bug in the codebase</td>
    </tr></v-click>
    <v-click><tr>
      <td><span v-mark="{ at: 10, color: 'orange', type: 'circle' }">feat</span></td>
      <td>introduces a new feature into the codebase</td>
    </tr></v-click>
    <v-click><tr>
      <td><span v-mark="{ at: 11, color: 'cyan', type: 'circle' }">build</span></td>
      <td>changes that affect the build system</td>
    </tr></v-click>
    <v-click><tr>
      <td><span v-mark="{ at: 11, color: 'cyan', type: 'circle' }">ci</span></td>
      <td>changes to your CI/CD configuration files and scripts</td>
    </tr></v-click>
    <v-click><tr>
      <td><span v-mark="{ at: 11, color: 'cyan', type: 'circle' }">perf</span></td>
      <td>performance improvements</td>
    </tr></v-click>
    <v-click><tr>
      <td><span v-mark="{ at: 11, color: 'cyan', type: 'circle' }">refactor</span></td>
      <td>code changes that neither fix a bug nor add a feature</td>
    </tr></v-click>
    <v-click><tr>
      <td><span v-mark="{ at: 11, color: 'cyan', type: 'circle' }">docs</span></td>
      <td>documentation only changes</td>
    </tr></v-click>
    <v-click><tr>
      <td><span v-mark="{ at: 11, color: 'cyan', type: 'circle' }">style</span></td>
      <td>changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)</td>
    </tr></v-click>
    <v-click><tr>
      <td><span v-mark="{ at: 11, color: 'cyan', type: 'circle' }">test</span></td>
      <td>adding missing tests or correcting existing tests</td>
    </tr></v-click>
  </tbody>
</table>

---
layout: center
---

# Scopes (optional)
Not defined by the specification, but commonly used to provide additional contextual information about the commit.

> For example, if a developer is working on a web application with multiple components such as the login system, user profile, and settings page, they can use scopes like login, profile or settings to indicate which part of the application the commit is related to. This helps other team members and future contributors understand the purpose of the commit without having to inspect the actual changes right away.

---
layout: center
---

# Breaking changes (optional)
Use `!` after the type/scope to indicate a breaking change.

## Examples
- `feat(login)!: change password hashing algorithm`
- `fix!: drop support for Node 10`