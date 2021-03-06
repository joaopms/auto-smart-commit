## Auto Jira smart commit

---

_The original version has more features like time-tracking. See https://github.com/radix-ai/auto-smart-commit_

---

This [pre-commit](https://pre-commit.com/) hook transforms your Git commit messages into [Jira smart commits](https://confluence.atlassian.com/fisheye/using-smart-commits-960155400.html).

If your branch name contains a [Jira issue key](https://confluence.atlassian.com/adminjiraserver073/changing-the-project-key-format-861253229.html) such as `ABC-123`, the hook will automatically format your commit message into a Jira smart commit:

| Command | Log entry |
| ------- | --------- |
| git commit -m "Release the kraken" | ABC-123 \| Release the kraken |


If the branch name does not contain a Jira issue key, the commit message is not modified.

See [How to Write a Git Commit Message](https://chris.beams.io/posts/git-commit/) for an explanation of the seven rules of a great Git commit message:

1. Separate subject from body with a blank line
2. Limit the subject line to 50 characters
3. Capitalize the subject line (automated)
4. Do not end the subject line with a period (automated)
5. Use the imperative mood in the subject line
6. Wrap the body at 72 characters
7. Use the body to explain what and why vs. how

## Installation

Add the following to your `.pre-commit-config.yaml` file:

```yaml
repos:
  - repo: https://github.com/joaopms/auto-smart-commit
    rev: v1.1
    hooks:
      - id: auto-smart-commit
```

and make sure to run `pre-commit install --hook-type prepare-commit-msg` to install the hook type necessary for this hook.
