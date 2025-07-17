## 🧠 What is SSR (Server-Side Rendering)?

SSR means the HTML is generated on the server at request time — every time someone visits the page.

### 🔄 How it works:

1. User visits a page

2. Server fetches data

3. Server builds the page’s HTML

4. Sends it to the user’s browser

### ✅ When to use SSR:

Use SSR when your page:

- Needs up-to-date or real-time data

- Changes frequently (e.g., prices, user dashboards)

- Is personalized per user (e.g., logged-in content)

- SEO matters (because SSR sends ready HTML to crawlers)

### 📦 Example use cases:

- E-commerce product page with real-time stock

- News article with breaking updates

- User account settings or profile

---

---

---

## 🧠 What is SSG (Static Site Generation)?

SSG means the HTML is generated at build time — not when someone visits the page. It’s built once and reused for all users.

### 🔄 How it works:

1. When you deploy your app, Next.js runs the page code

2. Fetches data at build time

3. Generates static HTML files

4. Those files are stored on the CDN and reused for every visitor

### ✅ When to use SSG:

Use SSG when your page:

- Doesn’t change often

- Can be prebuilt

- Needs fast load times

- SEO is important, but data doesn’t need to be live

### 📦 Example use cases:

- Blog posts

- Marketing pages (landing page, about)

- Documentation

- Product listings that rarely change

---

---

---

## 🧠 What is CSR (Client-Side Rendering)?

CSR means the page is rendered entirely in the browser using JavaScript. The HTML sent from the server is mostly empty, and the content is fetched after the page loads.

### 🔄 How it works:

1. User visits the page

2. Server sends a minimal HTML + JavaScript bundle

3. JavaScript runs in the browser and fetches the data

4. The page is built on the client (user's device)

### ✅ When to use SSG:

Use CSR when your page:

- The page is not critical for SEO

- Data is user-specific or private

- You want a highly interactive app

- Content depends on client-side state (auth, input)

### 📦 Example use cases:

- Dashboards after login

- Admin panels

- Shopping carts

- Product listings that rarely change

### ⚠ Downsides:

- Slower First Load: User sees blank screen until JavaScript finishes

- Bad SEO: Crawlers may not see the content

- Heavy JS: More JavaScript is sent to the browser


---

---

---

## 🧠 What is ISR (Incremental Static Regeneration)?

ISR is an enhancement to SSG. It allows you to:

- Serve fast static pages

- Regenerate them in the background at intervals

It gives the speed of SSG with flexibility to update content.

### 🔄 How it works:

1. Page is built once at build time (like SSG)

2. Next.js stores static HTML in the CDN

3. When a user visits the page after revalidate time:

    - Next.js serves old page

    - Then regenerates the page in the background

4. Future requests get the updated page

### ✅ When to use ISR:

Use ISR when:

- Content changes occasionally

- You want speed + up-to-date data

- Full SSR is too slow or expensive

### 📦 Example use cases:

- Blogs with occasional updates

- Product pages with infrequent stock/price changes

- Marketing pages that change every few hours

