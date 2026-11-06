---
name: build-automation
description: Build, change, run or repair an automation with Untopple. Use when someone asks for an automation, a workflow, a recurring or scheduled task, something that should happen on its own, or when an Untopple run failed or a workflow needs fixing.
---

# Build an automation with Untopple

Untopple builds and runs automations on a remote pod. The Untopple tools do the work; this skill says how to use them.

If the Untopple tools aren't available, the connector isn't signed in yet. Ask the person to connect it: in Claude Code, run `/mcp` and pick untopple; in the Claude app, open the plugin's Connectors tab and choose Connect.

## How to work

1. **Read the guide first.** Call `get_guide` before anything else: `start` for a new automation, `workflow` when writing one, `debug` when one is broken. The guide is kept up to date on the server, so follow it over anything you remember.
2. **Understand before building.** Ask what the person is trying to achieve, not only what they asked for. Write it down in `contract.md`, one section per workflow.
3. **Research, then check on the pod.** Explore with your own tools if you like, but check every source from the pod, because sites treat it differently. When a wrong result would look right, such as a ranking or a search across many sites, do the job once and agree the result with the person before you build; the workflow must then reproduce it.
4. **Build in a draft.** Every change happens in a draft from `start_draft`. Submit it when it works: submitting makes it live, so test it first.
5. **Show the result.** When you start a run, give the person its `watch_url`. Use `show_workflow` and `show_run` to show what you built and what happened, and give them each file's `download_url` when a run makes files they want.

## Things to keep in mind

- Build the workflow only through the Untopple tools. Local scripts are fine for exploring, but never as the automation itself.
- Use code wherever a rule is reliable, and a model only for free text no rule reads well. The model reads, code checks its answer and decides.
- Secrets never pass through you. When a service needs an account, call `request_connection` and give the person its `setup_url`.
- Leave the pod out of tool calls to use the default pod, unless the person names another.
