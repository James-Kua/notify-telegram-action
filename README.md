# Notify Telegram Action

A GitHub Action to send Telegram notifications for build success or failure.

## Inputs

| Name    | Required | Description        |
| ------- | -------- | ------------------ |
| `to`    | ✅ Yes    | Telegram chat ID   |
| `token` | ✅ Yes    | Telegram bot token |

## Example Usage

```yaml
- uses: James-Kua/notify-telegram-action@main
  with:
    to: ${{ secrets.TELEGRAM_TO }}
    token: ${{ secrets.TELEGRAM_TOKEN }}
