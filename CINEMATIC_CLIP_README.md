# Cinematic clip event — Murugesan failure prototype

Open `cinematic-clip-demo.html` from an HTTP-served copy of this branch (or download it and open it in a browser) to try the standalone prototype.

## Demonstration
1. Click **Preview failure** to force a low courage roll.
2. The D20 animates; failure triggers an automatic video reaction.
3. If no video has been selected, the prototype plays an animated comedic reaction.
4. The Dungeon Master delivers a Tamil punchline and shows an English translation.
5. The scene transitions to the continuation state.

**Roll Courage D20** instead gives a random outcome, with DC selectable in the editor. Choose an authorized MP4 or WebM from your device to substitute for the fallback. Uploaded media is kept in memory as a local browser object URL and is not sent to the repository or Firebase.

## Limitations / next steps
- This is a **standalone host-side proof of concept**, not an integrated scene in the existing 12-round multiplayer game.
- Browser Tamil speech synthesis requires a suitable installed Tamil voice for good pronunciation; initiating playback requires a user gesture.
- Browser audio/video autoplay restrictions may prevent clip playback; the fallback remains available.
- No film clips or copyrighted audio are bundled.
- Media uploads are not persisted.
- This has not yet been verified in an end-to-end multi-device playtest.
- Next: centralize scene events, integrate Firebase TV/phone synchronization, and add secure asset storage and a reliable event queue. A client-side roll should not be authoritative in multiplayer.
- The prototype deliberately remains on a review branch; main is unchanged.
