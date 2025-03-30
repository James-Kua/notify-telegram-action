# Notify Telegram Action

A GitHub Action to send Telegram notifications for build success or failure.

## Inputs

| Name              | Required | Description                                                                   |
| ----------------- | -------- | ----------------------------------------------------------------------------- |
| `workflow_name`   | ✅ Yes    | The workflow name that will be shown to have passed/failed                    |
| `to`              | ✅ Yes    | Telegram chat ID (the recipient’s chat ID)                                    |
| `token`           | ✅ Yes    | Telegram bot token (from BotFather)                                           |
| `changed_files`   | ❌ No     | A custom list of changed files to include in the message                      |
| `message_format`  | ❌ No     | Message format for Telegram (markdown or html). Defaults to `markdown`        |
| `disable_preview` | ❌ No     | Disable web page preview (true/false). Defaults to `true`                     |
| `timezone`        | ❌ No     | Timezone for the datetime (e.g. Asia/Singapore). Defaults to `Asia/Singapore` |

## Example Usage

```yaml
  uses: james-kua/notify-telegram-action@main
  with:
    workflow_name: 'CI workflow'
    to: ${{ secrets.TELEGRAM_TO }}
    token: ${{ secrets.TELEGRAM_TOKEN }}
    changed_files: ${{ steps.changed-files.outputs.all_changed_files }}
    message_format: markdown
    disable_preview: true
    timezone: 'Asia/Singapore'
```


Sample telegram message

```
✅ Build storybook passed!

⏰ 30 Mar 2025, 04:38PM [Sunday]

📂 main

🧑‍💻 James-Kua created commit: Use new workflow (#26)

🗂 Changed files:
.github/workflows/ci.yml   .github/workflows/storybook.yml

🎯 Repository: James-Kua/RedditLite

👍 See changes: https://github.com/James-Kua/RedditLite/commit/0aa096308fefacf86cdf6a0e83416c9f6d3abf01
```