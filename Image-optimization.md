# 🖼️ Next.js Image Optimization Examples

This document demonstrates how to use built-in image optimization features in Next.js.

---

## ✅ Built-in Optimization

Automatically resizes, compresses, and converts images (WebP/AVIF), with lazy loading by default.

```tsx
import Image from "next/image";

<Image
  src="/images/sample.jpg"
  alt="Optimized image"
  width={600}
  height={400}
/>;
```

---

## 🖼️ Responsive Images

Serves different image sizes based on screen size.

```tsx
<Image
  src="/images/banner.jpg"
  alt="Responsive image"
  fill
  sizes="(max-width: 768px) 100vw,
         (max-width: 1200px) 50vw,
         33vw"
  style={{ objectFit: "cover" }}
/>
```

---

## 🐢 Lazy Loading

All images are lazy-loaded by default.

```tsx
<Image src="/images/lazy.jpg" alt="Lazy image" width={800} height={500} />
```

---

## 🧠 Smart Formats (WebP / AVIF)

Images are served in modern formats automatically.

```tsx
<Image src="/images/photo.jpg" alt="Smart format" width={700} height={400} />
```

---

## 🗜️ Compression

Set `quality` to reduce file size with minimal quality loss.

```tsx
<Image
  src="/images/compress.png"
  alt="Compressed image"
  width={600}
  height={300}
  quality={50}
/>
```

---

## 🚀 CDN / Remote Image Support

Optimize and load external images via Next.js proxy.

1. Add allowed domain to `next.config.js`:

```js
module.exports = {
  images: {
    domains: ["images.unsplash.com", "cdn.example.com"],
  },
};
```

2. Use the remote image:

```tsx
<Image
  src="https://images.unsplash.com/photo-1682332413251-abc123"
  alt="Remote image"
  width={800}
  height={500}
/>
```

---

## 🧾 Notes

- `Image` must have known `width` and `height`, or use `fill` with CSS control.
- Uses browser capabilities to serve smallest & best format automatically.
- Great for performance, especially with large media content.
