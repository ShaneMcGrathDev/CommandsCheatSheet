# JavaScript Quick Reference for Next.js/React

Below is a concise reference of common ES6 and ES7 syntax used frequently in modern Next.js/React codebases. Each item includes a short summary and a simple code example.

---

## **ES6 Syntax Examples**

### **1. Arrow Functions**

Shorter function syntax.

```js
const greet = (name) => `Hello ${name}`;
```

### **2. Template Literals**

String interpolation with backticks.

```js
const message = `Logged in as ${user.name}`;
```

### **3. Destructuring Objects**

Extract values from objects.

```js
const { title, body } = props;
```

### **4. Destructuring Arrays**

Extract values from arrays.

```js
const [count, setCount] = useState(0);
```

### **5. Default Parameters**

Set fallback values.

```js
const getTotal = (price = 0) => price * 1.1;
```

### **6. Spread Operator**

Copy or expand arrays/objects.

```js
const newState = { ...state, loggedIn: true };
```

### **7. Rest Parameters**

Capture remaining arguments.

```js
const logAll = (...items) => console.log(items);
```

### **8. Import / Export**

Module organization.

```js
import Header from './Header';
export const PI = 3.14;
```

### **9. Classes**

Blueprints for objects.

```js
class User {
  constructor(name) {
    this.name = name;
  }
}
```

### **10. Enhanced Object Literals**

Shorter object notation.

```js
const name = 'Shane';
const user = { name, active: true };
```

---

## **ES7 Syntax Examples**

### **1. Array.includes()**

Check array membership.

```js
const exists = roles.includes('admin');
```

### **2. Exponentiation Operator**

Shorter math exponent syntax.

```js
const squared = 5 ** 2;
```

### **3. async/await**

Cleaner async code.

```js
const data = await fetch('/api/user').then(r => r.json());
```

### **4. Object.values()**

Return object values as array.

```js
const values = Object.values(settings);
```

### **5. Object.entries()**

Return key/value pairs.

```js
Object.entries(user).map(([k, v]) => console.log(k, v));
```

### **6. Trailing Commas**

Allow cleaner diffs.

```js
const nums = [1, 2, 3,];
```

### **7. Async Function in React useEffect()**

Run async logic in effects.

```js
useEffect(() => {
  const load = async () => setData(await fetch('/api/data').then(r => r.json()));
  load();
}, []);
```

### **8. Promise.finally()**

Run cleanup after promise resolves.

```js
fetch('/api').finally(() => setLoading(false));
```

### **9. String.padStart() / padEnd()**

Format strings.

```js
const padded = id.padStart(5, '0');
```

### **10. Nullish Coalescing (??)**

Default only for null/undefined.

```js
const title = user.title ?? 'Guest';
```

---

## **ES8 Syntax Examples**

### **1. async/await Improvements**

Async handling with try/catch.

```js
try {
  const res = await fetch('/api/data');
} catch (err) {
  console.error(err);
}
```

### **2. Object.getOwnPropertyDescriptors()**

Clone objects with descriptors.

```js
const clone = Object.defineProperties({}, Object.getOwnPropertyDescriptors(obj));
```

### **3. String padding (ES8)**

Pad strings to a fixed length.

```js
'5'.padEnd(3, '0');
```

### **4. Trailing Commas in Function Params**

Allows trailing commas.

```js
const f = (a, b,) => a + b;
```

### **5. Shared Memory + Atomics**

Low-level parallelism.

```js
const shared = new SharedArrayBuffer(1024);
```

---

## **ES9 Syntax Examples**

### **1. Rest/Spread in Objects**

Expanding and collecting object properties.

```js
const { id, ...details } = user;
```

### **2. Asynchronous Iteration**

Use for-await loops.

```js
for await (const item of fetchStream()) {
  console.log(item);
}
```

### **3. Promise.prototype.finally()**

Cleanup after operations.

```js
apiCall().finally(() => setLoading(false));
```

---

# **React / Next.js Patterns**

## **React Components**

### **1. Functional Component**

Basic reusable component.

```jsx
export default function Header() {
  return <h1>Hello</h1>;
}
```

### **2. Props Usage**

Pass and use props.

```jsx
function Greeting({ name }) {
  return <p>Hello {name}</p>;
}
```

### **3. Conditional Rendering**

Show UI based on state.

```jsx
{isLoggedIn ? <Dashboard /> : <Login />}
```

### **4. List Rendering**

Render lists dynamically.

```jsx
items.map(i => <li key={i.id}>{i.label}</li>);
```

### **5. Fragment Syntax**

Render without extra DOM.

```jsx
<>
  <Nav />
  <Content />
</>
```

---

## **React Hooks**

### **1. useState**

Declare component state.

```jsx
const [count, setCount] = useState(0);
```

### **2. useEffect**

Run code on render or dependency changes.

```jsx
useEffect(() => {
  console.log('mounted');
}, []);
```

### **3. useRef**

Access DOM elements.

```jsx
const inputRef = useRef();
```

### **4. useContext**

Read from React context.

```jsx
const value = useContext(AppContext);
```

### **5. useReducer**

More advanced state handling.

```jsx
const [state, dispatch] = useReducer(reducer, initialState);
```

---

## **Next.js Specific Examples**

### **1. Page Component (App Router)**

Default export defines the route.

```jsx
export default function Page() { return <div>Home</div>; }
```

### **2. Server Component Fetching**

Automatically server-side.

```jsx
export default async function Page() {
  const data = await fetch(process.env.API_URL).then(r => r.json());
  return <pre>{JSON.stringify(data)}</pre>;
}
```

### **3. Client Component**

Enable React hooks.

```jsx
'use client';

export default function Counter() {
  const [n, setN] = useState(0);
  return <button onClick={() => setN(n+1)}>{n}</button>;
}
```

### **4. API Route (App Router)**

Server API endpoint.

```js
export async function GET() {
  return Response.json({ status: 'ok' });
}
```

### **5. useRouter Navigation**

Client-side route changes.

```jsx
'use client';
import { useRouter } from 'next/navigation';

const router = useRouter();
router.push('/dashboard');
```

---

# **TypeScript + React/Next.js Examples**

### **1. Typed Props**

```tsx
type Props = { title: string };

export function Header({ title }: Props) {
  return <h1>{title}</h1>;
}
```

### **2. Typed useState**

```tsx
const [count, setCount] = useState<number>(0);
```

### **3. Interface for Objects**

```ts
interface User { id: number; name: string; }
```

### **4. Component with Children**

```tsx
type Props = { children: React.ReactNode };
```

### **5. API Response Types**

```ts
async function getUser(): Promise<User> {
  return fetch('/api/user').then(r => r.json());
}
```
