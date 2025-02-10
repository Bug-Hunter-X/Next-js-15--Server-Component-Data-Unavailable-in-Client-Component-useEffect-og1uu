# Next.js 15 Server Component Data Race Condition in useEffect

This repository demonstrates a common issue in Next.js 15 where data fetched in a server component is not readily available within a `useEffect` hook in a client component.  This leads to a race condition, causing unexpected behavior or errors.

## Problem

The client component attempts to access data from a server component before it's been fetched. This often manifests as undefined values or rendering errors. 

## Solution

The solution uses the `use` hook to handle the asynchronous data fetching from the server component, ensuring the data is ready before the client component tries to use it.

## Reproduction

1. Clone the repository.
2. Run `npm install`.
3. Run `npm run dev`.
4. Observe the console and initial render behavior in the browser. Note the errors and race conditions when accessing data prematurely.

## Setup

This example uses a simple API call to simulate a data fetching process.  The `bug.js` file demonstrates the problematic code, and `bugSolution.js` demonstrates the improved solution.