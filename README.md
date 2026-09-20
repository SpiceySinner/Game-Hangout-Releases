# Game-Hangout

Play together as if you were on one network. Game-Hangout puts you and your
friends on a small private network of your own, so games that only ever expected
a LAN can find each other again — and nobody has to open a port, forward
anything, or touch a router.

**[Download the latest version](https://github.com/SpiceySinner/Game-Hangout-Releases/releases/latest)**
— the file called `Game-Hangout_<version>_x64-setup.exe`. Windows 10 or 11.

This repository holds installers and nothing else. The source lives elsewhere
and is private; releases are here so that downloading needs no account, no
token, and no permission.

---

## Windows will warn you the first time

You will see a blue box saying **"Windows protected your PC"**. Click **More
info**, then **Run anyway**.

That box is not about a virus having been found. Windows shows it for any
program it has not seen often enough to have formed an opinion about, and a
program written by one person for their friends never reaches that number.
Buying the certificate that removes the warning costs a few hundred euros a
year, which is not where this project's money goes.

If that is not good enough for you, that is a reasonable position to hold — and
the honest answer is that you should not run software from strangers on the
internet. Ask whoever sent you this link whether they trust it.

## What it installs

Two programs, into `C:\Program Files\Game-Hangout`:

- **Game-Hangout** — the window. Runs as you, with your ordinary rights.
- **hangout-helper** — the part that creates the network adapter. Windows does
  not let ordinary programs do that, so this one asks for administrator rights
  the moment you start or join a hangout, and only then.

Listing your friends, downloading a game server and looking at your own id
raise no prompt at all, because none of them need any rights.

**A second window may open when you run a game server.** That black terminal
window belongs to the game's own server software, not to Game-Hangout. It is
supposed to be there, and closing it stops the server.

**Windows will ask about the firewall, once per game.** The first time you run a
game server, a blue box appears saying Windows Defender Firewall has blocked
some features, with a shield on the button. That is Windows noticing the game's
server waiting for players to connect, and it needs administrator rights because
answering it writes a firewall rule.

Say **Allow access**, with **Private networks** ticked. Windows remembers the
answer, so it happens once per game and never again — and it is about the game's
server, not about Game-Hangout, which is why it can only be asked at that moment
and not during installation.

## Updates

Game-Hangout checks for a new version a few seconds after it starts and tells
you if there is one. It never installs anything on its own, and it will refuse
to install while you are in a hangout, while a download is running, or while a
game server is up — those are all things an installer would interrupt.

Staying current matters more here than in most programs: two copies on
different versions do not tell each other so, they just quietly disagree about
what they are showing you.

## Removing it

Settings → Apps → Game-Hangout → Uninstall, the same as anything else.

Your identity and your friends list are deliberately left behind, so that
reinstalling does not make you a stranger to everybody who saved you. To remove
those as well, delete `C:\ProgramData\GameHangout` afterwards.

---

## How it works

Everyone runs the app. When one of you starts a hangout and the others join,
the app builds a small private network between your machines: a real network
adapter on each PC, linked directly to the others over encrypted connections.
Nothing is forwarded, and no server in the middle carries your traffic. To a
game, the others look like they are sitting on the same LAN.

Games that need a dedicated server (Minecraft, Project Zomboid, SCUM) get it
from the app. It downloads the server files from Steam — no account needed —
and starts the server on one member's PC. The save, the world, lives with that
PC. When that person leaves, the hangout hands itself and the world to the next
member, so the evening does not end with whoever started it. If you own a
machine that is always on (an old laptop, a Pi), it can hold the world while
everyone is asleep. That part is optional.

Mods travel as a list, not as files. Everyone gets the same list, every copy
fetches the mods from where they come from, and the app tests the combination
before anyone joins — missing dependencies are spotted up front, and when one
mod still breaks the server, the app finds which one.

Your identity is a key on your machine; friends are people who saved each
other. There is no account and no password, because there is nothing to log
in to.

### What we are working on right now (September 2026)

- **Letting strangers in.** The website lives at
  [game-hangout.com](https://game-hangout.com) now, and every link the app
  hands out — to a group, to a running hangout, to a modpack — lands on a
  page there that says what you are looking at and offers the download. Next
  is walking that road end to end with people who are not our friends yet,
  and listening to what they say.
- **A signed installer**, so the blue box on first start goes away. The road
  is decided; the section above about the warning gets rewritten the day it
  lands.

### The next big milestones

1. **More games.** Three work end to end today; the server files of 57 are
   measured and sit in the app's list. BeamNG (via BeamMP) is next in line.
2. **Adding a game yourself.** Every supported game is a small text file that
   says where its server comes from, how it starts and what it needs. The
   plan is a developer mode where you write that file for a game we have not
   touched, try it locally, and play on it — and, once that works without
   guesswork, hand it in so everyone gets the game.
3. **Opening the door.** Today you need a friend on the inside, or a link
   from one. The pieces for groups that start from the website are built; the
   walk with strangers is the first item above.
4. Further out, building mods together — but that is a conversation so far,
   not a plan.
