# 🚀 Advantages of Using Next.js Over React.js

Next.js is a production-grade framework built on top of React.js. It adds features like routing, SSR, SSG, and API routes out-of-the-box—making web apps faster, more SEO-friendly, and easier to build.

---

## ⚡ Why Choose Next.js?
 
### ✅ Core Benefits Over React

- **🔍 SEO-Friendly (SSR)**  
  Server-side rendering helps search engines index your pages more effectively.

- **⚙️ Static Site Generation (SSG)**  
  Pre-renders pages at build time—ideal for performance and scalability.

- **♻️ Incremental Static Regeneration (ISR)**  
  Rebuild individual pages in the background, even after deployment.

- **📁 File-Based Routing**  
  Just add a file in the `pages/` directory—it becomes a route.

- **🧩 Automatic Code Splitting**  
  Loads only what’s needed per page for better performance.

---

## 🛠️ Additional Features

- **📦 Built-in API Routes**  
  Create serverless functions inside the `pages/api/` directory.

- **🖼️ Image Optimization**  
  Resizes, compresses, and lazy-loads images automatically (WebP, AVIF, etc.).

- **🎨 CSS/Sass Support**  
  Supports CSS Modules and Sass with zero config.

- **🚀 Fast Performance**  
  Smart bundling, caching, and edge-ready deployment via [Vercel](https://vercel.com/).

---

## 🧠 Rendering Modes in Next.js

```ts
// SSR - Server-Side Rendering
export async function getServerSideProps() {
  const data = await fetchData();
  return { props: { data } };
}

// SSG - Static Site Generation
export async function getStaticProps() {
  const data = await fetchData();
  return { props: { data } };
}

// ISR - Incremental Static Regeneration
export async function getStaticProps() {
  const data = await fetchData();
  return {
    props: { data },
    revalidate: 60, // Regenerate every 60 seconds
  };
}
