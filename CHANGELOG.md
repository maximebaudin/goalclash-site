# Changelog

Toutes les modifications notables de GoalClash sont documentées ici.
Format basé sur [Keep a Changelog](https://keepachangelog.com/fr/1.1.0/).

---

## 6 Fevrier 2026 (2)

### Features
- Redesign main menu with stadium theme and game mode cards (Training, Online, Ranked)
- Add bottom navigation bar (Boutique, Ladder, Streaming, Collection)
- Add FloatingEffect component for bobbing UI animations with phase offset
- Training card opens play mode popup (1P/2P) as overlay over menu

### Fixes
- Fix MatchList and StatsPopup displaying over game field instead of menu background
- Fix StatsPopup not showing on first click
- Fix MatchListCanvas blocking menu interactions when inactive
- Remove legacy MenuController (MainMenuUI handles all flow)
- Simplify level display to just the number

---

## 5 Fevrier 2026

### Features
- Make harpoon a hybrid projectile/channel power (hold to reel in)

### Fixes
- Balance: Increase Police (STOP) mana cost to 55 and reduce stop duration to 0.1s
- Balance: Reduce black hole duration from 4s to 3s and redesign visual
- Balance: Reduce goal shield duration from 3s to 1s
- Balance: Reduce ghost invisibility duration from 3s to 1.5s
- Fix attraction power not moving opponent in online mode
- Fix ghost power blinking in online mode
- Fix double tree spawn and player pushback on tree activation
- Fix tree power online spawn direction and player collision
- Fix boxer punch having no effect on ball in online mode
- Fix ball-player collision while punching (boxer)
- Align online power visuals with offline and mutualize sprite creation
- Add Procfile to limit Netty memory usage

---

## 4 Fevrier 2026

### Features
- Add 12 new powers support (server + client)
- Implement real-time online character selection
- Add heart visual effect to Attraction power
- Add homing potion for Scientist power
- Rework character selection UI for simultaneous 2-player selection

### Fixes
- Add CHARACTER_SELECT support for WebSocket (WebGL)
- Disable team color tint on player sprites
- Sync server power physics with client
- Sync online powers with local implementations
- Include SELECTING state in GameLoop tick
- Fix rate limiting bug blocking real-time selection sync
- Fix online flow: connect before character selection
- Nerf wind and adjust powerup box spawning
- Update Boxer power: reduced range and power
- Update GoalShield power: position at goal entrance
- Update BlackHole power: spawn at player position
- Update Police power: brief stop then ball falls
- Update Didier power: straight-line projectile
- Rework Ice power: chill instead of freeze
- Reset all power effects on round reset
- Rework Magnet power: aura effect, cost increase
- Fix player sprite flip in online mode (players now turn when changing direction)
- Fix P2 ready button in online character selection
- Fix tree collision in online mode (players can no longer pass through trees)
- Add tree sway animation in online mode

---

## 3 Fevrier 2026

### Fixes
- Fix missing HitboxDebugger methods after revert
- Revert physics and power-up box changes
- Update physics constants and add ball speed tuning

---

## 2 Fevrier 2026

### Features
- Add PowerUp box and wind system for online mode
- Add PowerUp box with wind effect (local mode)
- Add mana cost markers, balance adjustments
- Add team color tint to differentiate players
- Add mobile controls and Google auth client support

### Fixes
- Fix memory leak: ensure room data cleanup on all exit paths
- Fix spectator mode idle timeout disconnection
- Fix goal detection to trigger when entire ball crosses goal post
- Fix mana cost markers in online mode
- Fix team tint not working in 2 player mode
- Fix box spawning during matchmaking lobby
- Fix wind animation and box hitbox in online mode
- Fix players moving at start of round
- Fix ball collision cooldown to be per-player
- Fix ball tunneling through goal crossbar
- Fix duplicate game result reporting
- Fix API server memory leak
- Sync physics: semicircle collision

---

## 1 Fevrier 2026

### Features
- Add Google authentication to API server
- Add XP/Level UI system

### Fixes
- Fix arrow keys controlling both players in 2-player mode
- Fix R2DBC UUID parameter binding

---

## 31 Janvier 2026

### Features
- Add XP and level system for online matches

### Fixes
- Fix race condition in GameResultService
- Handle missing players gracefully
- Fix R2DBC @Param annotations

---

## 30 Janvier 2026

### Features
- Add spectator mode for watching live matches
- Add splash screen during authentication
- Add CORS support for web builds (itch.io)

### Fixes
- Fix spectator timeout: use WaitForSecondsRealtime
- Fix spectator mode for WebGL: add WebSocket support
- Fix memory leaks: cache JWT key, cleanup expired tokens
- Reduce R2DBC connection pool size

---

## 29 Janvier 2026

### Features
- Add player level to online mode matchmaking
- Add player name/level display in online mode
- Add Unity client authentication integration
- Add player endpoints and JWT authentication
- Add API Server Phase 2: anonymous authentication
- Add API Server Phase 1: reactive setup with WebFlux + R2DBC

### Fixes
- Add Procfile to limit JVM memory for Railway
- Fix UUID casting in repositories
- Fix Spring Boot plugin to create executable JAR

---

## 28 Janvier 2026

### Features
- Add ball landing feature to local mode
- Add ball-on-head feature
- Implement giant, teleport, swap powers on server
- Add HitboxDebugger and adjust goal hitboxes
- Add sound effects for online mode
- Add options menu with volume controls
- Add terrain assets and improve scene visuals
- Add custom slime sprites system

### Fixes
- Fix server ball physics to match client
- Harmonize server physics to Unity coordinates
- Fix online mode: ball bounce and character skins
- Sync server physics with Unity client
- Adjust ball bounce physics

---

## 27 Janvier 2026

### Features
- Add Teleport and Swap powers
- Add Giant power - player grows 1.8x for 4 seconds
- Add accessories for all characters with preview
- Improve slime sprite quality with anti-aliasing

### Fixes
- Fix Giant power: 70 mana, 3 sec duration

---

## 26 Janvier 2026

### Features
- Add WebSocket support for WebGL builds
- Add Revolutionnaire power: avocado shield
- Add Didier power: PDV projectile that stuns
- Add stun visual effect: rotating stars
- Add floating particles effect for menu background
- Add character-specific accessories
- Add complete crossbar collision physics

### Fixes
- Fix online goal detection and celebration delay
- Fix GOAL state freeze
- Fix crossbar collision blocking goal entry
- Use wss:// for WebSocket on HTTPS pages
- Hide mobile controls on desktop/web platforms

---

## 25 Janvier 2026

### Features
- Add Archer character with Arrow power
- Implement online powers system (server authoritative)
- Add character selection before online play
- Implement realistic goal visuals and physics
- Add procedural net texture for realistic goal
- Implement goal celebration delay (1.5s)
- Add keep-alive ping and opponent disconnect handling
- Add quit button and center score display

### Fixes
- Fix goal entrance collision and slow motion
- Fix blue gap at goal post corner
- Improve Sprint power and reduce mana drain
- Add Magnet visual effect
- Change power key from Shift to Space
- Fix online score display and countdown flicker
- Fix online gameplay freeze and opponent left popup
- Optimize server memory: zero-alloc loop

---

## 24 Janvier 2026

### Features
- Finalize Mobile Controls (Joystick)
- Add Font Styles (Bangers/LuckiestGuy)

### Fixes
- Correct offline and online score attribution

---

## 23 Janvier 2026

### Features
- Scene Setup automation and Fonts integration
- 9-Slice UI integration
- Online UX improvements - ceiling collision, connection popup
- Add Railway deployment configuration

### Fixes
- Update client port to Railway's TCP port
- Fix maven-shade-plugin for fat JAR
- Improve online physics - ball Y offset
- Disable local physics when network-controlled
- Sync physics between client and server
- Set Fixed Timestep to 60Hz

---

## 22 Janvier 2026

### Features
- Add OnlineGameController for server sync
- Add online matchmaking button and NetworkManager
- Implement complete Game Server with Netty
- Add generated sprites (slime, ball)
- Add Audio System and Gameplay Refinements
- Implement Single Player Mode with AI opponent
- Add Magnet power and dynamic character grid
- Add procedural visual effects for Sprint and Magnet

### Fixes
- Fix game reset issues: reset mana/powers

---

## 20 Janvier 2026

### Features
- Initialize GoalClash project structure
- Add core gameplay scripts - PhysicsConstants, SlimeController, BallController, GameManager
- Add SceneSetup editor script for auto scene configuration
- Add power system with Runner character (Sprint power)
- Add mana bar system with UI display and regeneration
- Add character selection system with Classic character
- Add main menu with JOUER, VESTIAIRE, OPTIONS, QUITTER buttons
- Add victory screen with winner display and restart button
- Add score UI display in top corners

### Fixes
- Fix slime ground position - remove offset for semicircle pivot
- Change slime sprites to semicircles like original game
- Fix playerNumber assignment and ball collision references
- Correct physics coordinate system for Unity (Y+ = up)
- Use new Input System instead of legacy Input class
