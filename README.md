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