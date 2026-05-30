# Telegram Shop Bot

A professional Telegram shop bot using **python-telegram-bot v21** and **MongoDB Atlas**.

## Important security note
Your bot token and MongoDB password were shared in chat. Rotate your Telegram bot token in **@BotFather** and change the MongoDB database password before production use.

## Features included
- Main user menu: products, Canva, referral, methods, deposit, support, hidden admin panel
- Product system: add products, add stock, edit price, stock out, sales stats, instant delivery
- Bulk discounts: 2 = 5%, 5 = 10%, 10 = 15%
- Referral system: REF user links, instant points, referral count
- Canva system: points redemption and USDT manual purchase flow
- Deposit system: limits, payment methods, screenshot upload, admin approve/reject, history records
- Admin panels: products, payments, channels, contacts, admins, settings, broadcast, stats, tickets, coupons, users, backup/export
- Broadcasts: all, active, specific users, scheduled
- Exports: users, orders, products, payments, referrals CSV
- Auto-backup: daily JSON backup
- Security: anti-flood/rate limit, suspicious activity logging, banned users
- Analytics: DAU/WAU/MAU, revenue, AOV, top products, pending deposits, referrals
- Support tickets and quick admin replies
- Coupons/promotions database and admin creation
- Multi-language basics: `/lang en`, `/lang ur`, `/lang ar`

## Setup

```bash
cd telegram_shop_bot
python -m venv .venv
source .venv/bin/activate   # Linux/Mac
# .venv\Scripts\activate    # Windows
pip install -r requirements.txt
cp .env.example .env
nano .env
python main.py
```

## .env fields

```env
BOT_TOKEN=your_new_bot_token
MONGODB_URI=your_mongodb_uri
DATABASE_NAME=telegram_shop_bot
ADMIN_IDS=7103729427,6555089031
OWNER_IDS=7103729427,6555089031
BOT_USERNAME=YourBotUsername
BACKUP_DIR=backups
```

## Admin product formats

Add product:
```text
Netflix Premium | 10 | user1:pass1,user2:pass2
```

Add stock:
```text
Netflix Premium | user3:pass3,user4:pass4
```

Payment method:
```text
USDT TRC20 | Txxxxxxxxxxxxxxxxxxxx
```

Channel:
```text
@channelusername | Channel Name | yes
```

Coupon:
```text
SAVE10 | percent | 10 | 2026-12-31 | 100
```

## Notes
- Manual USDT/crypto deposits are supported through screenshot approval.
- Stripe/PayPal/SendGrid/SMS webhook integrations are scaffold-level requirements; add live API keys and endpoints before real automatic payments/emails/SMS.
- For high-volume stock delivery, replace the simple stock pop logic with MongoDB transactions.
