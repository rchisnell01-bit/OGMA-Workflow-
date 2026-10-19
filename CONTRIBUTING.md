# Contributing and field reports

The most valuable contribution right now is **a reproducible real-world test**, not another large framework.

To report your trial, open an issue in the repository and include:

- Which AI providers/chats you used (no account details).
- Whether you used manual relay or a tool you had already configured.
- The task type and whether a worker really acknowledged it.
- What the manager verified and where it failed.
- Any measured extra time or cost; use `UNKNOWN` when unavailable.
- The smallest edit that would have helped.

Use fictional or permitted inputs. Remove names, contact details, internal links, credentials, and private conversation logs before posting.

For a pull request, keep changes narrow and test the [guided demo](examples/five-minute-demo.md) against the intended flow. Explain any proposed expansion that adds dependencies, automated actions, or changed approval rules.

**Don't** remove approval gates, present simulated results as live evidence, or copy other creators' paid/proprietary prompt packs into this project.