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


## v0.45 Real class responsive/color fix
- Corrected previous CSS patches to target the app's real class names: `.timeCard`, `.boardPanel`, `.battlefield`, `.mapCell`, `.letterTile`, and `.deployControls`.
- Added early color-scheme/theme-color metadata for iframe/browser rendering.
- Rebuilt responsive rack sizing so letters do not crop and buttons remain right-aligned.
- Hard-locked dark Wordfront colors across Discord web and desktop.


## v0.46 Neon tile/design fix
- Restored neon green/purple map tile styling using real class names.
- Strengthened browser/Discord-web dark palette lock.
- Adjusted rack/deploy controls to avoid overlap while preserving responsiveness.


## v0.47 Dark UI final polish
- Restored darker original Wordfront palette.
- Restored neon green/purple board and rack tile styling.
- Reduced board sizing so it no longer clips into rack.
- Adjusted deploy controls to avoid overlap.


## v0.48 Board polish
- Made board letters smaller so stability numbers remain readable.
- Softened 2X tile brightness.
- Restored single-dot empty grid cells.
- Fixed Clear/Deploy button overlap with an even control grid.
- Added left-panel height/padding fixes so the bot card no longer clips.


## v0.49 Contested + clear button fix
- Added contested tile styling matching the legend.
- Softened 2X tile styling so placed letters stay readable.
- Fixed Clear/Deploy controls so Clear is no longer clipped.


## v0.52 Stable recovery
- Recovered from v0.50 black screen by rebuilding from stable v0.49.
- Kept complete Clear/Deploy button fixes.
- Added safe reconnect/session reattach support.
- Added server-side bot difficulty logic with safe default medium.
- Optional bot difficulty can be tested with URL query: `?bot=easy`, `?bot=medium`, `?bot=hard`, or `?bot=godlike`.


## v0.55 Clean difficulty build fix
- Rebuilt from stable v0.52 instead of broken v0.53.
- Added required Solo vs Bot difficulty modal cleanly outside the error block.
- Medium bot tuning is 5–7 letters.
- Verified the client builds successfully with Vite.
