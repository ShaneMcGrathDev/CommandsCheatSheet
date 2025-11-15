## Example #4 — Typed Array Props + Mapping (Markdown-Friendly)

This example demonstrates:

A Server Component preparing an array of typed data

A Client Component receiving the array as props

Mapping over the array to render multiple items

Adding simple state interactivity to each child

////////////////////////////////////////////////////////////////////////////

// Example #4 Server Component
// - Prepares typed array data
// - Passes array to Client Component

import Example4List from "./Example4List";

// Define a TypeScript type for items
export interface Task {
  id: number;
  title: string;
  done: boolean;
}

export default function Example4Page() {
  // Server-side data
  const tasks: Task[] = [
    { id: 1, title: "Learn Next.js", done: false },
    { id: 2, title: "Learn React Hooks", done: true },
    { id: 3, title: "Practice TypeScript", done: false },
  ];

  return <Example4List tasks={tasks} />;
}

////////////////////////////////////////////////////////////////////////////


// Example #4 Client Component
// - "use client" enables hooks
// - Receives typed array props
// - Maps over array to render items
// - useState for simple interactivity

"use client";

import { useState } from "react";
import type { Task } from "./page";

interface Example4ListProps {
  tasks: Task[];
}

export default function Example4List({ tasks }: Example4ListProps) {
  // Keep track of completed status locally
  const [completedIds, setCompletedIds] = useState<number[]>(
    tasks.filter(t => t.done).map(t => t.id)
  );

  const toggleTask = (id: number) => {
    setCompletedIds(prev =>
      prev.includes(id) ? prev.filter(i => i !== id) : [...prev, id]
    );
  };

  return (
    <ul>
      {tasks.map(task => (
        <li key={task.id}>
          <span
            style={{
              textDecoration: completedIds.includes(task.id)
                ? "line-through"
                : "none",
            }}
          >
            {task.title}
          </span>
          <button onClick={() => toggleTask(task.id)}>
            {completedIds.includes(task.id) ? "Undo" : "Complete"}
          </button>
        </li>
      ))}
    </ul>
  );
}
