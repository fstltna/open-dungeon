## OpenDungeons Release Notes

This file contains the subsequent release notes for each version of
OpenDungeons since version 0.4.7, in reverse chronological order.

The numbers preceded by a hash (e.g. #9) reference GitHub issue numbers on
our repository at https://github.com/OpenDungeons/OpenDungeons

### Version 0.7.1 - 24 Aug 2016

**Highlights:**

* Fixed crash when entering editor (#1246)

**General:**

* Added a minimap that displays the whole map (#1246)
* Added support to change overall ambient lighting factor in game settings (#1253)
* Fixed bug with rooms not giving vision when built on an old enemy room (#1251)

### Version 0.7.0 - 30 July 2016

**Highlights:**

* Multiplayer lobby using a master server, to find other players all over the world
* Animated main menu with scripted events!
* Play voice-overs on some game events
* Vastly improved creatures behaviour, including support for spell casting,
  elemental damage, better ranged behaviour, and many customisation features
* New rooms: Arena, Bridges, Casino, Prison, Torture room
* New creatures: Cultist, Elf, Dark Elf, Lava Spawn; Lich, Monk, Nature Monster,
  Rat, Roach, Skeleton
* New spells: Defense, Eye of Evil, Slow, Strength, Weak

**General:**

* Play sounds on some game events, with voice-overs by Eugene Loza (#393)
* Unit tests (#578) and continuous integration (#960)
* Display stacktrace in the logs on game crash (#1155)
* A lot of code refactoring and technical improvements!
* Culling of tiles and entities outside the camera range, increasing performance
  (#1198)

**Multiplayer:**

* Master server and in-game lobby, allowing to find available servers
  waiting for players (#777)
  - Chat support in the lobby/seat configuration menu (#1029)
* Improved game saving, only allowed for the server side (#938)

**Gameplay:**

* Creatures behaviour:
  - New KO state as an alternative to death (#751)
  - Vastly improved fighters behaviour (#957)
  - Vastly improved workers behaviour (#1004)
  - Implemented creature skills, abstract mechanism for both fighting
    and spell casting (#959)
    * Creature spells: Defense (#986), Slow, Strength, Weak (#1001)
  - Elemental damage type, creating a triangle relationship between
    strength and vulnerabilities (physical, magical, elemental) (#877)
  - Make creature moods configurable like other parameters (#979)
  - Make creature behaviours fully configurable (#992)
  - Creatures grow bigger as they gain levels (#992)
  - Creatures will use the closest room if multiple are available (#1172)
  - General creature balancing (ongoing effort) (#985, #1001)
* New rooms/traps:
  - Arena, where creatures fight one on one or in a battle royale until
    KO to earn XP (#699)
  - Bridges (wooden for water, stone for water and lava)(#191)
  - Casino, where creature spend their wages (#1046)
  - Prison, turns both foes and friends into skeletons (#754)
  - Torture room (#1058)
* New gem tile, provides an infinite source of gold (#735)
* Trap balancing by making them take defence skills into account (#1067)
* New setting to select the AI level (Easy and Normal so far) (#933)
* New Eye of Evil spell

**Levels:**

* Completed user maps support: official maps and user-made maps are
  properly differentiated (#383)
* New multiplayer level: Angel Nest (#1130)
* New skirmish levels: Duel to Death, Forgotten Treasures (#1130)
* Stonekeep Siege remake for bridge usage (#929)
* Dehardcoded portal spawn rate (#1119)
* Enemy and rogue portals at visible at game start (#1230)

**UI:**

* Camera management feature using the middle mouse button (#892)
* New map creation menu; missing part is the setup of level parameters
  like configured seats, etc. (#22)
* Main menu usability improvements (#1050)
* Display a scriptable 3D scene on the main menu, with lights and
  particle effects (#1064, #1074)
* Fixed spell cooldown display (#974)
* The two minimap styles can be now be used (#1217)

**Graphics:**

* New icons for stunned and jailed (#950)
* New creatures:
  - Cultist, by Danimal, Dread Knight and Katarzyna Zalecka (#1181)
  - Elf and Dark Elf, by Contmike and Danimal (#1016, #1017)
  - Lava Spawn, by piacenti, hwoarangmy et al. (#1190)
  - Lich, from Summoning Wars (#992)
  - Monk, by CDmir and hwoarangmy (#1190)
  - Nature Monster, replacing the BigKnight, by CDmir (#1069)
  - Rat, replacing the Wyvern, by CDmir (#1072)
  - Roach, by Danimal and Atmostatic (#962)
  - Skeleton, from Summoning Wars (#992)
* New objects:
  - Room objects:
    o Casino beer stand and poker table, by Danimal (#1054)
    o Roulette, by hwoarangmy (#1053)
    o Torture room object (#1115)
  - Weapons:
    o Basic axe, hammer, shield and sword, by YD (#1115)
    o Bow, by YD (#1065)
    o Crossbow, by Lamoot (#1065)
    o Good hammers, good shields, evil shields (#1115), good swords (#1123)

### Version 0.6.0 - 8 September 2015

**Highlights:**

* New spell logic with cooldown, targets and cost management
* Fancy new spells: Heal, Explosion and Haste
* Particle effects!
* Reworked library logic and made research order configurable
* New creature overlays that show the creatures' mood
* Customisable creature sound effects!
* Doors to better block enemies and macromanage allies
* In-game settings menu support!
* New claimed walls graphics and various other graphical improvements
* New minimap camera with real-time rendering
* Dedicated server support with command-line parameters

**General:**

* Allow to display callstack when a crash occurs with MSVS2013 versions (#701)
* Homogenize how the callstack is displayed independently from platform (#701)
* Training room max training level is configurable in config/rooms.cfg (#698)
* Simplifications on mode handling (#670)
* Support for command-line options (see --help for details) (#688)
* Support for running the game as a dedicated (standalone) server (#665)
* Cheat added to unlock all skills at once (for testing purposes) (#729)
* De-hardcoded main menu music, now configurable (#632)
* Readded support for Direct3D renderer on Windows (#799)

**Gameplay:**

* New "Heal" and "Explosion" spells (#706)
* New "Haste" spell (#842)
* Spell logic implementation and improvements:
  - Initial spell logic: cooldown, targets and cost (#683)
  - Spells are triggered only when relevant and "Spawn Worker" has no
    cooldown (#710)
  - Spell cooldown is shown on the spell icon via a smooth animation (#867)
  - Handle spells through a spell manager (#727)
* Reworked library logic:
  - Working at the library generates grimoires that represent a fixed
    amount of skill points (#817)
  - Rooms and spells are unlocked when their skill points requirements are
    fulfilled (#817)
  - Easily configurable research queue (#817 #869)
  - Handle researches through a research manager (#843)
* Implemented doors (#732)
* Warn the player when they place a trap without having a workshop to craft
  it (#671)
* Do not trigger payday messages if no fighting creatures are alive (#715)
* Prevent slapping creatures with a right-click when dropping them (#722)
* Creatures bank account: payday gold is accumulated and dropped on death,
  unless the creature leave the dungeon (#704)
* Improved fighter creature behaviour so that they go to sleep or eat when
  tired or hungry, if they are not forced to do a given task (#807)
* Portal wave AI configuration: range and strategy (#855)

**Levels:**

* Removed levels redundancy between skirmish and multiplayer maps:
  multiplayer maps can now be loaded in singleplayer vs AI from the skirmish
  menu (#696)
* New multiplayer map "Ruins of the Confluent" (#847)
* Improvements to the "The Bridge" level (#673)
* Drop unused intermediate tile fullness values in the editor (#590)

**Graphics:**

* Better-looking claimed walls models (#808 #818)
* Many tileset improvements (#273 #694)
* Particle effects support on entities (#683 #709 #710 #711)
* Add a random offset to creature position on their tile to prevent
  meshes overlap (#660 #697)
* Gold stacks have random orientations and offsets (#725)
* Rotate tables in the workshop and place creatures accordingly (#573)
* Increase size of the scarab nose (#721)

**Sounds:**

* Add support for customisable creature sound effects (#126)
* Normalised all sounds and made them mono (#888)

**UI:**

* In-game settings menu, replaces the default OGRE launcher (#3)
* In-game and editor tabs are now displayed as thematic icons (#742)
* Research UI improvements:
  - Customisable research order with automatic dependency management (#577)
  - Progress bar for the research icons (#840 #867)
  - Buttons to unselect all skills or autofill the queue (#851)
* Creature overlays improvements:
  - Display 8 health states instead of 4 in the skull flags (#733)
  - Display an overlay with the creature's mood (#734)
* New minimap camera that shows the actual map models in top-down view (#530)
* Creature selection relies on selected tile instead of ray casts (#785)
* Display picked up entities at a fixed size regardless of camera zoom (#794)
* Made UI buttons more responsive to multiple clicks (#343)
* Allow to toggle the keeper hand and tile selector with F9 (#684)
* Improved cost tooltips for rooms, traps and spells (#713)
* Display human-readable name for rooms, traps and spells instead of engine
  name (#863)

### Version 0.5.0 - 20 April 2015

**Highlights:**

* Fog of War implemented
* Spell system implemented with two spells: Summon Worker and Call to War
* Research logic and UI implemented: rooms, spells and traps should now be
  researched in the library
* Saving/loading feature
* Creatures pay day implemented
* Portals can be claimed and can generate rogue waves that attack keepers
* Traps must be crafted in the workshop
* Creatures mood implemented
* Creature overlays show relevant information on hover (or when pressing ALT)
* Many GUI improvements

**General:**

* Saving/loading feature (#531 #534)
* Many hardcoded values were made configurable via config files
* Rooms and traps prices are configurable (#346)
* Tileset configuration and biomes support (#14)
* Test levels are noted as such (#381)
* Backup the last three game logs (#567)
* Packaging/installation improvements:
  - Provide an appdata.xml file (#356)
  - Drop bundled FreeMono.ttf font (#366)
  - Install engine config files in the proper arch-dependent path (#400)
  - Link icon with the game window and executable on Windows (#202)
* Removed the broken Culling Manager (#170)
* Disable angelscript as it is not used currently (#504)
* Code abstration to prepare unit tests (#592)
* Win32 build now produces a backtrace upon segfault (#680)
* Lots of bug fixes

**Gameplay:**

* Implemented the Fog of War (#295)
  - Implemented trap vision logic (#408)
* Implemented creatures pay day (#431)
* Implemented spells support and made workers spawned only via a spell (#16)
* Implemented the Call to War spell (#484)
* Implemented the library's research logic + research tree (#411 #508)
* Portals can be claimed (#588)
* The max number of creatures is configurable and influenced by the number of
  claimed portals (#588)
* Implemented rogue portal waves (#594 #607)
* Gold dropped on the floor follows the same mesh logic as the one in treasury
rooms (#279)
* Improved the camera perspective (#345)
* Readded default viewpoint support and made the V key cycle the viewpoints
  (#494)
* AI repairs damaged rooms (#375)
* Revised the creature spawning logic (#568)
* Updated the help window content (#548)

**Rooms:**

* The workshop replaces the forge for traps. The forge will be used later to
craft creature's equipment (#459)
* Traps are crafted in the workshop only when needed (#469)
* Add support to disable a room for a specific player in a specific level
  (#86)

**Creatures:**

* Workers: Gold dug from gold tiles is now visually carried (#407)
* Improved creature vision processing (#396)
* Added support to make creature prefer certain jobs (#354)
* Implemented creature mood (#11)
* Improved wall claiming order (#282)
* Research entities should be brought to the temple center (#576)
* Many fixes to workers and fighters behaviour

**UI:**

* Added the research tree GUI, currently not interactive (#517)
* Skull flag system to see current creatures health + level + team color
  (#519)
* Console code cleaned up and using CEGUI (#134 #299)
* Chat and event messages handling upgrade (#638 #642 #647 #654)
* Fixed tooltips behaviour (#337 #397)
* Added a check box, permitting to disable replay creation when quitting the
  game (#406)
* Improved the UI of Combo-boxes/Check-boxes, ... from generic to OD-like
  (#419)
* Display the number of controlled fighting creatures (#562)
* The keeper hand is used as an icon and is above the GUI (#547 #420)

**Graphics:**

* Better light handling (#446 #453 #456)
* Support for normals (#514)
* Added normals for many materials
* Use more keeper hand animations (#350)
* New workshop and corresponding elements (#609 #612)
* New training dummy and wall models for the training hall (#656)
* New troll bed (#503)
* New goblin + bed (#438 #449)
* New grimoire model (#544)
* New gold ground tile (#536)
* Fixed material errors (#529 #570 #606)
* Spring cleaning: unused textures, models and materials dropped (#492 #579)

**Editor:**

* Fixed adding/moving lights (#19 #20 #486)
* Fixed seeing traps in the map editor (#455)
* Made adding portals/temple possible via the editor (#192)

**Balancing:**

* Decreased amount of gold stored in each treasury tile to 1000
* Reduced creature walking speed by 10%
* Set armor increase/level to 0.1 for all creatures
* Raised experience gained from battle
* Creature regain mood points when hitting other creatures (#649)
* Reduced workers claiming rate (#650)
* Increased portal cooldown (+25%)


### Version 0.4.9 - 22 December 2014

**Highlights:**

* Multiplayer mode implemented using a server/client logic
* Functional AI implemented
* Core gameplay better defined
* Traps support
* Gameplay elements are configurable via ini-style files: levels, creatures
  characteristics, equipment, rooms and traps behaviour
* Lots of new rooms
* Revamped UI
* Replay mode

**General:**

* The game is stable and does not crash at exit
* The game does use threads only when needed (through sf::Thread)
* The code has been reviewed, is following conventions and does not use not
  GPL'ed code (#91)
* The license of every files is clear and defined in the CREDITS file (#93)
* Fix CMake basic invocation flags handling (#97 #42 #57 #58)
* Lots of bug fixes

**Game logic:**

* Spawn pools. Each faction has got their own configurable set of spawnable
  creatures
* Support for configurable alliances
* Support for three functional traps
* Optimize pickup/dig mouse handling speed (#103)
* Upgrade and completion of the creature stats format (#151 #152 #245)
* Creatures are spawned based on the available rooms and their active spots
  number and it is configurable (#257)
* Better balancing through the use of a global balance sheet (#153)
* Creature definitions are overrideable in levels to create special creatures,
  or bosses
* Equipment is now defined in the config/equipment.cfg file
* Creatures can spawn with default equipment
* Rooms and traps behaviour are now defined in config/rooms.cfg and
  config/traps.cfg files
* Creatures can be slapped to death. And more importantly, those creepy
  chickens can be slapped while on a claimed tile

**Rooms:**

* Treasure room
  - New Ground texture
  - New Gold stacks
  - First treasury tile owned costs 0 to avoid being stuck (#87)
* Portal
* Dungeon Temple
* Training Room
  - Class & file rename (RoomDojo -> RoomTrainingHall) (#83)
  - Better training dummy model
* Dormitory
  - Class & file rename (RoomQuarters -> RoomDormitory) (#83)
  - Beds are persistent on room expansion.
  - Beds are removed when creatures die.
* Hatchery & food system (#13)
  - All models integrated and the room can placed in game (#106)
  - The room spawns chickens wandering within the room limits.
  - Creatures can eat them visually and calm their hunger.
* Forge (not actually useful in this release)
* Library (not actually useful in this release)
* Crypt: spawns gnomes when you let enemy creatures decay there (#322)
* Add support to destroy rooms or traps using a new button to get a refund of
  half their price (#108)

**Creature behaviour:**

* Creature hunger system (#13)
* Creature behaving correctly in narrow passages (1-tile wide) (#4)
* Separate water/lava and flying collision handling (#101)
* Better creature fighting behaviour (#154)
* Make workers flee on first enemy blow (#90)
* Workers drop mined gold in the form of a pickable gold stack if no treasury
  room

**Modes and menus:**

* Game mode and editor mode functional with a level loading menu
* Minimap functional
* The basic menus are functional and look definite (#6)
* Factions and players are configurable in a lobby
* The remote clients shouldn't have to select a level (#70)
* Show room pricing (#89)
* Added buttons to grab workers and fighters easily in the menu (#84 #85)

**Basic AI (#15):**

* The AI can build every useful room
* The AI takes care of building rooms to get the maximum "active spots"
  (represented by room models)
* The AI can drop fighters nearby other enemy creatures to trigger some fun
* AI takes care of having at least one treasury tile before searching for gold

**Graphics & audio:**

* All models are displayed fine even if not yet using normals (#76 #100 #129)
* New and improved models (including a new set of beds)
* Added missing music/sounds (#95 #23)


### Version 0.4.8 - 25 April 2011

* Now with a new GUI, it is not completely done, but we are getting there. The
  mini-map and goals screen will be finished in later versions.
* Now with a main menu. We now have the code set up for a main menu, it will
  nicer in the next versions.
* Fixed a bug in the cannon trap, so it can now actually be placed. It
  actually also somewhat works and fires a moving projectile :)
* A lot of code refactoring, us devs love that :D
* Now with support for normal mapping.
* A claim tile sound, so you can hear you Kobolds working hard for you ;)
* A bunch of smaller bug-fixes
* The files structure has changed, the media folder is now gone.
* The dojo now got training dolls and training poles. (Thanks to p0ss)

### Version 0.4.7 - 8 March 2011

**Media Updates:**

* New creature models for 8 creatures.
* Several new meshes have been added to the game including the Portal, and the
  Cannon.
* A new GUI for the game which replaces the generic one we had before and also
  allows you to start the game from the system menu.
* Creatures now properly display the Die and Flee animations in combat.
* Two basic sound effects have been added, an attack and a dig sound.

**Code Updates:**

* Creatures, tiles, rooms, and traps are now colored according to which team
  they are on.
* Creature AI calculations have been improved so that combat now works
  correctly and it has been optimized significantly.
* Creature AI is now multithreaded, and the number of active AI threads can be
  set via the in-game console (the default is 2).
* Many, many bugfixes including fixing lots of race conditions present in the
  previous code and in the new multithreaded AI.

**Distribution:**

* A Windows installer (msi-package).
