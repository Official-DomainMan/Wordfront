# Wordfront MVP v0.18 Word-List Validator

This version fixes the dictionary problem by using the npm `word-list` package on the server.

## Run

Server:
```powershell
cd C:\Dev\wordfront-v018-wordlist-validator\server
npm install
npm run dev
```

Client:
```powershell
cd C:\Dev\wordfront-v018-wordlist-validator\client
yarn install
yarn dev
```

## v0.18 fixes
- Uses a large local English dictionary from `word-list`.
- Server-side validation applies to all players.
- SENT, GET, GOLF, GRAMS, HORN, and JOKER are included.
- Fake letter strings should still reject.
- Keeps the v0.17 UI cleanup.


## v0.19
- Fixed cut off WORDFRONT logo.
- Tightened left rail sizing.
- Cleaner gear-style menu button.
- Better responsive board scaling.


## v0.20
- Rebuilt UI to match the latest mockup more closely.
- Fixed cut-off logo.
- Restored full Surrender/Menu buttons.
- Fixed turn log layout.
- Improved board/rack proportions.


## v0.21
- Fixed left panel cards being cut off/overlapping.
- Separated bot card and turn log into their own grid rows.
- Kept Surrender/Menu as full buttons.
- Adjusted logo scale so it stays inside the left rail.


## v0.22
- Removed the Turn Log panel from the left rail.
- Removed strength numbers from board letters for cleaner readability.
- Board tile strength is available via hover tooltip.
- Left rail now keeps Lobby, Scoreboard, Bot card, Surrender, and Menu fitting cleanly.


## v0.23
- Fixed lobby card clipping so the Leave Lobby button is visible.
- Menu Return to Lobby now actually returns to the home/lobby screen and ignores old game broadcasts.
- Added a server leaveGame event so the client leaves the socket room.


## v0.24 Discord Activity Support
- Adds `@discord/embedded-app-sdk`.
- Adds `/api/auth/exchange` on the backend.
- Adds production static serving for the Vite build.
- See `DISCORD_ACTIVITY_SETUP.md`.


## v0.25
- Fixed Express 5 production fallback route error: `Missing parameter name at index 1: *`.
- Replaced `app.get('*')` with `app.use(...)` for client-side routing fallback.


## v0.26
- Discord Activity UI scaling pass.
- Smaller left/right rails to give the board more room.
- Fixed Leave Lobby clipping.
- Reduced board letter size inside tiles.
- Kept stacked Surrender/Menu buttons for Discord iframe fit.


## v0.27
- Current Rules reduced to two rules.
- Right panel compacted to remove empty space.
- Board letters made smaller.
- Fixed Deploy Word clipping.
- Moved invalid-move errors into a fitted bottom-right alert box.
- Discord Activity layout closer to the provided mockup.


## v0.28
- Smaller board letters, closer to the original web app look.
- Logo subtitle simplified to version only.
- Hidden visible Discord env warning from the logo area.
- Fixed Deploy Word button clipping.
- Added responsive scaling for smaller Discord windows.


## v0.29
- Fixed overlapping left/right/top/bottom panels.
- Made board letters smaller.
- Added cooler beveled/3D board tile styling.
- Improved body text font while preserving neon section headers.
- Kept bottom-right error box unchanged.


## v0.30
- Fixed game panels clipping/overlap in Discord-sized windows.
- Fixed Deploy Word button clipping.
- Added compact Discord-specific layout sizing.
- Added cooler beveled board tile styling.
- Added themed styling for the pre-game lobby/home screen.


## v0.31
- Fixed Railway production frontend trying to call localhost:3001.
- Production now uses the same Railway origin for Socket.IO and API calls.
- Solo vs Bot/Create Game buttons should work on the hosted Railway URL.


## v0.32 Postgres persistence
- Added optional Railway Postgres persistence using `DATABASE_URL`.
- Saves completed matches to `matches`.
- Saves cumulative player stats to `player_stats`.
- Adds `/leaderboard` and `/matches/recent` API routes.
- If `DATABASE_URL` is missing, the game still runs normally without persistence.


## v0.33 Perfect UI frame
- Reworked the game layout to match the approved mockup.
- Fixed cut-off side panels and top/bottom sections.
- Made Deploy Word fully visible.
- Improved board/card/rack spacing and visual hierarchy.
- Added responsive Discord embed fallbacks.


## v0.34 Rack/button polish
- Moved Clear and Deploy Word to the right side of the rack area.
- Fixed Deploy Word clipping.
- Added slight height/breathing room to Lobby card so Leave Lobby is not clipped.
- Left the rest of the v0.33 UI unchanged.


## v0.35 Async crash fix
- Fixed Railway crash caused by `await persistIfFinished(game)` inside a non-async socket handler.
- Removed unnecessary persistence check immediately after joining games.
- Keeps v0.34 rack/button UI polish.


## v0.44 Iframe responsive clean
- Rebuilt responsive CSS from stable v0.35.
- Uses true viewport-based iframe layout instead of fixed transform scaling.
- Rack tiles use fractional sizing so they cannot crop.
- Locks solid dark Wordfront colors across Discord web and desktop.
