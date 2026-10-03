# Bidding simulator

> A 2D web-based abandoned storage auction game. Play online with up to 6 friends per room.

Scan dark storage units with a flashlight, read your rivals, bid the right number, and find out whether you just bought treasure or trash.
Units are packed with Thai-flavored vintage finds, from old country-music vinyl and 90s toys to one-of-a-kind originals drawn by other players.

*"Godang" comes from โกดัง, the Thai word for warehouse.*

---

## 🎮 Concept

**Core loop**

```
Scan the unit → Bid → Open it up → Sell your finds → Upgrade → Move on to bigger units
```

- **Flashlight scouting**: A short time limit and a narrow beam. Reading a unit is a skill, not just luck.
- **Number-only bidding**: No chat, no typing. Every decision is a number.
- **Haggling with numbers**: NPC buyers have hidden budgets and distinct personalities. You get a limited number of counteroffers; push too hard and they walk.
- **Authenticate or get burned**: Some items are fakes. Inspect them yourself or pay an expert.

## ✨ Features

### Multiple auction formats
| Format | How it works |
|---|---|
| Open auction | Players outbid each other; every new bid resets the countdown |
| Sealed bid | Everyone submits one bid at the same time; all bids are revealed together |
| Dutch auction | The price starts high and keeps dropping; first to press wins |

### Online play for 2–6 players
- **Team mode (Co-op)**: Pool your money and compete against NPCs together. Each player scouts a different corner of the unit and shares intel through quick signals 👍 👎 💎 🛑, then the team votes on a price ceiling.
- **Party mode (Versus)**: Bid against each other. Richest player after a set number of days wins.
- Join rooms with a 6-digit code, no account required.
- Reconnect to your room after a dropout; an AI plays conservatively on your behalf in the meantime.

### NPC rivals with personalities
Each rival has their own bidding style and tells, like the hot-headed tycoon who loves driving up prices or the auntie collector who only fights hard for antiques.

### Player-made items *(planned)*
- Draw pixel art in-game (small canvas, limited palette) and turn it into a sellable item.
- Every item gets a **single, unique serial number** and a full ownership history.
- Copies of existing works are detected and tagged as **forgeries**, which become part of the gameplay.
- Creators earn an in-game currency royalty every time their item changes hands.
- Trade in the lobby marketplace using **in-game currency only**.

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Frontend | HTML5 Canvas + Phaser (2D pixel art) |
| Hosting | Cloudflare Pages / itch.io |
| Multiplayer | Cloudflare Workers + Durable Objects (one room = one Durable Object) |
| Realtime | Hibernatable WebSockets |
| Database | Cloudflare D1 |

**Design principles**
- **Authoritative server**: True item values, balances, and auction results live on the server only.
- NPC behavior is driven by formulas and probability in code. No LLM calls during gameplay.
- Content (items, descriptions, NPC lines) is generated ahead of time and stored as data files.
- Built to run within free-tier quotas in the early stages.

## 🗺️ Roadmap

- [ ] **v0.1 Single-player prototype**: Bid against 3 NPCs, flashlight scouting, opening units, selling
- [ ] **v0.2 Balance**: 40 items, economy and upgrades, balance tuning via bot simulations
- [ ] **v0.3 Online**: 2–6 player rooms, team mode, open and sealed-bid auctions
- [ ] **v0.4**: Party mode, Dutch auctions, reconnect support
- [ ] **v0.5 Player-made items**: Pixel art editor, serial numbers, forgery detection, lobby marketplace, reporting system

## 📜 Content Policy

- Parody is limited to public-domain artworks (e.g. the Mona Lisa) and the game's own characters.
- No real people's faces, real logos, or copyrighted characters.
- In-game brands are original parody brands.
- Player-made items are subject to reporting and moderation.
- No real-money trading.

## 🤝 Contributing

The project is in its early stages. Ideas, bug reports, and pull requests are welcome. Feel free to open an issue.

## 📄 License

To be determined.
