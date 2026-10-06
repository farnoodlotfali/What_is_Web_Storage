# What is Web Storage

A concise guide to the **Web Storage API**, covering what it is, the two mechanisms it provides for storing data, how to use `localStorage` and `sessionStorage`, and how they compare to cookies.

## 📄 Contents

This guide covers:

- What Web Storage is
- Local Storage vs Session Storage
- Key concepts:
  - **Key / Value**
  - **localStorage**
  - **sessionStorage**
  - **Storage Object**
- How to save, read, remove, and clear data with `localStorage`
- How to save, read, and clear data with `sessionStorage`
- Web Storage vs Cookies
- Key takeaways

## 🗄️ What is Web Storage?

Web storage is an API that provides a mechanism by which browsers can store key/value pairs locally within the user's browser, in a much more intuitive fashion than using cookies.

The web storage provides two mechanisms for storing data on the client:

1. **Local storage** — stores data for the current origin with no expiration date.
2. **Session storage** — stores data for one session, and the data is lost when the browser tab is closed.

## 💡 Local Storage vs Session Storage

| | Local Storage | Session Storage |
| --- | --- | --- |
| **Expiration** | No expiration date | Cleared on tab close |
| **Scope** | Shared across all tabs of the same origin | Per tab only |
| **Persistence** | Persists after the browser is closed | Lives only for that tab's session |

## 💡 Web Storage Example

**1. Save, read, remove, and clear data with `localStorage`:**

```javascript
// Save data
localStorage.setItem("username", "farnood");

// Read data
const user = localStorage.getItem("username");
console.log(user); // "farnood"

// Remove one item
localStorage.removeItem("username");

// Remove everything
localStorage.clear();

// Still there after refresh / restart
// until explicitly removed
```

**2. Save, read, and clear data with `sessionStorage`:**

```javascript
// Save data for this tab only
sessionStorage.setItem("step", "2");

// Read data
const step = sessionStorage.getItem("step");
console.log(step); // "2"

// Opening a new tab to the same site
// does NOT share this data

// Closing this tab clears it
sessionStorage.removeItem("step");
sessionStorage.clear();
```

> `localStorage` data survives page refreshes and even closing the browser, while `sessionStorage` is cleared as soon as that tab is closed.

## 📚 Web Storage vs Cookies

| Feature | Cookies | Web Storage |
| --- | --- | --- |
| **Storage size** | About 4 KB | 5 MB or more |
| **Sent to server** | Yes, with every request | No, stays in the browser |
| **Expiration** | Set manually | localStorage: none / sessionStorage: tab close |
| **API style** | String-based, manual parsing | Simple `setItem` / `getItem` |
| **Access** | Client and server | Client (browser) only |

Use cookies when the server needs the data too. Use Web Storage for browser-only data.

## 🧩 Key Concepts

| Concept | Description |
| --- | --- |
| **Key / Value** | Data is stored as simple string pairs, like a key and its value. |
| **localStorage** | Persists with no expiration date, until removed. |
| **sessionStorage** | Lives only for the current tab's session. |
| **Storage Object** | Each origin gets its own separate storage area. |

## ✅ Key Takeaways

1. **Browser-based key/value storage**: Web Storage stores key/value pairs locally within the user's browser.
2. **More intuitive than cookies**: simple `setItem` / `getItem` methods, with no manual parsing needed.
3. **localStorage**: stores data for the current origin with no expiration date.
4. **sessionStorage**: stores data for one session; lost when the browser tab is closed.

## 📥 PDF

The complete guide is available in the PDFs below:

- **[What is Web Storage (English).pdf](./What_is_Web_Storage.pdf)**
- **[What is Web Storage (Persian).pdf](./What_is_Web_Storage_FA.pdf)**
