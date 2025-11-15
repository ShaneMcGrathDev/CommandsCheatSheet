
## Example #2 — Server Data Fetching + Client State (Markdown-Friendly)

This example demonstrates a common real-world pattern:

Server Component performs data fetching using fetch()

Typed data is prepared server-side

Client Component receives the data as props

The Client Component uses useState and useEffect to interact with it

A perfect next step after Example #1.

////////////////////////////////////////////////////////////////////////////

// Example #2 Server Component: Async fetch + typed data model
// - Server Component by default
// - Fetching data inside an async component
// - Passing typed props to a Client Component

import Example2Client from "./Example2Client";

// Define a TypeScript type for API data
export interface TodoItem {
  id: number;
  title: string;
  completed: boolean;
}

export default async function Example2Page() {
  // Fetch mock data from a public endpoint (server-side)
  const res = await fetch("https://jsonplaceholder.typicode.com/todos/1");
  const todo: TodoItem = await res.json();

  return <Example2Client todo={todo} />;
}

////////////////////////////////////////////////////////////////////////////

// Example #2 Client Component: Local state + props
// - "use client" enables interactivity (hooks)
// - useState + useEffect
// - Receives typed props from the server

"use client";

import { useState, useEffect } from "react";
import type { TodoItem } from "./page";

interface Example2ClientProps {
  todo: TodoItem;
}

export default function Example2Client({ todo }: Example2ClientProps) {
  const [isCompleted, setIsCompleted] = useState<boolean>(todo.completed);

  // A simple effect that logs when the completion state updates
  useEffect(() => {
    console.log("Todo completion state updated:", isCompleted);
  }, [isCompleted]);

  return (
    <div>
      <h1>Todo Item</h1>

      <p>ID: {todo.id}</p>
      <p>Title: {todo.title}</p>

      <button onClick={() => setIsCompleted(!isCompleted)}>
        Mark as {isCompleted ? "Incomplete" : "Completed"}
      </button>

      <p>Status: {isCompleted ? "Completed" : "Incomplete"}</p>
    </div>
  );
}
