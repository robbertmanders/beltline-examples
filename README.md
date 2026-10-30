# Beltline examples

Example belts and agents for [Beltline](https://github.com/robbertmanders/beltline). Beltline ships none of its own: a new install lists this repository under **Settings → Library repositories**, and you install what you want from the **Library** page.

The repository is laid out like a Beltline library:

```text
belts/<id>/v<n>.json
agents/<id>/v<n>.md
```

## Belts

| Belt | Trigger | Stages |
| --- | --- | --- |
| `issues`: Issues to pull requests | GitHub issues labelled `agent` | Triage, Spec, Approve, Build, Verify, Ship, Merge; then Wrap up once merged, or Resolve conflicts and Fix checks back to Merge |
| `reviews`: Pull request reviews | Review requests for you | Review, Post review |
| `jira`: Jira tickets to pull requests | `project = KEY AND labels = agent` | As the issues belt |
| `epics`: Epics to tickets | `issuetype = Epic AND labels = beltline` | Plan, approve, open the feature branch, file a wave of tickets, watch the epic, assess, then the next wave or land it |
| `tasks`: Tasks | Tasks you start | Spec, Approve, Build, Verify, Ship, Merge |
| `nightly`: Nightly test sweep | Weekdays at 06:30 | Build, Verify, Ship, Merge |

A belt installs paused: shared belts name no repositories. Open it, add your repositories (and change the label, query or schedule to yours), save, and resume it. Installing a belt also installs the agent versions it uses.

## Agents

Triage, Spec, Build, Verify, Ship, Wrap up, Resolve conflicts, Fix checks, Review, Post review, and the epic agents Plan the epic, Open the feature branch, File the wave, Assess the epic, Replan the epic and Land the epic. Each runs on Pi with a placeholder model; choose one you allow before you resume a belt.

## Contributing

Share a belt or agent from Beltline (**Share…** on its page) to open a pull request here. A saved version never changes: change an item by adding its next version. Check a change with `beltlined --check-library <clone>`; a belt without repositories is expected to report that.
