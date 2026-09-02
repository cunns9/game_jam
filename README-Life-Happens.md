# Life Happens

**Life Happens** is a single-player life-strategy card game about balancing money, energy, time, and stability while dealing with unpredictable everyday events.

You had a plan. Then life happened.

## Play the game

The complete game is contained in one file:

`life-happens.html`

No installation or internet connection is required.

1. Download `life-happens.html`.
2. Open the file in Chrome, Edge, Firefox, or Safari.
3. Select **Deal the first card**.

The game works on both computers and phones.

## Objective

Complete 10 rounds and collect at least **5 Stability points** without allowing any of these resources to reach zero:

- **Money** — your available financial resources
- **Energy** — your physical and mental capacity
- **Time** — the time available for handling life
- **Stability** — the lasting security created by your decisions

You begin with:

| Resource | Starting value |
|---|---:|
| Money | 5 |
| Energy | 5 |
| Time | 5 |
| Stability | 0 |

## How to play

Each round presents a Life Happens card containing:

- An unexpected event
- Three possible responses
- A different resource tradeoff for each response

Choose the response that best supports your overall strategy. After making a choice, the game reveals what happened and updates your resources.

Select **Next card** to continue.

## Winning and losing

You win by finishing the game with:

- At least 5 Stability points
- Some Money remaining
- Some Energy remaining
- Some Time remaining

The game ends early if Money, Energy, or Time reaches zero.

Because cards are shuffled at the beginning, the event order changes whenever you play again.

## Card categories

The game currently includes events involving:

- Transportation
- Career
- Home
- Money
- Health
- Family
- Opportunities
- Pets
- Social life
- Education

## Game philosophy

There is not always one perfect response. A choice that creates stability may cost money or energy. A choice that protects your energy may delay progress.

The main challenge is deciding:

> What can I spend now without destabilizing everything else?

## Project structure

This version is intentionally simple:

```text
life-happens.html
```

The HTML file contains:

- Page structure
- Responsive CSS
- Card data
- Game rules
- Resource calculations
- Start and ending screens

There are no external libraries, images, folders, or dependencies.

## Editing the game

Open `life-happens.html` in a code editor such as Visual Studio Code.

### Add a card

Find this line inside the `<script>` section:

```javascript
const cards = [
```

Add another card object using this structure:

```javascript
{
  category: "WORK",
  icon: "💼",
  title: "Unexpected Meeting",
  story: "Your manager schedules a meeting during your focus time.",
  choices: [
    [
      "Attend immediately",
      "Protect the opportunity, but lose time.",
      { time: -1, stability: 1 },
      "The meeting was useful, but your original plan is delayed."
    ],
    [
      "Ask to reschedule",
      "Protect your focus.",
      { energy: 1 },
      "The meeting moves to a better time."
    ],
    [
      "Join while multitasking",
      "Attempt to do everything at once.",
      { energy: -2 },
      "You attended, but absorbed almost nothing."
    ]
  ]
}
```

Separate neighboring card objects with commas.

### Change a resource effect

Resource changes are written inside an effect object:

```javascript
{ money: -2, stability: 1 }
```

- A positive number adds resources.
- A negative number removes resources.
- An omitted resource stays unchanged.

### Change starting resources

Find the `start()` function and edit:

```javascript
stats = {
  money: 5,
  energy: 5,
  time: 5,
  stability: 0
};
```

### Change the visual design

The main colors are at the beginning of the `<style>` section:

```css
:root {
  --ink: #151528;
  --purple: #5b3df5;
  --cream: #f6f3ea;
  --gold: #ffca57;
  --mint: #43d7a0;
}
```

Changing these values updates the primary color palette throughout the game.

## Current version

Version 1.0 includes:

- One-player gameplay
- 10 randomized rounds
- 10 event cards
- Three choices per event
- Four-resource strategy system
- Responsive phone and computer layouts
- Win and loss screens
- Replay button
- Offline play

## Possible future additions

- Difficulty levels
- More cards and card categories
- Not Today defense cards
- Plot Twist cards
- Stability achievements
- Sound effects
- Two-player mode
- Custom player names
- Saved high scores

## Credits

Created as an original HTML, CSS, and JavaScript game concept.

**Title:** Life Happens  
**Tagline:** You had a plan.
