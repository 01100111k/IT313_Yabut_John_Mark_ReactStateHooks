# Lab Timer & Practice Tracker

## Problem

The Lab Timer & Practice Tracker is a small React Native application designed to help students during laboratory sessions. It allows students to keep track of how many practice problems they have solved and how long they have been working.

The application demonstrates the use of React state, hooks, event handling, conditional rendering, lifting state up, and a custom hook.

## Approach

The application is built using React Native and Expo.

The `LabScreen` component acts as the parent component and manages the shared state of the application.

The application uses:

- `useState` to store the number of solved problems and the timer running state.
- `useEffect` inside the custom `useStopwatch` hook to update the timer every second.
- A cleanup function with `clearInterval()` to stop the timer when it is paused or when the component is unmounted.
- Conditional rendering to display `Great job!` when the solved count reaches 5 and to display either `Running...` or `Paused`.
- Event handling through `onPress` functions for the Solve +1, Reset, Start, and Stop buttons.
- Lifting state up by keeping the shared state in `LabScreen` and passing the required values and callback functions to `PracticeTracker` and `Stopwatch`.
- A custom hook named `useStopwatch` to handle the stopwatch functionality.

## Main Components

### LabScreen

`LabScreen` is the main parent component. It manages:

- The solved problem count.
- Whether the stopwatch is running.
- The stopwatch seconds.
- Functions for solving, resetting, starting, and stopping.

### PracticeTracker

`PracticeTracker` displays the number of solved problems and provides the Solve +1 and Reset buttons.

When the solved count reaches 5, it displays:

> Great job!

### Stopwatch

`Stopwatch` displays the elapsed time and the current timer status.

It displays:

- `Running...` when the timer is running.
- `Paused` when the timer is stopped.

### useStopwatch

`useStopwatch` is a custom React hook that manages the stopwatch seconds.

It uses `useEffect` and `setInterval()` to increase the timer every 1000 milliseconds while the stopwatch is running.

The interval is cleared using `clearInterval()` when the timer stops or the component is unmounted.

## Project Structure

```text
LabTimer_Sacuan
│
├── components
│   ├── PracticeTracker.js
│   └── Stopwatch.js
│
├── hooks
│   └── useStopwatch.js
│
├── src
│   ├── LabScreen.js
│   └── app
│       ├── _layout.tsx
│       ├── explore.tsx
│       └── index.js
│
├── assets
├── package.json
└── README.md