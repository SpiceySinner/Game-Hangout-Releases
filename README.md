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
