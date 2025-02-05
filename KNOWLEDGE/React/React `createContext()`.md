
# What is `createContext()` in React ?

`createContext()` in React is a function that creates a **Context object**, which allows data to be passed deeply through the component tree without needing to pass props manually at every level. It is part of the **React Context API**, which is used for state management and sharing global data like themes, authentication, and user preferences.


### **Syntax**

```jsx
const MyContext = React.createContext(defaultValue);
```


- `defaultValue` (optional): The default value of the context when no `Provider` is present.

### **Usage of createContext()**

#### 1️⃣ **Create Context**


```jsx

import React, { createContext } from "react";  const UserContext = createContext(null); // Create a context with default value null  export default UserContext;

```

#### 2️⃣ **Provide Context (Using Provider)**

Wrap your components inside a `Provider` to supply data.


```jsx

import React, { useState } from "react"; import UserContext from "./UserContext";  const UserProvider = ({ children }) => {   const [user, setUser] = useState({ name: "Souvik", age: 22 });    return (     <UserContext.Provider value={{ user, setUser }}>       {children}     </UserContext.Provider>   ); };  export default UserProvider;
```
#### 3️⃣ **Consume Context (Using useContext Hook)**

jsx

CopyEdit

`import React, { useContext } from "react"; import UserContext from "./UserContext";  const UserProfile = () => {   const { user } = useContext(UserContext);    return (     <div>       <h2>User Name: {user.name}</h2>       <p>Age: {user.age}</p>     </div>   ); };  export default UserProfile;`

#### 4️⃣ **Wrap Components with Provider**

jsx

CopyEdit

`import React from "react"; import ReactDOM from "react-dom"; import UserProvider from "./UserProvider"; import UserProfile from "./UserProfile";  const App = () => (   <UserProvider>     <UserProfile />   </UserProvider> );  ReactDOM.render(<App />, document.getElementById("root"));`

### **When to Use `createContext()`?**

- When passing props through multiple levels becomes cumbersome (prop drilling).
- For global state management (e.g., authentication, themes, language settings).
- When Redux or Zustand feels like overkill.

### **Alternative: Using Context with `useReducer()`**

Instead of `useState()`, you can use `useReducer()` for more complex state logic.

Would you like an example of that too? 🚀