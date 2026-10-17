# Changelog

Every change gets a new build number. Not every build is published: a GitHub release lists everything since the last one, so read down to the previous published version.

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
