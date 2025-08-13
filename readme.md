massive thanks to the creators of all these amazing scripts. i simply got bubblegum and stacked them together. shout out to all the makers of
Auto Cards, Story Arc Engine, True Auto Stats, Narrative guidance overhual, Random events, ReputeX, System requests, Epoch time System

⏳ Epoch Time System
A self-contained time-tracking and world clock module for AI Dungeon scenarios. Tracks absolute and relative time across player actions, sleep/travel skips, and narrative arcs. Designed to function beyond the limitations of standard JavaScript Date—from the dawn of time to the heat death of the universe.


🚀 Features
Monotonic world time independent of player behavior
Custom EpochDate engine handles ±1 quadrillion years
Auto-advances every N minutes (default: 6) per turn
AI-friendly headers with fuzzy-matched events and pacing instructions
Optional event instructions to stage time-sensitive beats as sluglines
Supports Everyday, Weekday, and Weekend rhythm keywords
Built-in timestamp cleanup to prevent AI fixation on static time


📆 Time Header Output

[ stage event actions as sluglines ]
[ event: shrill school bell pierces the air ]
[ time: Monday 08:54 2025-10-01 | Z-Day +1 ]




Time – Always reflects in-world progression, even if the AI stalls

Event – Context-sensitive label from timeline or weekly rhythm

Instruction – Optional nudge to frame events cinematically or manage pacing


📅 @eraTimeline – Absolute Events

08:00 2025-09-01 - 15:00 2025-09-01: First Day of School
10:00 2025-10-15 - 01:00 2025-10-18: Midterms



Ranges or single timestamps
Multiple concurrent events supported
Active ±timeIncrementMinutes fuzz around boundaries
Great for plot beats, pressure clocks, foreshadowing, or surprise twists


🔁 @rhythmSchedule – Weekly & Daily Rhythms

Monday:
04:30 EXT. CALLE wood-smoke drifts low as bakers fire their ovens
04:45 EXT. CANAL the Matins bell rolls across the water
05:10–05:30 EXT. WATERWAY Gondoliers steady their oars

Everyday:
02:00 bell tower tolls

Weekend:
07:30 late market opens, smell of fried dough drifting across the plaza

Everyday:
02:00 bell tower tolls

Weekend:
07:30 late market opens, smell of fried dough drifting across the plaza



Supports Everyday, Weekday, or Weekend in addition to named days
Time ranges or single moments
Fuzzy matching around current time for natural trigger points
Perfect for schools, military bases, shift cycles, or looming deadlines


🧠 Engine Details


EpochDate uses BigInt for near-unlimited year range
Simplified leap years/month lengths for speed and stability
Day-of-week via Zeller’s Congruence
Timestamps in story are automatically consumed to avoid AI “time micromanagement”
Event instruction only prints if @includeEventInstruction:true and an event is active


🪄 Why Use It?

“The AI doesn't know how to track time. Now it doesn’t have to.”


Keeps pacing consistent, even if players dawdle
Natural urgency and rhythm without manual bookkeeping
Works for horror clocks, military schedules, magical rituals, school bells, or apocalypses
Lets the world breathe — time flows, the AI reacts


🧪 Example Scenario Use Cases


Magic School – Bells ring, class starts, secret rites at midnight

Zombie Survival – “Z-Day +4”, full moon at 01:00, rain at dusk

Chrono Trigger-style – Jump 65 million years without losing the beat

Vampire Campaign – Pre-sunrise warnings at 05:30; dawn burns at 06:00


⚙️ Configuration Options (in Epoch card notes)
If no card is present, one is auto-generated with sane defaults (year = 2025):

@timeIncrementMinutes:6
@instructionalText:[ enforce circadian rhythm. World continues indifferently—in medias res. Only print HH:MM YYYY-MM-DD headers on time skips (sleep, travel, drift, scene change) ]

@includeEventInstruction:true
@eventInstruction:[ stage event actions as sluglines ]
@includeWeekday:true

// Static Era Label:
//@eraName:War of the Lance

// Relative Counter:
//@eraEpoch:Z-Day
//@eraStart:2025-01-01
//@eraAdvance:daily

// Timeline-Based Events:
//@eraTimeline:
//08:00 2025-09-01 - 15:00 2025-09-01: First Day of School
//05:30-06:00 hurry, sunrise is coming at 6. Dawnlight burns, blinds, and weakens

// Weekly/Daily Rhythms:
//@rhythmSchedule:
//Monday:
// 04:30 EXT. CALLE wood-smoke drifts low as bakers fire their ovens
//Everyday:
//02:00 bell tower tolls
//Weekend:
//07:30 late market opens



📜 License
MIT permissive license
