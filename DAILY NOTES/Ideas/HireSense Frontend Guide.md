

[ChatGPT Convo](https://chatgpt.com/share/67e9010e-34ac-800a-98de-088c3f2b9eba)


```
import axios, { AxiosInstance, AxiosRequestConfig, AxiosResponse } from 'axios';

const API_BASE_URL = process.env.NEXT_PUBLIC_API_BASE_URL || 'http://localhost:5000';

const api: AxiosInstance = axios.create({
  baseURL: API_BASE_URL,
  timeout: 10000,
  headers: {
    'Content-Type': 'application/json',
  },
});

// Request Interceptor
api.interceptors.request.use(
  (config: AxiosRequestConfig) => {
    const token = localStorage.getItem('token');
    if (token) {
      config.headers = {
        ...config.headers,
        Authorization: `Bearer ${token}`,
      };
    }
    return config;
  },
  (error) => Promise.reject(error)
);

// Response Interceptor
api.interceptors.response.use(
  (response: AxiosResponse) => response,
  (error) => {
    console.error('API Error:', error.response?.data || error.message);
    return Promise.reject(error);
  }
);

// API Functions
export const get = async <T>(url: string, config?: AxiosRequestConfig): Promise<T> => {
  const response = await api.get<T>(url, config);
  return response.data;
};

export const post = async <T>(url: string, data?: any, config?: AxiosRequestConfig): Promise<T> => {
  const response = await api.post<T>(url, data, config);
  return response.data;
};

export const put = async <T>(url: string, data?: any, config?: AxiosRequestConfig): Promise<T> => {
  const response = await api.put<T>(url, data, config);
  return response.data;
};

export const del = async <T>(url: string, config?: AxiosRequestConfig): Promise<T> => {
  const response = await api.delete<T>(url, config);
  return response.data;
};

export default api;

```



This `api.ts` file:

- Uses Axios for HTTP requests.
    
- Configures a base URL from environment variables.
    
- Sets up request and response interceptors for authentication and error handling.
    
- Exposes generic `get`, `post`, `put`, and `del` functions for API calls.
    

Let me know if you need additional features like query parameters or specific API endpoints! 🚀

##### You said:

how would be the file structure for nextjs app for the apis

###### ChatGPT said:

For a clean and scalable **Next.js** app with a structured API service layer, you can follow this directory structure:

```bash
/my-nextjs-app
│── /src
│   │── /api                # API service layer
│   │   │── api.ts          # Axios instance & request handlers
│   │   │── auth.ts         # Authentication API functions
│   │   │── user.ts         # User-related API functions
│   │── /components         # UI components
│   │── /pages              # Next.js pages
│   │── /hooks              # Custom hooks (useAuth, useUser, etc.)
│   │── /utils              # Helper functions
│── /public                 # Static assets
│── .env.local              # Environment variables
│── next.config.js          # Next.js configuration
│── package.json            # Dependencies
│── tsconfig.json           # TypeScript config


```



### **API Service Layer (`/src/api/`)**

- **`api.ts`** → Sets up Axios instance & interceptors.
    
- **`auth.ts`** → Handles authentication (login, register, logout).
    
- **`user.ts`** → Manages user-related API calls (profile, settings).
    

### **Example `auth.ts` (Authentication API)**

```typescript

import { post } from './api';

export const login = async (email: string, password: string) => {
  return post('/auth/login', { email, password });
};

export const register = async (data: { email: string; password: string; name: string }) => {
  return post('/auth/register', data);
};

export const logout = async () => {
  return post('/auth/logout');
};

```

This keeps your API logic modular and easy to maintain. Let me know if you need modifications! 🚀

##### You said:

what is API service layer and request intrcepter

###### ChatGPT said:

### **1. What is an API Service Layer?**

An **API service layer** in a Next.js project is a centralized module that handles all API requests. Instead of making API calls directly from components, the API service layer abstracts request logic, ensuring **code reusability, maintainability, and cleaner components**.

#### **Benefits of an API Service Layer:**

✅ **Separation of Concerns** → Keeps API logic separate from UI logic.  
✅ **Reusability** → Centralized functions can be reused across multiple components.  
✅ **Error Handling** → Consistently handle API errors in one place.  
✅ **Authentication & Authorization** → Easily add tokens to requests.

---

### **2. What is a Request Interceptor?**

A **request interceptor** is a function that modifies outgoing HTTP requests **before they are sent to the server**. In Axios, it is useful for adding headers, tokens, or modifying request data.

#### **Example: Adding an Authentication Token**

```typescript
import axios from 'axios';

const api = axios.create({
  baseURL: process.env.NEXT_PUBLIC_API_BASE_URL || 'http://localhost:5000',
  timeout: 10000,
  headers: { 'Content-Type': 'application/json' },
});

// Request Interceptor - Add Auth Token
api.interceptors.request.use(
  (config) => {
    const token = localStorage.getItem('token');
    if (token) {
      config.headers.Authorization = `Bearer ${token}`;
    }
    return config;
  },
  (error) => Promise.reject(error)
);

export default api;

```

#### **How It Works:**

1️⃣ Before sending any request, Axios checks if a **token** is stored in `localStorage`.  
2️⃣ If the token exists, it is **added to the request headers** as `Authorization: Bearer <token>`.  
3️⃣ This ensures **every API request includes authentication**, without manually adding it to each request.

---

### **3. Response Interceptor (Bonus)**

A **response interceptor** processes API responses **before they reach the application**, making it useful for **error handling** or **auto-logout** on unauthorized responses.

#### **Example: Handling API Errors**

```typescript

api.interceptors.response.use(
  (response) => response, // Pass successful responses
  (error) => {
    if (error.response?.status === 401) {
      console.error('Unauthorized! Logging out...');
      localStorage.removeItem('token');
      window.location.href = '/login'; // Redirect to login
    }
    return Promise.reject(error);
  }
);

```
---

### **Conclusion**

- **API Service Layer** organizes API calls in a structured way.
    
- **Request Interceptors** modify outgoing requests (e.g., adding auth tokens).
    
- **Response Interceptors** handle responses (e.g., auto-logout on `401`).
    
