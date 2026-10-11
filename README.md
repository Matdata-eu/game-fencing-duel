# Piste Duel

One-on-one fencing as an installable web app (PWA). Pick foil, épée or sabre; the rules, the scoring box, the weapon and the fencers' kit change with it. A referee calls each action with the standard hand signals.

**Play:** https://matdata-eu.github.io/game-fencing-duel/

## Modes
- **Bot**: you (red, left) against a bot (green, right) on Easy, Medium or Hard. Harder bots react faster, parry more often, riposte sooner and judge distance better.
- **2 Players**: two people on one device. Keyboard: Red `A D` step, `S` lunge, `W` parry, `E` flèche. Green `← →` step, `↓` lunge, `↑` parry, `/` or right `Shift` flèche. Against the bot, `Space` also does a flèche. On a touchscreen each player gets buttons on their side.
- **Clubs**: fence for [Schermclub Parcival](https://www.schermclubparcival.be/) (Leuven), for Schekul (the KU Leuven student fencing club Parcival grew out of), or for no club. The club shows on the socks, the crest on the jacket and under the fencer's name; red and green stay with the side, like the lights on the scoring box. Defaults: you fence for Parcival, the bot for Schekul.
- **Bout**: 5 touches (3 min), 10 touches (6 min) or 15 touches (9 min). If the score is tied at time, the referee draws priority for one extra minute: first touch wins, and if nobody scores the fencer with priority wins.

## Weapons
| | Foil | Épée | Sabre |
|---|---|---|---|
| Hits with | point | point | edge and point |
| Valid target | torso (silver lamé vest) | whole body, including the hand and arm | above the waist, arms and mask (lamé jacket and mask) |
| Off-target hit | white light, action stops, no point | – | – |
| Double hits | right of way | a point each (within 1/25 s) | right of way |
| Lockout | 300 ms | 45 ms | 170 ms |
| Forward rush | flèche | flèche | flunge (flèche is not allowed) |

## Superpowers
Each fencer can pick a tongue-in-cheek national superpower (or none). You get one use per 5 touches of bout length. Press `Q` (Red) or `.` (Green), or the ★ button.

| Nation | Superpower | When | What happens |
|---|---|---|---|
| Belgium | Belgian compromise | the referee gives a touch against you | After long negotiations, everybody gets a point. |
| Italy | Protesta! | the referee gives a touch against you | You protest at length. Half the time the referee gives in and annuls the touch; otherwise it's a yellow card. |
| France | Home referee | during the bout | The referee speaks French anyway: until the next touch, every close double goes your way. |
| Hungary | Hussar charge | during the bout | Your next attack gallops in, longer and faster. |
| Germany | Precision | during the bout | For 8 seconds every incoming attack is parried automatically, exactly on time. |
| Great Britain | Tea time | during the bout | Your opponent politely accepts a cup of tea and stops fencing for a moment. |

The bot uses its superpower too.

## Moves
- **Step forward / back** (pas en avant / pas en arrière): tap or hold a direction.
- **Balestra** (jump forward): double-tap forward. Lunge right after it for a balestra lunge. Double-tap back to jump back.
- **Lunge** (fente): attack. Attack while stepping forward for an advance-lunge (marche-fente).
- **Flèche**: its own key or button, or press attack twice quickly (foil and épée). At sabre the same control does a flunge.
- **Stop-hit** (contre-attaque): hold back and press attack. At épée it goes for the hand or arm, and some attacks aim there too.
- **Parry and riposte** (parade, riposte): parry as the attack arrives, then attack straight away. A parried attacker can parry the riposte back if it comes late.

## Right of way and the referee
At foil and sabre the referee decides who scores when both lights go on. The fencer who starts the attack first has right of way; a successful parry takes it over for the riposte; an attack that falls short loses it. Two attacks starting together are simultaneous and nobody scores. The referee shows each decision with the usual signals: halt, attack, parry, riposte, counter-attack, point awarded, off target, no touch, and priority. Stepping off the end of the piste gives a point to the opponent; body contact (corps-à-corps) stops the action without a point.

## Install
Open the game in Chrome, Edge or Safari and choose "Install" or "Add to Home Screen". After the first load it works offline.

## Run locally
No build step. Serve the folder over `localhost` or HTTPS, for example:

```sh
python3 -m http.server 8000
```

Files: `index.html` (the whole game), `manifest.webmanifest`, `sw.js` (offline cache), `icons/`. Pushes to `main` deploy to GitHub Pages through `.github/workflows/pages.yml`.

## Support
Found a bug or have an idea? [Open an issue](https://github.com/Matdata-eu/game-fencing-duel/issues).

## Credits
- Game, graphics and sound effects: made from scratch in code (canvas drawing, Web Audio), no third-party assets. The referee's voice uses your browser's built-in French speech, when available.
- Fonts: [Bungee](https://fonts.google.com/specimen/Bungee) by David Jonathan Ross and [Barlow Condensed](https://fonts.google.com/specimen/Barlow+Condensed) by Jeremy Tribby, both under the SIL Open Font License, loaded from Google Fonts.
- Club names belong to Schermclub Parcival and Schekul. The club colours and lettered crests in the game are simple stand-ins, not their official logos, and are not covered by the MIT license.
- Built by [Matdata](https://matdata.eu) with [Claude Code](https://claude.com/claude-code).

## License
[MIT](LICENSE)
