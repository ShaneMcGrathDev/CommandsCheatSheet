
## Example #1 — Smallest Server + Client Component Setup (Markdown-Friendly)

////////////////////////////////////////////////////////////////////////////

// Example #1: Smallest Server → Client flow
// - Server Component by default in Next.js App Router
// - ES6 arrow function
// - Passing typed props to a Client Component

import ExampleClient from "./ExampleClient";

export default function ExamplePage() {
  const message: string = "Hello from the Server Component!";

  return <ExampleClient message={message} />;
}

////////////////////////////////////////////////////////////////////////////

// Example #1 (client): Smallest interactive Client Component
// - "use client" enables interactivity
// - TypeScript interface for props
// - ES7 optional chaining used in message?.length

"use client";

interface ExampleClientProps {
  message: string;
}

export default function ExampleClient({ message }: ExampleClientProps) {
  return (
    <div>
      <h1>{message}</h1>
      <p>Message length (via ES7 optional chaining): {message?.length}</p>
    </div>
  );
}
