# WHATSMORE — More Than Chat.

A working, clickable demo of the WHATSMORE chat app with a WhatsApp-style interface. It covers all 10 core features. It runs entirely in the browser: no install, no build step, no server.

## Run it

Double-click **`index.html`** to open it in Chrome, Edge, Safari or Firefox.

To get the microphone, camera and screen-sharing features, serve the folder over localhost:

```bash
python3 -m http.server 5173
```

Then open http://localhost:5173. The demo also works on a phone-sized screen. It switches to a mobile layout with bottom tabs.

Everything you do is saved in your browser. Use **Settings → Reset demo data** to start fresh.

## What to try

| # | Feature | Try this |
|---|---------|----------|
| 1 | **Private chat** 💬 | Reply, react, edit, delete, forward, pin or star a message (hover a message → ⌄, or right-click). Use the emoji, GIFs and stickers panel, voice notes (mic button), photos and docs (**+**), the scheduled message option (**+ → Schedule message**), **Lock chat** and **Disappearing messages** (choose *1 minute (demo)* to watch messages vanish). Open **⋮ → AI summary**. |
| 2 | **Voice & video calls** 📞 | Use the call and video buttons in any chat. They support mute, camera, background blur and screen share. **Calls → Create call link** makes a WHATSMORE Call Room. |
| 3 | **Groups & communities** 👥 | *Weekend Trip*: vote in the poll, pay the split bill, open **⋮ → AI summary**. **Communities** tab: an Announcements group where only admins can post. Group info has admins, members and descriptions. |
| 4 | **Stories & status** 📸 | **Status** tab: view stories (including a business offer), react or reply, and post your own with a privacy setting. |
| 5 | **Username connection** 👤 | **New chat** → search `@meera.designs` to send a chat request without a phone number. Settings → Profile changes your @username (checks it's unique). There's also **My QR code** and QR scanning. |
| 6 | **End-to-end encryption** 🔐 | Tap the yellow encryption note to see a security code. **Settings → Account & security** has the privacy dashboard, passkeys, 2-step verification and remote logout of sessions. |
| 7 | **AI assistant & translation** 🤖 | Chat with *Siva* (Telugu) or *Priya* (Hindi) and tap **Translate to English**. Tap the ✨ button in the message box to fix grammar or rewrite a message as formal or casual. Smart reply chips appear above the message box. |
| 8 | **Cloud & files** ☁️ | **Files** tab: type *“Show me the invoice Ramesh sent in January”*. Files are auto-sorted (Photos, Documents, Receipts, Invoices…), and there are storage plans. |
| 9 | **Payments** 💳 | **+ → Payment** to send, request or split a bill. Your history is in Settings → Payments. |
| 10 | **Business accounts** 💼 | *Sunrise Bakery*: ask *“What time do you open tomorrow?”* and the AI auto-replies. **+ → Catalogue → Order → Pay** gets you an invoice. |

## Important: this is a prototype

- **Other people are simulated.** Replies, typing indicators, votes and payments come from scripted bots. There is no backend and no real network messaging.
- **Encryption is shown, not implemented.** A production build would use the Signal protocol for 1:1 chats and Sender Keys for groups, with independent audits.
- **AI and translation are rule-based.** Production would use an on-device or privacy-preserving model.
- **Payments are fake.** No money moves. A real launch needs licensed payment partners and must follow local regulations, such as RBI and NPCI rules for UPI.

## Project structure

```
index.html          App shell
css/styles.css      WhatsApp-style theme (light + dark), mobile layout
js/icons.js         SVG icon set
js/data.js          Demo seed data (contacts, chats, stories, catalogue…)
js/core.js          State, storage, helpers, menus, modals, toasts
js/sidebar.js       Navigation rail, chat list, new chat, status, calls, communities, files
js/settings.js      Settings pages (profile, security, privacy, payments, plans)
js/chat.js          Conversation view, message rendering, composer, emoji panel
js/messaging.js     Sending, simulated replies, business bot, payments, polls, voice, AI
js/features.js      Chat actions, lock, forward, attachments, QR, call links, groups
js/overlays.js      Info drawer, stories viewer, calls, media viewer
js/main.js          Event wiring and startup
```
