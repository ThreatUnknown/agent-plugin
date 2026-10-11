---
name: run-a-security-agent
description: Use when the person wants something checked, rescanned or fixed in a Threat Unknown organization, asks to start, follow or answer a Threat Unknown agent, or asks what a Threat Unknown agent run did or is waiting for.
---

# Running a security agent

Follow the `threat-unknown-safety` rules throughout. You never scan or change the
organization's services yourself. You start one of our agents, which does the work on the
person's authority, and you follow it.

## 1. Check what is already running

Call `list_agent_sessions`, with `kind` set to `"assessment"` or `"remediation"` when you
know which you want. If a matching run is active, offer to follow it rather than start
another.

## 2. Pick the agent

- **Assessment**: looks at one connected platform and records findings. Changes nothing in their services.
- **Remediation**: proposes changes to one platform, and makes them only after they are
  approved.

## 3. Ask first

Tell the person which agent you would start and what it will do: which platform, whether it
can propose changes. Wait for their yes. It runs on their authority against their live
services.

Never guess an agent's name: a real name starts that agent at once. If you do not know the
exact name, call `launch_agent_session` with `templateSlug: "?"`. That starts nothing and
answers with the agents that exist. Some listed agents may still be refused for this
person's role.

## 4. Start it

Call `launch_agent_session` with the exact `templateSlug` of the agent the person agreed to.
Leave `force_create` out.
- If the answer has `alreadyRunning: true`, no new run started. You got the existing
  run's session. Follow that one. Pass `force_create: true` only if the person, told that a
  run is already going, asks for a second.
- Give the person the `sessionUrl` so they can watch it in Threat Unknown.
- A refusal says why, for example their role cannot start that agent. Relay it and stop.

## 5. Follow it

Call `read_agent_session` on the session id. Read the tool calls as well as the messages:

- A `present_choices` call means the agent is waiting on a choice. The options are in its
  `choices` argument and appear nowhere in the messages. The message just before it holds
  the question.
- A `request_approval` call means a change is waiting. Use the `review-pending-approvals`
  skill.
- A session can look idle while it waits on one of these. Check before you say it stopped.

Runs take time. Read again when the person asks for an update rather than in a tight loop.

## 6. Answer its questions

Tell the person the agent's question and its options, in plain words, and get their answer.
Then call `send_session_message` with the text of the option they chose, exactly as the
agent wrote it. For a free-text question, send their answer in their words.

Only send what the person decided. Do not answer the agent's questions yourself, even when
the answer seems obvious.

The message can be refused: the person is speaking in that session themselves, the session
is not waiting on an answer, or it needs something only Threat Unknown's own screens can
send. Relay the refusal and do not retry. Only a reply that says the message was sent means
the agent has it.

## 7. Report

Say what the agent did and what it found, from the session. Say what is still waiting on the
person. Do not report a fix as done until a later scan shows the finding as `pass`.
