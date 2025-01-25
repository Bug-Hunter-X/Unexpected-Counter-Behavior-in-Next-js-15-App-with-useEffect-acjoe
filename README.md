# Unexpected Counter Behavior in Next.js 15 App

This repository demonstrates an unexpected behavior in a Next.js 15 application when using `useEffect` hook with `setInterval` for updating a counter.  The counter continues to increment even after navigating away from the page and back. This issue arises from the fact that the cleanup function in the `useEffect` hook (which should clear the interval) may not be correctly executed when the component unmounts unexpectedly when switching pages.

## Steps to Reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run `npm run dev`.
4. Navigate to the `/about` page.
5. Observe the counter incrementing every second.
6. Navigate to the `/` page.
7. Navigate back to `/about`.
8. The counter will continue from where it left off, demonstrating unexpected behavior. 

## Solution

The solution involves ensuring that the `useEffect` cleanup function reliably clears the interval, regardless of the navigation method.
