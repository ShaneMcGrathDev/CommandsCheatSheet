## Example #5 — ES6 Object Destructuring + Spread + Nested Components (Markdown-Friendly)

This example demonstrates:

Server Component preparing typed objects

Client Component receiving array of objects

Using destructuring and spread operators for updates

Nested child component (TaskItem)

React state and simple interactivity

////////////////////////////////////////////////////////////////////////////

// Example #5 Server Component
// - Prepares typed array of objects
// - Passes data to client component

import Example5List from "./Example5List";

export interface Task {
  id: number;
  title: string;
  done: boolean;
  description?: string;
}

export default function Example5Page() {
  const tasks: Task[] = [
    { id: 1, title: "Learn Next.js", done: false, description: "App Router basics" },
    { id: 2, title: "Learn TypeScript", done: true, description: "Props + types" },
    { id: 3, title: "Practice ES6", done: false, description: "Destructuring + spread" },
  ];

  return <Example5List tasks={tasks} />;
}



////////////////////////////////////////////////////////////////////////////


// Example #5 Client Component
// - "use client" enables hooks
// - Handles state and interactivity
// - Uses ES6 destructuring and spread operators
// - Nested TaskItem component

"use client";

import { useState } from "react";
import type { Task } from "./page";

interface Example5ListProps {
  tasks: Task[];
}

export default function Example5List({ tasks }: Example5ListProps) {
  // Local state for tasks
  const [taskList, setTaskList] = useState<Task[]>(tasks);

  const toggleTask = (id: number) => {
    // Update task done state immutably using map + spread operator
    const updatedTasks = taskList.map(task =>
      task.id === id ? { ...task, done: !task.done } : task
    );
    setTaskList(updatedTasks);
  };

  return (
    <ul>
      {taskList.map(task => (
        <TaskItem key={task.id} task={task} toggleTask={toggleTask} />
      ))}
    </ul>
  );
}

// Nested child component
interface TaskItemProps {
  task: Task;
  toggleTask: (id: number) => void;
}

const TaskItem: React.FC<TaskItemProps> = ({ task, toggleTask }) => {
  // ES6 object destructuring
  const { id, title, done, description } = task;

  return (
    <li style={{ marginBottom: "8px" }}>
      <div>
        <strong style={{ textDecoration: done ? "line-through" : "none" }}>
          {title}
        </strong>{" "}
        <em>({description})</em>
      </div>
      <button onClick={() => toggleTask(id)}>
        {done ? "Undo" : "Complete"}
      </button>
    </li>
  );
};
