# Magic Kingdom Content Audit — v1

Status: first audit pass. This file is a planning artifact and does not change the live app.

Audit date: 2026-09-19
Primary source standard: current official Walt Disney World pages and current official park map/directories. Third-party sources may later supplement planning estimates, but not replace official names, locations, operating status, or official links.

## Official coverage benchmarks
As of the audit date, Disney's official Magic Kingdom rides/entertainment directory returns **64 things to do**. Disney's official Magic Kingdom dining directory returns **40 dining options**. Those totals include seasonal/rotating entertainment and special dining events, so the app should not blindly treat every result as a permanent daily offering.

Official directories used:
- Attractions/experiences: https://disneyworld.disney.go.com/attractions/map/magic-kingdom/
- Entertainment: https://disneyworld.disney.go.com/entertainment/magic-kingdom/
- Dining: https://disneyworld.disney.go.com/dining/map/magic-kingdom/
- Park overview/map access: https://disneyworld.disney.go.com/destinations/magic-kingdom/

## What must be represented in the master content database
### Rides and attractions
Every currently offered ride and guest-facing attraction, including high-profile and easy-to-miss experiences.

Examples that must be present and verified:
- Astro Orbiter
- The Barnstormer
- Big Thunder Mountain Railroad
- Buzz Lightyear’s Space Ranger Spin
- Dumbo the Flying Elephant
- Enchanted Tales with Belle
- The Hall of Presidents
- Haunted Mansion
- “it’s a small world”
- Jungle Cruise
- Mad Tea Party
- The Magic Carpets of Aladdin
- The Many Adventures of Winnie the Pooh
- Peter Pan’s Flight
- Pirates of the Caribbean
- Prince Charming Regal Carrousel
- Seven Dwarfs Mine Train
- Space Mountain
- Swiss Family Treehouse
- Tiana’s Bayou Adventure
- Tomorrowland Speedway
- Walt Disney World Railroad
- Tomorrowland Transit Authority PeopleMover
- Walt Disney’s Carousel of Progress
- Monsters, Inc. Laugh Floor
- Mickey’s PhilharMagic
- Country Bear Musical Jamboree
- Casey Jr. Splash 'N' Soak Station
- Main Street Vehicles
- A Pirate’s Adventure ~ Treasures of the Seven Seas
- Smellephants on Parade

### Entertainment and parades
Official entertainment directory currently includes items such as:
- Happily Ever After
- Disney Festival of Fantasy Parade
- Disney Starlight: Dream the Night Away
- Disney Adventure Friends Cavalcade
- The Dapper Dans
- Casey’s Corner Pianist
- Mickey’s Magical Friendship Faire
- seasonal/special-ticket entertainment where applicable

Each show/parade record needs:
- official name
- location
- approximate runtime
- recommended arrival buffer
- indoor/outdoor
- weather sensitivity
- planning-time show pattern (2026 estimate when useful)
- actual published performance times once Disney posts them
- official Disney page

Disney currently lists Festival of Fantasy at 12 minutes on its official page; this is the kind of runtime data that should be stored rather than guessed in the itinerary.

### Character experiences and smaller experiences
The audit must explicitly check character greetings, interactive experiences, atmosphere entertainment, castle experiences, play areas, and any rotating offerings so they are not lost simply because they are not rides.

Examples to verify individually:
- Princess Fairytale Hall greetings
- Meet Ariel at Her Grotto
- Mickey/Town Square character offerings
- Cinderella Castle guest-facing experience
- seasonal/rotating character appearances
- Disney Fab 50 / interactive offerings if still active and relevant in 2027

## Dining coverage
Official dining directory currently lists 40 Magic Kingdom dining options, including restaurants, quick service, snacks, kiosks, lounges, and special dining events.

The app should preserve **all useful dining choices**, not only selected reservations.

Core table-service and reservation locations to verify individually:
- Cinderella’s Royal Table
- Be Our Guest Restaurant
- The Crystal Palace
- Jungle Navigation Co. LTD Skipper Canteen
- Liberty Tree Tavern
- The Diamond Horseshoe
- The Plaza Restaurant
- Tony’s Town Square Restaurant
- The Beak and Barrel

Quick service/snack locations to verify individually include:
- Casey’s Corner
- Columbia Harbour House
- Cosmic Ray’s Starlight Café
- Pinocchio Village Haus
- Pecos Bill Tall Tale Inn and Cafe
- The Friar’s Nook
- Gaston’s Tavern
- Main Street Bakery
- Sleepy Hollow
- Storybook Treats
- Sunshine Tree Terrace
- Aloha Isle
- Cheshire Café
- The Lunching Pad
- Liberty Square Market
- Golden Oak Outpost
- Tomorrowland Terrace Restaurant
- Prince Eric’s Village Market
- Tortuga Tavern
- Energy Bytes
- Plaza Ice Cream Parlor
- Auntie Gravity’s Galactic Goodies
- Astrofizz

Each dining record should have:
- official name
- park + land/area
- service type
- cuisine
- reservation required/recommended
- approximate meal duration
- mobile order availability when relevant
- official Disney restaurant page
- **direct official menu link where Disney provides one**
- map/location information
- backup-meal suitability

## Link audit rules
Every tappable link in the app should be checked for:
1. correct official destination
2. no obsolete attraction name/slug
3. no broken or old PDF/menu link when a current dynamic Disney menu page exists
4. HTTPS
5. useful fallback when Disney changes a page

Preferred fallback hierarchy:
- exact official experience/restaurant page
- park-specific official directory
- official park overview/map page

The app should never leave a dead button with no explanation.

## Map/location normalization
The routing engine needs a canonical area for every experience. UI labels and data should use the same land/area terminology everywhere.

Examples:
- Bibbidi Bobbidi Boutique → Cinderella Castle
- Cinderella’s Royal Table → Cinderella Castle / Fantasyland context
- Mickey’s Magical Friendship Faire → Cinderella Castle Forecourt
- Festival of Fantasy Parade → route + selected viewing zone rather than one generic land

Location records should support routing coordinates/waypoints separately from the human-readable area label.

## Master record fields
Every experience should eventually have one canonical record containing:
- id
- official name
- type
- park
- land/area
- routing point/coordinates
- map number if current map supplies one
- short description
- approximate experience duration
- queue/wait model category
- show runtime + arrive-early buffer when applicable
- height requirement
- intensity
- indoor/outdoor
- heat/rain value
- Lightning Lane status/rules
- Rider Switch relevance
- party participation rules
- official Disney URL
- official menu URL when dining
- seasonality/status
- last verified date

## User-specific permanent rule
Mission: SPACE is a hard exclusion for the trip. Everything else should default to **want to experience this trip** unless later excluded by the user or by a specific party member.

## Next audit passes
1. Compare every Magic Kingdom canonical item against the current app database and mark: present / missing / duplicate / outdated name / wrong land / broken link / incomplete metadata.
2. Repeat the same official-source audit for EPCOT, Disney’s Hollywood Studios, and Disney’s Animal Kingdom.
3. Audit all restaurant/menu links.
4. Audit current official park-map links and map-number references.
5. Build a machine-readable canonical content file for the new planning engine.

## Source notes from first pass
- Official Magic Kingdom attraction directory: 64 things to do on 2026-09-19.
- Official Magic Kingdom dining directory: 40 dining options on 2026-09-19.
- Official entertainment listings include daytime and nighttime parades plus atmosphere entertainment, demonstrating why the audit cannot be limited to rides.
- Festival of Fantasy's official page lists a 12-minute runtime, confirming that show/parade duration data can and should be stored separately from arrival buffer.
