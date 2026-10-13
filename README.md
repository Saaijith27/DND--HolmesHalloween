# DND — Holmes Halloween 🎭
## Chandramukhi Mansion — Automatic Digital Dungeon Master

A 12-chapter haunted mansion browser adventure with Tanglish dialogue, English player instructions, phone voting, and a TV Dungeon Master.

### What works now
- TV host screen and five-player phone controller UI
- Unique six-character room code
- Live Firebase Realtime Database synchronization once configured
- Automatic timers: 5 minutes × 12 chapters (about 60 minutes), or 3- and 1-minute test modes
- Vote totals displayed on TV; majority choice revealed automatically at end of each round (ties favor the first option)
- Five Chandramukhi-inspired character roles
- Host can skip rounds and restart

**Important:** Movie clips and spoken text-to-speech narration are NOT implemented yet. The game currently renders narration as on-screen text. Character roles are cosmetic in this version.

## Try it right away
After GitHub Pages deploys, open https://saaijith27.github.io/DND--HolmesHalloween/ and select **Create TV Room** to see the local TV preview. Without Firebase configured, phones cannot join.

## Enable cross-device multiplayer with Firebase
1. Create a free-tier Firebase project at https://console.firebase.google.com/ (pricing and quotas are subject to Firebase's current terms).
2. Add a **Web app** under Project settings, copy the Firebase configuration fields into `firebase-config.js`. Add `databaseURL` from Realtime Database.
3. In **Authentication → Sign-in method**, enable **Anonymous** sign-in.
4. Create a **Realtime Database** and choose a region. In **Rules**, paste `database.rules.json` and publish the rules.
5. Commit your updated `firebase-config.js` to GitHub; wait for GitHub Pages to redeploy.
6. On the TV choose **Create TV Room**; players scan/type the displayed link or enter the room code on their phones and select roles.
7. The TV host starts the game. Rounds advance on their timers, and voting results synchronize across devices.

The Firebase web config is *not* a password; database security comes from its rules. **These prototype rules allow any anonymous signed-in visitor who knows a room code to read the room and submit one vote per UID, and do not comprehensively prevent abuse.** Do not store private data. Before publishing widely, implement stronger access control, room expiry, validation and anti-abuse limits.

### Known limitations
- The TV/browser must remain open during play because its timer drives round advancement.
- If the TV loses connectivity or sleeps, chapter changes will pause until the host returns.
- In the non-Firebase preview, votes are not synchronized and the TV advances automatically using the first option.
- The Firebase setup is required for different devices to share one room.
- The basic majority-vote result only affects the text reveal; the 12 chapters follow a fixed sequence rather than true branching paths.
- A player can manually choose from any of the five roles (uniqueness is not enforced).
- No hosted video library or synthesized audio narration is present yet.

### Game files
- `index.html` — game UI, story, countdowns, host/phone synchronization
- `firebase-config.js` — template Firebase config for your project
- `database.rules.json` — prototype Firebase Realtime Database rules

Made for a fun Halloween game night. Use audio/video clips you have the rights to play.
