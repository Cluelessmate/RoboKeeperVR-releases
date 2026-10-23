# Changelog

Every change gets a new build number. Not every build is published: a GitHub release lists everything since the last one, so read down to the previous published version.

## v1.18.0

### Modes, simplified
- **Five modes instead of ten.** The main menu is now **CAREER · ARCADE · PLAY / MY CLUB · TROPHIES · OPTIONS**, and **PLAY** holds the **Penalty Cup**, **Training** and **2 Player** (plus **Stats & scores**).
- **The daily challenge is gone**, and so are its online board and its "Daily hero" trophy (that cabinet slot is now the Penalty Cup).
- **Shootout and Rival Duels** are replaced by the Penalty Cup. **Practice, the reflex test and the tutorial** now live under Training. **Online scores** sit on the Stats page, and the **button guide** is in Options > Controls.

### New
- **Career.** Season mode grows into a career. You stay with your own club and kit, and climb four divisions: **County League**, **Robo League**, **Robo Premier**, **World Elite**. Each one is a step harder and has a bigger home ground. Finish in the top two to go up, bottom and you go down. Scouts give you a **keeper rating** every season, and the career hub keeps your history (Career > FIXTURES > MY CAREER). Existing seasons carry on in the Robo League.
- **Penalty Cup.** A three-round knockout (quarter-final, semi-final, final) against the rival robots. Each tie is five penalties, and one of them is the rival's signature shot. Your team's five kicks are rolled at the start, so you know how many you must keep out. Win the final for the **Penalty Cup** trophy and a trophy lift.
- **Training drills**, run by the coach drone:
  - **Reaction Lights**: 20 pads light up around you, always inside your calibrated reach. Punch each one before it goes out; quicker hits score more.
  - **Low Dives**: 15 skimmers from the ball machine into the bottom corners.
  - **Crosses**: 12 corners and crosses (below).
- **Corners and crosses.** In Arcade (from wave 2), mixed practice and the Crosses drill, the striker whips the ball in from wide while two robot attackers charge in to head it. The cross is always aimed inside your reach from your line, so you never need to move. Claim it, punch it, or let a robot nod it at the far corner. Step forward if you want to: you meet it, and them, sooner.
- **Punch the robots.** Any robot that gets too close (corner attackers, the rebounder, match robots charging in) can be punched. A jab gets "BOXED OUT! +50"; a big swing knocks it flat, "FLATTENED! +100".
- **Glove perks**, earned with saves in any mode: **GRIP+** at 50 (catches stick more easily), **PUNCH+** at 150 (punches go further), **REACH+** at 300 (a slightly bigger glove), **TURBO** at 500 (gold booster flames). Options > Gameplay > PERKS turns them off.
- **Best saves.** Your six best saves ever, with their replays, are kept in a **Save of the Season** reel. Trophies > BEST SAVES plays them on the big screen.
- **The crowd is on your side.** Four saves in a row and the crowd sings your name. On match days (career and Penalty Cup), home fans in the side stands hold up banners such as "#01 LOGAN" and "SAFE HANDS" in your colours.
- **2 Player: pass the headset.** Player 1 keeps for ten shots while player 2 shoots on the PC, then "SWAP!", and player 2 goes in goal. Most saves wins, with both scores side by side, and the PC screen tells you whose go it is.
- **Crash log and Report a Bug.** If the game closed without quitting properly, the next start saves a crash report from the last session's log. Options > REPORT A BUG saves a report now (version, PC, settings and the log) and opens its folder.
- **Update notice.** If a newer build is on GitHub, the main menu says so.

### Behind the scenes
- **Tests on GitHub.** Every push runs the headless tests and autotests (`.github/workflows/tests.yml` and `tools/ci_tests.sh`), so a broken build shows up as a red cross.
- **Online leaderboard, ready to switch on.** `server\deploy.ps1` puts the score server on your free Cloudflare account and fills in `config/online.cfg` (steps in `server/DEPLOY.md`). It is Arcade-only now.
- **Website assets.** Transparent logos (`docs/website/logo_*.png`) and 1920x1080 screenshots (`docs/website/screenshots/`), made by `tools/make_web_assets.py` and `tests/v14_shots.gd --only=web`.
- **New autotests:** `--cup` and `--drill --kind=lights|lowdives|crosses`. The `--shootout`, `--rival` and `--daily` flags are gone.

### Fixed
- A rebound robot that got knocked over mid-chase could leave the game waiting for a shot that never came.

## v1.17.0

### New
- **Read the kick from the run-up.** Each kick style now shows itself over the second half of the run-up: the robot leans back for a chip or a dink, leans in and pumps its arms for a laces drive, comes in on a curved approach with its shoulders open for a curler, runs low for a driven shot and goes stiff-legged for a toe-poke. The timing of every shot is unchanged.
- **Celebrations fit the moment.** An ordinary goal gets a small celebration (spin, ear cup, shush, the robot). A big moment gets a showpiece (backflip, floss, knee slide, aeroplane): a goal late in a match, every third goal you let in, the goal that costs your last life, a golden ball or a rival's signature shot.
- **The coach drone joins in.** If the robot dances (the robot or the floss) the drone can't help bopping along for a moment, then catches itself and sulks. It does a spin for a worldie.
- **A different feel for each save.** A fingertip save gives two light flicks, point blank one hard jolt, a worldie three rising pulses, a punch a thud and a knock back up the arm, a catch a tap then a squeeze in both hands, and the woodwork rattles.
- **Your goalmouth wears in.** The grass in front of your goal gets scuffed and bare as a match or run goes on (and muddy in the rain). Fresh again for the next one.
- **Visor logo glint.** The headset now opens on the Visor logo with a glint sweeping across it, carrying on from the desktop splash, before "LOGAN PRESENTS".
- **Subtitles** (Options > Sound & Vibration). What the announcer and coach drone say, in small text low down in your view, well under where the ball comes. Off by default.
- **RESTART NOW** on the Graphics page. It appears when you change graphics or foveated rendering, which only take effect on a restart, and restarts the game straight away.

### Changed
- **Voices come through clearly.** While the announcer or coach drone speaks, the crowd and weather dip by 7 dB, then come back up gently.
- **No more loud spikes.** A limiter on the sound effects stops pile-ups (punch, post, cheer and horn at once) from getting too loud.
- **Coach drone never blocks your view.** If it is between you and the robot or a ball in play, for example when a shot starts while it is still in front of you, it turns see-through until it is out of the way.
- **Frame-time readout** now shows the graphics and foveated rendering settings actually running (and "restart to apply" when they differ from the menu), plus the frame-time target in ms.

### Tests
- **New menu test** (`tests/test_menus.tscn`): presses every pad on every page in every UI style, cycles every option through all its values and checks every label still fits its pad. It also checks that every page link leads somewhere and that the game handles every action the menu sends.

## v1.16.2

### New
- **More goal celebrations.** When a robot scores it now picks one of eight (never the same twice running): the jumping spin, doing **the robot**, a **knee slide** towards you, the **aeroplane** (arms out, banking round in a circle), a **backflip**, cupping an ear to the crowd ("can't hear you!"), walking up to **shush** you, and **the floss**.
- **Painted turf.** The grass has a hand-painted look that fits the rest of the game: soft brush-stroke clumps in three tones of green, slightly bolder mowing stripes with brushy edges, and painted blade strokes close to your feet that fade out with distance (no shimmer). Same colours as before, nothing oversaturated, and no toon shading.
- **Kick variety.** Robots strike the ball differently for each kind of shot: a big laces drive with a hop off the ground for power shots, an inside-foot curl with the body swinging round for curlers and free kicks, a short stab leaning back for chips, a tiny dink for the Panenka, a low driven strike over the ball, and a stiff toe-poke for knuckleballs. The timing of every shot is unchanged, so they're no harder to read.

- **Push the coach drone about.** Nudge it with your glove and it slides out of the way; park it somewhere else at the side and it stays there for the rest of the session. A hard push or a punch anywhere on it (not just the head) knocks it over.
- **The drone comes to you between shots.** While a shot is on its way it waits out to the side as before, but in the lull between shots it flies round to hover in front of you, then darts back out of the way as soon as the next run-up starts.

### Changed
- **Sound effects balanced.** Every sound was measured and the ones that stood out were turned down: the referee's whistles (7 dB), the punch (6 dB, it plays right next to your head), the wave-clear, game-over and star jingles, the robots' happy chirps, the glove catch, cheers and "ooh"s, and a few others (2-5 dB).
- **No big pop-ups in your way mid-match.** Call-out banners during play are half the size and sit high above the action, out of the line of any shot, and they duck away completely whenever a ball is in the air. Score pop-ups near your face are drawn smaller, and "+1 LIFE", "UNLOCKED" and tips now appear low, below your eye line.
- **Distant ball looks better.** Instead of turning into a bright white glow far away, the ball keeps its panels and gets a crisp lit rim and a thin gold tracking ring round it (like a TV ball tracker). It still grows a little with distance so you can pick it up early.
- **Softer, quieter rain.** The rain no longer hisses: it's a soft, lower patter on the grass and about 9 dB quieter.
- **Puddles look natural.** Puddles were blocky shapes with sharp, straight edges; now they're rounded with a soft damp shoreline. Muddy patches on park pitches lost their blocky edges too.
- **Warmer announcer.** The stadium announcer is less harsh: a wider, smoother PA sound with much less distortion and a darker echo. Every announcer clip was remade.
- **Credits** now say "Made by Kieran and Logan."

### Fixed
- **White specks on dry grass.** Little white patches were dotted over every pitch even on clear days: a bit of the snow cover was leaking through when it wasn't snowing. Gone, along with the square glints the old bumpy grass texture made in the sun.
- **Grey screen when changing graphics settings.** Changing GRAPHICS or FOVEATED mid-game rebuilt the headset's picture (its resolution, anti-aliasing and shading rate) while it was rendering, which could freeze it (SteamVR's grey screen). Those parts are now set once when the game starts, and a change applies the next time you start; shadows still change straight away. Changing any other option no longer touches the headset's picture at all.

## v1.16.1

### New
- **New logo and icon: "Visor".** A VR headset whose lens shows your view of a shot coming in: the ball flying at you in a yellow burst and your orange gloves reaching for it, with the six pad colours underneath. It's the game's icon, the Windows .exe icon and the loading screen, now with a white ROBOKEEPER title and the cyan VR pad.
- **The coach drone has a face.** Its head is now a little TV with a glowing screen, and the screen shows how it feels:
  - **Starry eyes** and a big grin for a worldie or a fingertip save, a **happy ^ ^ smile** for a save, a **proud** little smile for a catch, a gasp then a grin for a point-blank stop.
  - **Sad** (droopy eyes, a frown and a tear) when you concede, **disappointed** if you leave it hanging on the high five, **excited** while it waits for one, and over the moon when you give it.
  - **> <** when you punch it, **spiral eyes** while it lies on the grass, then **woozy** as it gets back up. The screen glitches when it takes a knock.
  - Its eyes **follow the ball** in flight and blink and glance around the rest of the time. The ear rings, antenna tip and the band round its rocket glow in the same colour as its mood.
  - A ball you've already touched (a parry or a throw) now **bounces off** it ("OW!"); a live shot it ducks out of the way of, so it never changes whether a shot goes in.
- **Smarter-looking drone:** a fin across the top, bigger ear pods, a springy antenna that wobbles as it flies, and three tail fins on the rocket.
- **Cute new drone voice.** A higher, softer robot voice that finishes each line with a little chirp (a happy trill, a sad slide down, a squeak when it's hurt, a warble when it's dizzy). 33 new lines on top of the old ones, never the same one twice in a row:
  - hello and goodbye ("Hello, keeper! Beep beep!", "Bye bye! Beep!");
  - saves ("Beep boop! Nice save!", "Boop! Blocked!", "Superstar!", "Does not compute! Amazing!", "My circuits are tingling!", "Sticky gloves!", "Got it! Hee hee!");
  - goals ("Aww... beep.", "Oopsie!", "I believe in you!");
  - the high five ("Up top!", "Woo hoo!", "Aww, left hanging...");
  - knocks ("Ouchie!", "Hey! Rude!", "My antenna!", "Bonk!", "Eek!", "Bzzt... seeing stars...", "Rebooting... I'm okay!");
  - and in a quiet moment it hums or chats to itself ("La la la...", "Ready when you are!", "I'm watching the ball!").
- When you concede, the drone always looks sad now (it still only speaks half the time).

### Changed
- **Better grass in every weather.** Same hand-painted look, but it now reacts properly to the conditions:
  - **Rain:** the turf goes darker and glossy instead of shiny foil blotches. A few puddles collect in the low spots (only the odd one on stadium pitches, more at the park and the rec), with rain rings rippling in them. The muddy goalmouths go slick.
  - **Snow:** a proper soft white cover that lies thinner in places so grass peeps through, trampled to grey slush in the goalmouths. The pitch lines are painted **blue** in snow so you can still see them.
  - **Clear days:** slightly bolder mowing stripes, and fine blade streaks along the cut when you look down (they fade out with distance, so no shimmer).
  - **Grass tufts** round the goal now sway in the breeze and bend and gust with the wind. They go dark in the rain and stick up out of the snow.

## v1.16.0: "Coach"

### New
- **Coach drone.** In practice, the reflex test, the tutorial and the daily challenge, the stadium announcer is replaced by a little flying robot with arms and a rocket base (like your gloves' boosters). It hovers beside you and shouts "Nice save!", "Fingertip!", "World class!", "Safe hands!" and more in its own chirpy robot voice. At the end it flies in for a **double high five**: slap both its hands. Or punch it in the head and it loses its balance, crashes to the grass, lies there sparking, then gets back up a bit wobbly.
- **Customisable boots** (MY CLUB → BOOTS): the same designs, patterns and colours as the gloves (sole and laces instead of palm and strap), plus MATCH MY GLOVES. You'll see them on your keeper's feet.
- **"Beast" gloves**: a dark teal design with black raised ribs across the fingers and a grey palm, using a new **Ribs** pattern you can also pick for your own gloves and boots.
- **Robot scorers are named.** When a robot scores, the announcer calls out who it was: the rival, or a punny robot footballer (Wayne Rooney-tron, Gary Line-coder, Jack Grease-lish, Peter Crouch-droid, Cole Palm-pilot and more), with the name over his head and on the scoreboard.
- **Title screen**: punch the ball at the warming-up robot and he explodes into pieces, which bounce around the pitch and then whizz back together.

### Changed
- **Real football, properly kicked.** Every pass, cross, shot and dribble touch now has a visible kick: the robot winds up and his foot meets the ball, and a pass is controlled with a first touch. The robot on the ball lines his kicking foot up with it. The ball never moves unless someone kicks it (or you throw it), it bounces off any robot in its way instead of passing through, and if it ever sits still in open play the nearest robot is sent for it.
- **Running looks right.** Robots' strides now match their speed (no more skittering legs when they sprint), still with the stiff, robotic servo steps.
- **Better slide tackles.** Three tackles (a studs-first slide, a two-footed flying scissor lunge and a spinning low sweep), and the robot who's hit goes tumbling: rolled over his shoulder, spun round and down, or upended onto his front, before getting back up.
- **Drop kick**: you toss the ball up a little, it drops to your boot at knee height out in front, and your leg follows through high into view with a streak behind the boot. Big ones get a moment of slow motion and a trail on the ball. It still flies where you're looking.
- **Options are organised by category**: GAMEPLAY, CONTROLS, GRAPHICS, SOUND & VIBRATION, COMFORT and ABOUT. The pause menu's OPTIONS opens the same pages (gameplay settings and calibration wait until you're out of the match).
- **Gloves page**: the preview has its own panel beside the pads, so the gloves no longer poke through the buttons. "READY-MADE DESIGNS" and "MAKE YOUR OWN" are clearly separated: designs are pads in their own colours, the parts you change are the teal pads below.
- **Maresfield's keeper kit is purple** again (older saves had drifted).
- **Crowd**: each stand is now drawn separately (stands out of view are skipped) and heads are part of the same mesh as the bodies, which halves the crowd's draw work at the same look.

## v1.15.0: "Flowing Football"

### New
- **Acrobatic finishes.** The opposition now cross from the wings for their striker to meet in the air with a **volley**, a **header**, a **diving header** or a **bicycle kick**, each with its own animation (leaving the ground, the strike, the landing and getting back up), a banner and an announcer call. The warning still comes first: orange eyes, a beep and a "!" before every one. Sometimes one of your defenders gets there first and heads it clear.
- **Away kits.** The away team always changes into an away kit picked to stand out from the home shirts, so you never mix up the teams (no more orange against red).
- **Team-mate markers.** A small spinning mint-green marker floats over your team-mates' heads in matches.
- **Options on the pause menu.** Pause now has RESUME, OPTIONS and QUIT, with RECENTER VIEW and RESET HEIGHT below. OPTIONS covers sound & vibration, comfort, graphics, foveated rendering, frame time, replays, seated/standing, which wrist the HUD is on, and reduced flashing. BACK takes you back to the pause menu.

### Changed
- **The ball only moves when someone kicks it.** Every pass, shot, cross and back-pass is struck by a robot actually on the ball. Possession never just swaps: losing the ball is now a pass that gets read and cut out, or a tackle. A loose ball goes to whoever reaches it first.
- **Smoother dribbling.** The robot on the ball runs flat out onto it and keeps it close instead of trailing behind.
- **Smarter AI.**
  - Passes go to team-mates in space with a clear lane; marked players get ignored.
  - Under pressure a robot moves the ball on quickly; in space he runs with it.
  - Off the ball, one team-mate always shows for a short pass and the most advanced player makes a run in behind.
  - Defenders split into one closing the ball down (staying goal-side), one covering, and the rest marking a man. Robots far from play jog instead of sprinting.

## v1.14.0: "Rivals"

### New
- **Rival robots.** Seven star strikers with names that send up real footballers, each with their own look (hair, beards, a crown, a captain's armband, speed fins), a name tag over their head, a favourite mix of shots and a **signature shot**:
  - **KANE-O-MATIC 9** (Cogsworth Rovers): low, hard and right in the corner (SPOT-ON).
  - **MBAP-E 7** (Voltchester City): rapid drives that skim the turf (TURBO DRIVE).
  - **HAAL-UNIT 99** (Boltham Athletic): hits everything as hard as he can (THE HAMMER).
  - **RON-DROID 77** (Circuit Wanderers): knuckleballs that dance in the air (KNUCKLE-BOT).
  - **MESS-E 10** (Steelport United): dummies, curlers and the MAGIC CHIP.
  - **SALAH-MATIC 11** (free agent, beat 3 rivals): bends it into the far corner (THE CURL).
  - **BOT-ALDINHO 80** (free agent, beat 5 rivals): tricks and the NO-LOOK finish.
- **In the season** each club's rival leads the line. The announcer warns you about him at kick-off ("Watch out for... Haal-Unit!"), and up to twice a match he tries his signature shot, with a banner, his colour on the ball and his own call. Win the match to beat him.
- **RIVAL DUEL** (MORE MODES → RIVALS): 10 shots from the rival you pick, three of them his signature. Save 6 to beat him. Stopping a signature shot is worth +200.
- **More unlockables:**
  - **Match balls** (MY CLUB → BALL & NET), one for beating each rival: Retro leather, Neon, Steel, Pinwheel, Galaxy, Pharaoh and Samba. The ball you pick is used in every mode.
  - **Goal nets:** Club colours (win 3 season matches), Red (keep 5 clean sheets), Midnight (beat 2 rivals) and Volt (beat all 7).
  - The two free-agent rivals unlock their own duels.
- The trophy cabinet shows how many unlocks you've earned and how many rivals you've beaten.

### Changed
- Locked pads show what you need to do in bigger, two-line text (for example "BEAT / MBAP-E").
- MY CLUB has four pads along the bottom: KIT & CREST, GLOVES, BALL & NET and BACK.

## v1.13.0: "Champions"

### New
- **Lift the trophy.** Win the league or the cup and a plinth rises out of the turf in front of you with the trophy on it. Grab it with either glove and lift it over your head: fireworks go up over the stands, confetti rains down, the crowd sings your name and the announcer calls it. Then the results come up, and the trophy is in your cabinet. On a PC (or if you don't lift it within 20 seconds) it lifts itself.
- **Things to earn:**
  - Three new glove designs: **Champion** (win the league), **Cup Hero** (win the cup) and **Worldie** (make 3 Worldie saves), with three new glove colours (Champion Gold, Chrome, Cosmic).
  - Two new kit colours: **Champion Gold** (win 5 season matches) and **Teal** (keep 3 clean sheets).
  - **Stadium choice** for arcade, shootout and 2 player (MORE MODES → STADIUM): National Arena, Town Stadium, **Sunday League Park** (win a season match) and the **World Final** (win the cup).
  - Locked pads say how to earn them, and an "UNLOCKED!" chip and jingle pop up when you do. Things you'd already earned before this update are unlocked without a pile of pop-ups.
- **Match report on the full-time screen:** a goal map of where this match's shots went (saved / faced in each zone, green to red) and your three best saves with their speed and your reaction time.
- **The crowd reacts to you:** after a big save the fans sing your name ("LO-GAN!" clap clap clap) for every name the announcer knows ("KEE-PER!" otherwise), and they boo the referee when a foul goes against you.
- **Announcer variety:** 2–3 different lines for most calls (saves, goals, kick-off, full time, fouls, free kicks, penalties, corners, the woodwork, near misses, counters, replays and more), never the same one twice in a row.
- **Sound & vibration page** (OPTIONS → MATCH, SOUND & MORE): separate volumes for music, crowd, announcer and effects, plus controller vibration strength. Each pad steps down by 20% and plays a sample.
- **Comfort page:** snap turning (30° or 45°) or smooth turning on the right stick, a comfort vignette that darkens the edges of your view while the stick moves or turns you (off / light / strong), and **RESET HEIGHT**, which re-measures your eye height so you stand at keeper height. RESET HEIGHT is on the pause menu too.
- **Frame-time readout** (FRAME TIME): FPS, frame time, worst frame, CPU/GPU time and draw calls in the corner of your view, green when on target and red when dropping frames.
- **Foveated rendering** (FOVEATED: off / light / strong) draws the edges of your view in less detail to keep the frame rate up, where the headset and GPU support it.

### Changed
- **Tutorial:** catching now tells you to keep the ball, and there are new steps for the overarm throw, rolling it out and the drop kick (with your controller's button names).
- **No more hitch when the venue changes:** every stadium is built while the game loads, so going from the menu to a match (and back) is instant.

## v1.12.1: "Distribution"

### New
- **Four ways to get the ball back into play** when you have it:
  - **Throw it overarm:** swing from up high and let go of the grip for a long throw, nudged a little towards where you're looking.
  - **Roll it out:** sweep your hand low and let go, and it's rolled along the ground.
  - **Pass:** press cross / square (A / X) to pass to the teammate you're looking at.
  - **Drop kick:** hold circle (B) and let go. The ball drops from your hands, your robot leg winds back, swings through and volleys it, with a thump, a burst of sparks, a ring of light, a hard controller kick and a split-second freeze. It flies straight where you're looking. The longer you hold, the harder it goes (full power after a second), shown by a meter over the ball that turns from green to red. From your feet (a goal kick or a trapped back-pass) it's a big hoof with the same swing.

### Changed
- **Buttons:** the left triangle (Y) recentres the view, and the right circle (B) is the drop kick. Options, Create and Menu pause. The PS VR2 Options button now also works through the system-button route SteamVR uses for it.
- The Controls page and the in-game hints name your controller's buttons (for example "CROSS: pass · CIRCLE: drop kick · or throw it").

### Fixed
- A goal-kick ball at your feet could not be kicked (it was never put into play).

## v1.12.0: "Proper Football"

### Changed
- **Season matches play like real football.** The ball has real physics: passes are kicked along the ground or lofted, slow down as they roll and bounce when they land. Passes go in front of the receiver, who runs onto them, and defenders near the ball's path can cut them out. A pass nobody reaches is chased down by whoever's nearest, and an overhit one runs out for a throw-in or corner. Nothing is scripted any more, so moves break down and turn over naturally.
- **Tackles only go in on the robot with the ball.** If he's already moved it on, the tackle hits nobody.
- **Their striker shoots on the run** from all sorts of distances, from close in to 30-odd metres, with a short warning first: his lights flash orange, he beeps and a "!" pops up over his head.
- **Free kicks and penalties now come from fouls.** The whistle goes, the announcer calls it ("That's a foul! Free kick!" or "Penalty! The referee points to the spot!"), a banner pops up, and the big screen replays the foul while the ball is placed.
- **No more vanishing ball after a save.** A ball you catch or trap stays yours until you throw it, roll it, drop-kick it (A/X pass, B/Y kick) or drop it, and play carries on from wherever it goes. If you hang on to it for a very long time it gets thrown out to a defender for you. Shots that go wide are your goal kick: a new ball appears at your feet. The ball only goes back to the centre spot after a goal.
- **Start screen:** the "BOOM!" text no longer sits in front of your eyes, the logo gets out of the way straight away, and the ball flies a little slower, so you can watch it all the way into the far net.
- **Menu pads need a pull-back:** after pressing a pad you have to pull your hand back in front of the next pad before it will press, so a punch that follows through can't hit the pad that appears behind it.
- **Quit game:** a QUIT GAME pad in Options, with a check before it closes.
- **Big screen:** everything now fits inside it. The team name, score, combo, match score or wave, lives, best score, focus meter and venue line each have their own space and shrink to fit, and big messages wrap onto at most two lines.
- **Keeper's boots** are now built like the other robots' boots: chunky boots on kit-coloured soles with studs, a lace plate and a metal ankle joint.
- **Reflex ball machine:** a proper tripod with splayed legs, rubber feet and braces, a yoke holding the launcher, a barrel with a steel muzzle, and a hopper of balls on top.
- **Stretching gloves** no longer leave an orange beam back to your hand. The rocket flame is the effect now.
- Four new announcer lines: "That's a foul!", "Free kick!", "Penalty! The referee points to the spot!" and "Goal kick."

## v1.11.1: "New Look"

### Changed
- **New game icon** in the Punch Pads style: a chunky orange robot keeper glove (rocket booster firing) punching a football, with a yellow impact burst on a gunmetal tile edged in the six pad colours. It's used for the exe, the window and the project.
- **New loading screen:** the same artwork over a big ROBOKEEPER title in Bungee with a cyan VR pad and a row of little punch pads, on the console's gunmetal colour.
- The "LOGAN PRESENTS" intro in the headset now has a strip in the six pad colours instead of the orange line.
- **Upload to GitHub now moves on to the next version by itself:** after a successful push it raises the version (for example 1.11.1 → 1.11.2) in the project and export settings, starts an "in progress" entry in the changelog and pushes that, so new work never lands on a version that's already been published. Run `publish.ps1` with `-NoBump` to skip it.

## v1.11.0: "Punch Pads"

### New
- **New menus: chunky 3D punch pads.** Every menu button is now a real arcade pad, with a housing, a light ring and a coloured cap that moves. Your glove pushes the cap in; a proper punch slams it to the bottom with a heavy clunk, a hard controller thump, sparks and a split-second freeze, and it springs back up past its rest. The ring glows and the pad rises a touch as your glove comes close (with a soft tick). Brushing past or resting a glove on a pad doesn't press it, but pushing it nearly all the way in does.
- **Arcade console:** the main menu's six pads and the full-time buttons sit on a console tilted towards you at chest height, under a screen showing your club and next fixture.
- **The menus are at the training ground** (Maresfield Rec) instead of the stadium.
- **New UI style, Punch Pads** (now the default): gunmetal console, bright orange, yellow, blue, green, purple and white pads, and new fonts: Bungee for the pads, titles and call-outs, Rubik for smaller text. The other styles are still in Options → Sound & more → UI STYLE.

### Changed
- **HUD:** big call-outs ("GREAT SAVE!", "WAVE 3") are now coloured banners that slam in and snap shut. Score popups are chunky coloured chips that pop in and out. On the big screen the score rolls up with a "+points" flash, and the combo and wave sit in coloured pills. The wrist hologram is unchanged.
- **Pad text always fits:** every label is sized to fit its pad, wrapping between words when that helps. A new test checks every pad on every page in every UI style.

### Fixed
- **LICENSES.txt is written again when publishing:** the tool the upload script uses was missing. It now includes Godot's notices and all the font licences.

## v1.10.0: "Total Football"

### Changed
- **The robots actually dribble now.** The ball carrier knocks the ball ahead in touches and runs onto it, steers round defenders in the way, and beats them with skill moves: a robotic shoulder-drop jink and a burst past, instead of the ball jumping sideways.
- **Real tackling.** Defenders close down and either poke the ball away with a standing tackle (they don't always win it; sometimes the attacker rides it and skips past) or fly in with a slide.
- **Brutal slide tackles.** Faster, longer slides that throw up sparks along the grass. Big hits launch the victim into the air in a cartwheel; he lands in a heap with a dust and spark burst, sometimes minus an arm. Now and then an attacker sees it coming and hurdles the slide, keeping the ball.
- **Fluid matches: the ball never teleports or stops dead.** It has real momentum: passes slow as they roll and the receiver takes it in his stride, tackles leave a loose ball squirting away, shots off the post rebound back into play, and the ball spins the way it is actually moving.
- **Play carries on from where the ball really is.** After you parry or block a shot, the match continues from your real ball wherever it ends up, still rolling. When you hold it and don't distribute, you roll it out to a defender. Their keeper rolls out saves to a team-mate.
- **Proper restarts.** Shots that go wide are goal kicks taken by a defender from the six-yard box; throw-ins, corners and goal kicks wait for the taker to get there, then a fresh ball appears. Throw-ins leave from over the robot's head.
- Back-passes to you are played from wherever the defender has dribbled the ball, with no jump.

## v1.9.0: "Big Moments"

### New
- **Saves feel bigger.** Hard shots you get a hand to now land with a split-second freeze, an impact ring and sparks; fast catches too. Great saves get a louder cheer and applause.
- **Near misses:** shots that fly just wide or over, or come off the woodwork, make the whole stadium gasp ("JUST WIDE!"), with the announcer calling it.
- **Match atmosphere:** the announcer and crowd react to tackles ("What a tackle!", "Oh! That is a crunching challenge!"), shots off the post ("Off the post!", "It's hit the woodwork!") and corners ("Corner!"). Seven new announcer lines.
- **Goal replays in season matches:** when your team scores at the far end, the big screen replays it from a TV camera behind the goal ("Let's see that again!"); goals you concede are replayed too.
- **Graphics setting** (Options → Sound & more → GRAPHICS: Low / Medium / High). Low: fewer fans, no shadows, no grass tufts, 75% headset resolution and 2x anti-aliasing. Medium: most of the crowd, shorter shadows, 88% resolution. High: everything. Resolution and shadows change straight away; the crowd from the next match.
- **Two keeper buttons:** **A/X** passes to the teammate you're looking at (thrown out of your hands, or played along the ground from your feet; if nobody's there it goes where you look). **B/Y** kicks it long where you're looking: a drop kick from your hands or a big kick from your feet, harder the longer you hold. On the keyboard: E to pass, Q to kick. Recenter is now in the pause menu (it used to be B/Y).

### Changed
- **Hand-painted grass:** soft brush-stroke patches in a few tones of green, broad colour washes and the odd lighter dab, with just a hint of short-blade texture up close.
- **Painted pitch lines:** the markings are slightly patchy and see-through, like paint on grass, instead of solid white strips.

### Fixed
- **The crowd had no bodies on some graphics cards** (only heads showed). Fans are now built so their bodies always show.

## v1.8.1

### Changed
- **Back to the previous visuals.** The bright, saturated cel-shaded look from 1.8.0 was too much, so the lighting, colours, grass, stands and goals are back to how they were in 1.7.0. The fix for the hard seam in the grass stripes is kept, and so are all of 1.8.0's other changes (keeper body, leg saves, in-stride shots, passing).

## v1.8.0: "Arcade Polish"

### Changed
- **New art style: bright and stylised**, in the spirit of arcade football games. Cel-shaded (toon) lighting on everything, punchier colours and contrast, a deep blue sky, rich green grass with clean broad mowing stripes, teal stands and seats, cyan light bars, and a neon-lit back frame on the goals. Robots, gloves and scenery all share the look.
- **Your body in the headset** only appears when you really look down for your feet, and then it's just your socks and boots. Your legs are now sized to your height, so you stand tall instead of always crouching (the TV camera sees the whole robot keeper standing properly).
- **Leg saves are subtler**: a foot only slides out a little (at most about 40 cm) for a low ball, and only when you're moving towards it, by stepping or with the left stick. Hands are always the better save.
- **Match shots flow**: in open play the striker now shoots in his stride from exactly where the ball is. No more stopping, teleporting to a new spot, beeping and flashing red eyes; the ball just carries on as the real ball you have to save. (Free kicks and penalties are still set up properly with a whistle.)
- **More varied passing**: short passes along the floor, driven passes, chips over the top, long floated balls and low pinged switches, through balls into space for runners, and give-and-go one-twos where the passer bursts forward for the return. Carriers release the ball sooner, so the play flows. Strikers shoot from different distances each attack.

### Fixed
- A hard seam in the grass stripes right under you.

## v1.7.0: "Matchday Live"

### New
- **Penalty run-ups like real takers.** Robots now pick from eight run-ups: the standard angled run, a long sprint from the edge of the box, a two-step stab, a dead-straight run, a curved run from wide, a skip-hop just before the kick, a slow robot march then a burst, and a dead stop to wait for you to move before going again. Other shots get a few simpler run-ups too.
- **Matches feel more like real football.** Teams push up and spread wide when they have the ball and drop back narrow when they don't, and each robot drifts so the shape breathes. Carriers weave and jink past defenders. Overhit passes go out for **throw-ins** (ball held overhead, then thrown) and over the goal line for **corners** (whipped into the box for a header) and **goal kicks**. Their keeper **dives** at your team's shots (the wrong way when it goes in), shots can come **off the post**, and the scoring team runs to the corner flag to **celebrate** with arms up and jumps. The crazy slide tackles stay.

### Changed
- **Better-looking stadiums.** Real seats in every stand (one stand in your club colour), split into blocks by stair aisles, with empty seats, half-full blocks and packed ends so the crowd is no longer one solid slab. Fans now have arms (most throw them up when the crowd gets loud), trousers, scarves, hair and woolly hats, and some stand while others sit. There's a club-colour band along the front of each stand, glowing light strips under the roofs at night, and two team dugouts on the touchline.
- **Nicer goals and grass.** The nets hang and sag like real nets and use a diamond mesh; the posts have dark collars at the grass. The mowing stripes swap light and dark depending on which way you look along them (like real cut grass), stadium pitches have a faint cross-cut, the grass is a richer green and has a soft sheen at low angles.
- **Robots move like robots.** Their joints move in quick servo "ticks" instead of a smooth human swing, feet land with a heavy clunk, arms pump stiffly with elbows locked, the head stays level and locked on, and when they're standing about the head scans in sharp snaps.

## v1.6.0: "Rocket Gloves"

### New
- **You're a robot keeper.** Your keeper is a robot like the others: robot head, chassis and legs, with your keeper kit (shirt, shorts, socks and boots) worn over the top. In the headset you only see your body when you look down; the TV camera always sees the whole robot.
- **Floating rocket gloves.** Your gloves aren't attached to your body any more: they float on rocket boosters. The boosters fire (flame, glow and a whoosh) when a glove stretches out for a fast save.
- **Wrist hologram.** The score, multiplier, lives or match info and focus meter are now a hologram that flickers on above your wrist when you look at it, and fades when you look away.
- **2 player: mouse controls for the striker.** Move the mouse to aim at the goal, hold left click to fill the power meter (it rises and falls, so let go at the right moment), mouse wheel for the shot type, right click for a dummy run-up. Curl shots bend in by themselves. There's a big power meter on the PC screen and a steady striker camera behind the penalty spot. A gamepad still works.

### Changed
- **The ball is much easier to see at a distance**: it's drawn bigger, glows and has a soft halo the further it is from you, so you can follow it through a crowd of robots in a season match. Close to you it's a normal ball.
- **Stronger vibration** whenever you touch the ball: every pulse is now long and strong enough to feel on PSVR2 Sense controllers through SteamVR.

### Fixed
- **Moving with the left stick no longer stretches your hands out.** Walking was being read as a fast fling of your arms (dive assist).
- **2 player: "Waiting for the robot..." forever.** After a season match the robot was left in match mode and never took the next shot. It's now reset whenever a game starts or you go back to the menu, so 2 player (and every other mode) always starts with a robot that moves.
- **Leaving 2 player** always puts everything back: the power meter and striker panel go, the keeper's keys and camera return to normal.

## v1.5.3

### Fixed
- **Upload to GitHub** could fail with "rejected (non-fast-forward)" when pushing to the public repo. The script's local copy of the public repo now always starts from what's on GitHub before adding the new release files.

## v1.5.2

### Fixed
- **Upload to GitHub** stopped with "Cannot find drive. A drive with the name 'E' does not exist" while looking for Godot. It now skips drives that aren't there.

## v1.5.1

### Changed
- **Upload to GitHub** now publishes to both repos properly every time. It exports a fresh Windows build with Godot first, so the public download always matches the source, checks the build's version number, writes the licences file, then pushes the source to the private repo (tagged with the version) and uploads the build to the public repo as that version's release, with the changelog in the zip. Press **S** when it asks to push the source only.

## v1.5.0: "Six-a-Side"

### New
- **"Logan Presents" splash** before the title, then a much meatier title punch: a split-second hit-stop, a shockwave ring and flash, "BOOM!", a heavy rumble, and the ball rockets into the top corner of the far net with a goal horn, a cheer and confetti before the menu opens.
- **6-a-side season matches.** Five outfield robots and a keeper on each side, with faster pacing: you're never left with nothing to do for more than about 15 seconds.
- **Brutal slide tackles.** Robots fly in on the ball carrier and send them tumbling. Hard ones leave the victim sparking for the rest of the match, and sometimes an arm comes clean off. A foul by your team near your box gives a free kick, and in the box a penalty.
- **Full keeper body with legs.** If you step towards a low ball, your leg reaches out to block it ("SAVED WITH THE FOOT!"). Hands are still the safest way to save.
- **Back-passes to your feet.** A back-pass is trapped at your feet. Tap A/X (E on the keyboard) to pass along the ground where you're looking, or hold it for a shot.
- **Drop kicks.** Holding the ball in your gloves? Press A/X to drop-kick it upfield (hold for more power).
- **Knock robots over.** A ball you kick or throw hard at an opposing robot (or the training robot) makes it stumble, and sometimes fall flat.
- **Reflex test.** 15 shots from a ball machine at close range; it measures your average and fastest save time.
- **Practice options.** Reactions (ball machine), free kicks, penalties, or everything.
- **Controls page** (More modes → Controls) with button glyphs that match your controller: PlayStation VR2 Sense, Meta Quest / Touch, Valve Index, Vive wands, Windows Mixed Reality or keyboard and mouse, plus the 2-player striker's gamepad (Xbox, PlayStation or Switch style). Punch CONTROLLER to pick a different set if it guessed wrong.
- **Crests and kits for every Robo League club.** Each club has its own crest (on the scoreboard, the season page and the robots' chests) and a patterned kit: Cogsworth hoops, Voltchester chevron, Boltham stripes, Circuit sash, Steelport halves and Mega-Bot pinstripes.

### Changed
- **New gloves** closer to the reference photos: fanned, rounded fingers, a fleshy thumb pad, a contrast panel down the index side, and a robot hand inside. You can see the metal wrist joint, hydraulic rods and a glowing ring between the cuff and your sleeve.
- **The thumb** now sits low on the hand and angles out and forward, as on a real glove. Before, it pointed back into the hand.
- **Penalties:** in a penalty (shoot-out, penalty practice or a penalty in a match) you can only move sideways along your line. Everywhere else you can move freely.
- **Maresfield Rec** is closer to the real layout: the heath and gorse on one side, the tree belt along the High St, trees and conifers at the far end, the hut, and the play park at the back with its climbing frame, slide, swings, roundabout and springers.
- **The big screen** is raised above the stand roofs in the big stadiums, so it no longer clips into the stand.
- **Long-sleeved keeper shirt** on your keeper body, matching your sleeve in VR.

### Fixed
- More Modes had lost its BACK button.

## v1.4.0: "Full Pitch"

### New
- **Season matches on a full-size pitch.** Both teams of robots play the match out in front of you on a 105 x 68 m pitch, with a goal at each end. They pass, dribble, press and lose the ball. Your team attacks the far goal, and you see your goals go in. The opponents shoot at you from all ranges, from the edge of the six-yard box out to 30 yards, with the odd free kick (with a wall) and penalty.
- **Back-passes.** Your defenders sometimes knock it back to you. Catch it, block it or punch it clear. Let it roll past you and it's an own goal.
- **Match length.** Season matches last 10 minutes by default. Change it to 5, 15, 20, 30 or 45 minutes in *Options → Match, sound & more*. The scoreboard clock always runs to 90', with a half-time whistle.
- **New gloves, based on modern roll-finger keeper gloves:** broad padded fingers, latex that wraps round the sides, a padded backhand, a raised emblem, a wide wrist strap with your number on it and a long cuff. There are six ready-made designs: Club Colours, Teal Camo, White Gold, Red Strike, All Black and Volt. You can then change the pattern (plain, camo, lines, strike or ribbed) and the main, detail, palm and strap colours on the **Gloves** page, with a live preview. Every design is available from the start.
- **Move with the left stick.** Shuffle along your goal line and come off it (up to 3.5 m) to cover more of the goal. It's smoothed, it goes back to the middle at every kick-off, and it can be turned off in the options. On desktop it's A/D and W/S.
- **Save with your face and body.** The keeper now has a proper body: head, shoulders, arms (from your shoulders to your gloves) and legs, all turning with your head. A ball that hits you is a save once it bounces away ("SAVED WITH THE FACE!"), and a goal if it squirms in.
- **Maresfield Rec.** The training ground is now Maresfield Recreation Ground: the brick pavilion and gravel car park behind the goal, wooden bollards, the green welcome sign with sunflowers under a big tree, the stoolball strip and its white sightscreen, the wooden hut, the fenced play area, big old trees all round, red-roofed houses, the High St lane and fields beyond. Practice and the tutorial are played there, in daylight or at dusk.

### Changed
- **Career mode removed.** The season is the career now. The first match after the tutorial is your first season match, and the Career medal is now the **Winner's medal** (5, 15 and 30 season wins).
- **Pause button** pauses and unpauses, with one press counted once even if a controller reports it twice.
- **No more accidental mode starts.** After a page changes, buttons ignore punches for a moment, and a glove already inside a button has to come out before it can press it. *More modes* is rearranged too: nothing that starts a game sits where the *More modes* button was.
- **2 player works without restarting.** The headset now always renders on its own, and the PC screen has its own camera. It switches to the TV camera for the striker during a 2-player match, and the *PC screen* option (headset view or TV camera) changes straight away.
- **Better robots.** Glossy clear-coat shells with a rim light, pectoral and ab plates, light strips down the flanks, arms and thighs, a brow ridge and jaw guard, team-colour shorts and socks, shin guards and wrist bands. Small details aren't drawn from far away, so a pitch full of robots stays fast.
- **Better grass.** Real grass blades round your goalmouth, fine blade detail close up, rougher grass beyond the lines, worn goalmouths at both ends, and on the rec wobbly mowing stripes and sun-dried patches.
- **The big screen** now stands in a corner of the pitch, angled at your goal, so it never blocks the match.

### Fixed
- **Title screen ball is always in reach.** The "punch the ball to play" ball now follows your head and floats at chest height just in front of you, standing or seated, wherever you face. Before, it could end up out of reach above the goal. Pulling a trigger also starts the game.
- **Gloves follow your hands.** The game now checks which controller pose names SteamVR reports and uses the first one that tracks, and writes it to the log.

### Also changed
- **Punching the title ball sends it rocketing away** at over 55 m/s (about 200 km/h), with a cannon boom, a crowd roar and a big rumble.
- **Press Start to pause.** The Start/Menu/Options button on either controller, a gamepad's Start, or Esc pauses the match and opens the pause menu (Resume, Recenter, Quit). Press it again or punch RESUME to carry on. Every controller button press is written to the log, to help map buttons on new controllers.

## v1.3.0: "Matchday"

### New
- **Season mode.** Maresfield Dynamo FC plays the Robo League against five robot clubs, each with its own colours and style of play. There's a league table, fixtures and results. Your team scores from open play, and catching the ball can start a counter-attack. Finish in the top two to reach the Robo Cup Final against Mega-Bot Galaxy, where a draw goes to penalties.
- **Daily challenge.** Twelve shots that are the same for every keeper in the world, each day. Your best score and daily streak are saved, and there's a daily online leaderboard.
- **Club badge and kits.** The Maresfield Dynamo JFC badge is the club crest. The home kit is orange with black numbers and the goalkeeper kit is purple with a black number. You see your purple sleeves in VR, and the TV-camera keeper wears the kit.
- **Kit and crest designer.** Pick your home and keeper colours, number colours, and a crest shape (club badge, round, shield or diamond) with badge colours. The Club Colours gloves, pitch-side boards, corner flags and home fans all follow.
- **Trophy cabinet** with eight trophies to win: league, cup, career medal, Golden Glove, daily streak, boss buster, worldie and a 100-save century.
- **Save ratings.** "Worldie!", "Fingertip save!", "Point blank!" and "Safe hands!", scored by your reach, reaction time and the ball's speed, each with bonus points.
- **End-of-match highlights.** Your three best saves replay in slow motion on the big screen at full time.
- **Music.** A menu theme and a match track that builds layer by layer as your combo grows.
- **Stadium announcer and crowd chants.** For example "Save by number one, Logan!" (the announcer knows over 140 first names), plus "Maresfield!" chants.
- **Splash and title screen.** A logo sting with floodlights powering on, then punch the ball to play while the robot warms up.
- **Guided first launch.** "Welcome, Logan" → calibrate reach → tutorial → first match.
- **Simpler main menu** with six big buttons: Season, Daily Challenge, More Modes, My Club, Trophies, Options.
- **About page** with the version, credits and all licences, also shipped as LICENSES.txt.
- App icon, and the exe now shows "RoboKeeper VR 1.3.0" in Windows.

### Improved
- **Auto-pause** when you take the headset off, open the SteamVR menu, the headset loses tracking, or a controller disconnects (with a message saying which one).
- **Fade to black** between the menu and matches.
- **Haptics** scale with ball speed: a soft tap for a catch, a hard jolt for a rocket, and a double pulse for the big saves.
- Music and announcer volume settings under Options → Sound & More.

## v1.2.0: "Club Colours"

### New
- **Your team.** You're **#01 Logan** of **Maresfield Dynamo FC** by default. Change your name, shirt number and team under *My team*. Your team crest and name show in the menu header, on the scoreboard and on pitch-side boards. Your shirt number is printed on your glove straps and kit.
- **Menu redesign** in the Stadium Night style, with a club header on the main menu.
- **UI styles.** The game now has a consistent UI style sheet, with four looks to choose from under *Options → UI Style*: **Stadium Night** (default), **Broadcast**, **Clean Light** and **Neon Arcade**. Fonts, colours and button styles stay consistent across menus, the scoreboard, popups, the tutorial and the PC screen.
- New open-source fonts made for readability in VR: Space Grotesk, Inter, IBM Plex, Recursive and JetBrains Mono.
- Buttons are colour-coded by what they do: green to continue, red to quit or reset, gold for career.

### Fixed
- **Controllers not tracking.** The gloves now follow PSVR2 Sense, Index, Vive, WMR and Touch controllers. Before, they stayed on the floor. The game also checks which hand pose your VR runtime provides and uses that one.
- The PC-screen message banner is now centred.
- Menu panels keep their true colours under floodlights and at dusk.

## v1.1.0: "No Step Required"

You can now play the whole game standing still or seated. You never need to step.

### Play your way
- **Reach calibration.** Sweep your arms for 8 seconds and the goal sizes itself so every shot is reachable. Choose *Goal → Fit my reach*.
- **Dive assist.** Fling your arm out and your glove stretches out further, joined to your hand by a glowing beam, for full-length diving saves. Strength is set in Options: Off / Low / Normal / High.
- **Seated mode.** The pitch is lowered to your reach so you can still save low shots.
- **Glove fit.** Tilt, twist and nudge the gloves until they sit right on your controllers.
- **Comfort options.** Show the HUD on your left or right wrist, reduce flashing effects, and turn replays on or off.

### New modes
- **Career.** 12 levels across 5 venues, from a Sunday-league park to the World Final. Earn up to 3 stars per level. Some levels have special objectives, such as catches or a clean sheet.
- **Tutorial.** 7 guided steps: block, dive, catch, throw, punch, slow-mo and reading the robot.
- **2 Player.** The keeper plays in VR while a striker on the PC keyboard or gamepad aims, picks the shot type, adds curl and can fake a dummy run-up.
- **Online leaderboard** for Arcade scores. It needs a free 5-minute setup: see the README.

### New robot tricks
- **Feints.** Stutter-step run-ups, looking one way and shooting the other, and the cheeky **Panenka**.
- **Free kicks.** A wall of BLOCK-4 defenders jumps as the ball is struck, and the shot dips over or curls around them.
- **Rebounds.** If you parry into the danger zone, POACHR-7 sprints in for a first-time finish. If you clear the ball wide instead, you get a bonus.
- **Boss waves every 5 waves.** TWIN-STRIKE fires two cannons at once, GIGA-BOT is huge and stomps, and PHANTOM's shots vanish mid-flight. Hit a boss 3 times with thrown balls to defeat it.

### Atmosphere
- **Instant replays.** Great saves play back in slow motion on the giant screen.
- **Weather and time of day.** Rain makes the grass skid and the gloves slippery, snow makes the ball die and turns it orange, wind bends shots and the corner flags show which way it's blowing. Day, dusk and night lighting.
- **Stats.** A goal-zone heat map of where you let shots in, save % for each shot type, plus dives, catches and best combo.
- **Glove designs.** 8 designs unlock with career stars.

### Looks and sound
- Remodelled robots with rounded armour, shoulder lights and an LED face screen with expressions (happy, sad, angry, stunned, focused).
- Gloves now have two-jointed fingers, knuckle guards and wrist straps.
- Crowds now have heads and the stands have roof trusses. Added corner flags, dugouts, banners, parkland and houses.
- Re-synthesised crowd made of real-sounding voice formants (chants, oohs, groans, cheers with applause), plus new dive whoosh, boss, weather and UI sounds.

### Under the hood
- **TV camera PC view.** The monitor can show a broadcast camera with its own HUD instead of mirroring the headset.
- Automated tests now cover shot accuracy with wind and free kicks, glove blocking up to 45 m/s and dive-assist reach.

## v1.0.0
- First playable version: Arcade, Practice and Shootout, the STRIKR-9000 robot with 7 shot types, catching and throwing, slow-mo focus, a stadium and a scoreboard.
