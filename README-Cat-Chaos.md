# Cat Chaos

## Productivity Edition

**Cat Chaos** is a single-player strategy game about attempting to finish a work session while two cats create increasingly ridiculous distractions.

The cats have no respect for your deadlines.

## Play the game

The entire game is contained in:

```text
cat-chaos.html
```

No installation, account, server, or internet connection is required.

1. Download `cat-chaos.html`.
2. Open it in Chrome, Edge, Firefox, or Safari.
3. Select **Start the work session**.

The layout automatically adapts to phones and computers.

## Objective

Reach **100% Task Progress** within 12 turns while keeping:

- **Focus above 0**
- **Chaos below 6**

Each turn, one of the cats creates a new interruption. Choose how to respond while balancing productivity, focus, chaos, and your limited supply of treats.

## Starting resources

| Resource | Starting value | Purpose |
|---|---:|---|
| Focus | 6 | Your ability to continue working |
| Chaos | 1/6 | The current level of household disorder |
| Treats | 3 | A limited resource for redirecting the cats |
| Task Progress | 0% | How much work you have completed |

Focus can rise as high as 8. Chaos reaches its limit at 6.

## How to play

Each event presents:

- A cat-related disaster
- Three possible responses
- A different strategic tradeoff for every response

Select one response using the on-screen buttons.

On a computer, you can also press:

| Key | Action |
|---|---|
| `1` | Select the first response |
| `2` | Select the second response |
| `3` | Select the third response |

After making a choice, the game shows the outcome and updates your resources. Select **Continue working** to begin the next turn.

## The resources

### Focus

Focus represents your mental concentration.

Interruptions, multitasking, and direct conflict with the cats can reduce it. Restorative choices, clever redirection, and accepting occasional cat affection can increase it.

The game ends if Focus reaches 0.

### Chaos

Chaos measures how much control the cats have gained over the room.

Some choices solve an immediate problem but allow the room to become more chaotic. Other choices cost time or progress but reduce Chaos.

The game ends when Chaos reaches 6.

The room illustration on the computer version becomes messier as Chaos rises.

### Treats

Treats can quickly redirect a cat and often produce strong results. You only begin with three, so using one is a strategic decision.

Attempting to use a treat when the treat supply is empty costs additional Focus.

### Task Progress

Task Progress shows how close you are to completing the work session.

Reach 100% before the game ends to win.

## Winning and losing

You win when Task Progress reaches 100% while:

- Focus remains above 0
- Chaos remains below 6

You lose if:

- Focus reaches 0
- Chaos reaches 6
- The 12th turn ends before Task Progress reaches 100%

## Scoring

The final score rewards:

- Completed Task Progress
- Remaining Focus
- Remaining Treats

It subtracts points for remaining Chaos.

The scoring formula is:

```text
Score = Task Progress + (Focus × 5) - (Chaos × 6) + (Treats × 2)
```

The minimum possible score is 0.

## Performance ranks

| Score | Rank |
|---:|:---|
| 125 or more | S |
| 105–124 | A |
| 85–104 | B |
| 65–84 | C |
| Below 65 | CAT |

Winning and achieving a high rank are related but separate challenges. You can complete the task with a messy room and receive a lower rank, or replay to find a more efficient strategy.

## Current cat events

The game includes:

- Keyboard Occupation
- The Cup Is Too Close
- Haven't Eaten in 17 Minutes
- Tail in the Meeting
- Crash in the Other Room
- Your Chair Is Occupied
- Cable Ambush
- Mandatory Lap Time
- Sudden Zoomies
- Paper Inspection
- In. Out. In Again.
- The Delivery Box

The events are shuffled at the beginning of each session.

## Project structure

Cat Chaos is intentionally built as one self-contained file:

```text
cat-chaos.html
```

The file contains:

- HTML page structure
- Responsive CSS
- Room illustration
- Cat-event data
- Game rules and calculations
- Keyboard controls
- Start, gameplay, outcome, and ending screens

It has no external dependencies.

## Customize the game

Open `cat-chaos.html` in a code editor such as Visual Studio Code.

### Change the starting difficulty

Find the `start()` function:

```javascript
s = {
  focus: 6,
  chaos: 1,
  treats: 3,
  progress: 0
};
```

Examples:

- Increase `focus` for an easier game.
- Decrease `chaos` to start with a calmer room.
- Increase `treats` for more redirection options.
- Increase `progress` for a shorter session.

### Add a new cat event

Find:

```javascript
const events = [
```

Add a new event using this structure:

```javascript
[
  "EVENT TYPE",
  "🐾",
  "Event Title",
  "Describe what the cat has done.",
  [
    [
      "First response",
      "Brief explanation of the tradeoff.",
      { focus: -1, progress: 10 },
      "Describe the result."
    ],
    [
      "Second response",
      "Brief explanation of the tradeoff.",
      { treats: -1, progress: 14, chaos: -1 },
      "Describe the result."
    ],
    [
      "Third response",
      "Brief explanation of the tradeoff.",
      { progress: 6, chaos: 1 },
      "Describe the result."
    ]
  ]
]
```

Separate neighboring events with commas.

### Available effect properties

```javascript
{
  focus: 1,
  chaos: -1,
  treats: -1,
  progress: 12
}
```

- Positive values increase a resource.
- Negative values decrease a resource.
- Omitted resources remain unchanged.

### Change the colors

The primary color palette appears at the beginning of the `<style>` section:

```css
:root {
  --ink: #18202a;
  --paper: #fffaf0;
  --orange: #ff7a45;
  --yellow: #ffd85a;
  --blue: #3f80ff;
  --mint: #70dfbd;
  --pink: #ff9fc4;
}
```

Editing these values changes the visual theme throughout the game.

## Current version

Version 1.0 includes:

- One-player gameplay
- 12 randomized turns
- 12 original events
- Three responses per event
- Four-resource strategy system
- Limited treat mechanic
- Dynamic room chaos
- Mouse, touch, and keyboard controls
- Responsive phone and computer layouts
- Final scores and five possible ranks
- Instant replay
- Offline play

## Possible future additions

- Difficulty selection
- Custom cat names
- Cat personality selection
- Timed challenge mode
- Sound effects and mute control
- Unlockable events
- Combo bonuses
- High-score saving
- Two-player competition
- Additional rooms
- Cat costume cards

## Credits

Created as an original HTML, CSS, and JavaScript game.

**Title:** Cat Chaos  
**Edition:** Productivity Edition  
**Tagline:** Two cats. One deadline. Zero cooperation.
