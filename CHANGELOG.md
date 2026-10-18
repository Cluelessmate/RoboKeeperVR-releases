# Changelog

Every change gets a new build number. Not every build is published: a GitHub release lists everything since the last one, so read down to the previous published version.

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
