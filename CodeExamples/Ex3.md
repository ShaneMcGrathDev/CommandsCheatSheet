## Example #3 — Basic Props Passing + React.FC (Markdown-Friendly)

This example demonstrates:

How to pass a child component as a prop to a parent component

Using typed props with TypeScript

Using React.FC type syntax

Using useState and useEffect in the child

////////////////////////////////////////////////////////////////////////////

// Example #3 Parent Component
// - Server Component (default in Next.js App Router)
// - Passing a child component as a prop
// - Uses typed props with React.FC

import Example3Child from "./Example3Child";

// Define props for parent
interface Example3ParentProps {
  title: string;
  ChildComponent: React.FC<{ message: string }>;
}

export default function Example3Parent() {
  const title = "Parent Component Title";

  return (
    <div>
      <h1>{title}</h1>

      {/* Pass child component as prop with message */}
      <Example3Child message="Hello from the Parent!" />
    </div>
  );
}

////////////////////////////////////////////////////////////////////////////

// Example #3 Child Component
// - "use client" enables hooks
// - React.FC syntax used
// - Simple useState + useEffect
// - Typed props

"use client";

import { useState, useEffect } from "react";

interface Example3ChildProps {
  message: string;
}

const Example3Child: React.FC<Example3ChildProps> = ({ message }) => {
  const [displayMessage, setDisplayMessage] = useState<string>("");

  // Set the message once after mount
  useEffect(() => {
    setDisplayMessage(message);
  }, [message]);

  return <p>{displayMessage}</p>;
};

export default Example3Child;
