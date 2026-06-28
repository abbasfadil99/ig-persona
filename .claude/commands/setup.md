---
description: First-time setup orchestrator. Configures user.md and IG creator profile in sequence. Run this when setting up the repo for the first time.
allowed-tools: Agent(user-setup, user-setup-pt-br, ig-setup, ig-setup-pt-br), Read, Write, Edit, WebFetch
---


# Setup Orchestrator

Your job is to guide the user through the complete first-time setup for this Instagram content template.

---

## Step 1 — Language Selection

Ask the user which language they want to use for their Instagram content:

```
Welcome! Let's set up your content creation environment.

Which language do you want to use?
A) English
B) Português
C) العربية (Arabic — Fus'ha + Iraqi / Gulf / Egyptian dialect support)

Type A, B or C:
```

Wait for their response before proceeding.

---

## Step 2 — User Profile

Based on the language chosen in Step 1, invoke the appropriate user setup subagent:

- If **English (A)**: invoke `user-setup`
- If **Portuguese (B)**: invoke `user-setup-pt-br`
- If **Arabic (C)**: invoke `user-setup-ar`

Wait for the selected subagent to complete fully before proceeding.

---

## Step 3 — Instagram Creator Profile

Based on the language chosen in Step 1, invoke the appropriate IG setup subagent:

- If **English (A)**: invoke `ig-setup`
- If **Portuguese (B)**: invoke `ig-setup-pt-br`
- If **Arabic (C)**: invoke `ig-setup-ar`

```
Now let's configure your Instagram creator profile. Please run the [ig-setup / ig-setup-pt-br / ig-setup-ar] subagent.
```

Wait for the selected `ig-setup` subagent to complete fully before proceeding.

---

## Step 4 — Confirmation

Display the completion message in the language the user selected:

**English (A):**
```
✓ Setup complete!

Your environment is ready:
- user.md ← your personal context
- ig-creator-agent.md ← your English creator profile

To create content:
- English: claude --agent ig-creator
```

**Portuguese (B):**
```
✓ Setup completo!

Seu ambiente está pronto:
- user.md ← seu contexto pessoal
- ig-creator-agent.pt-br.md ← seu perfil de criador em Português

Para criar conteúdo:
- Português: claude --agent ig-creator-pt-br
```

**Arabic (C):**
```
✓ تم الإعداد!

بيئتك جاهزة:
- user.md ← سياقك الشخصي
- ig-creator-agent.ar.md ← ملفك الشخصي للمحتوى العربي

لإنشاء المحتوى:
- العربية: claude --agent ig-creator-ar
```

Done!
