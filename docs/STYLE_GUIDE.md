# Unmuted Theme Style Guide

## Overview
This style guide defines the coding standards, best practices, and conventions for the Unmuted Shopify theme (Dawn-based customization for Everyday AI).

---

## Table of Contents
1. [File Organization](#file-organization)
2. [Liquid Templates](#liquid-templates)
3. [CSS/Styling](#cssstyling)
4. [JavaScript](#javascript)
5. [Naming Conventions](#naming-conventions)
6. [Git Workflow](#git-workflow)
7. [Accessibility](#accessibility)

---

## File Organization

### Directory Structure
```
unmuted/
├── assets/          # CSS, JS, images, fonts
├── config/          # Theme settings (settings_schema.json, settings_data.json)
├── layout/          # Layout templates (theme.liquid, etc.)
├── locales/         # Translation files
├── sections/        # Reusable sections
├── snippets/        # Reusable code snippets
└── templates/       # Page templates
```

### File Naming
- **Liquid files**: Use kebab-case (e.g., `product-card.liquid`, `hero-banner.liquid`)
- **CSS files**: Use kebab-case (e.g., `base.css`, `component-card.css`)
- **JavaScript files**: Use kebab-case (e.g., `cart-drawer.js`, `product-form.js`)
- **Images**: Use descriptive kebab-case (e.g., `logo-white.svg`, `hero-background.jpg`)

---

## Liquid Templates

### General Principles
- Keep logic minimal in templates
- Use snippets for reusable components
- Comment complex logic
- Avoid deep nesting (max 3 levels)

### Syntax Standards

#### Variables
```liquid
{%- liquid
  assign product_title = product.title
  assign is_available = product.available
-%}
```

#### Conditionals
```liquid
{%- if product.available -%}
  <button type="submit">Add to Cart</button>
{%- else -%}
  <button disabled>Sold Out</button>
{%- endif -%}
```

#### Loops
```liquid
{%- for product in collection.products limit: 4 -%}
  {% render 'product-card', product: product %}
{%- endfor -%}
```

### Whitespace Control
- Use `{%-` and `-%}` to control whitespace
- Keep output clean and minimal

### Comments
```liquid
{%- comment -%}
  Product card component
  Displays product image, title, price, and add-to-cart button
{%- endcomment -%}
```

---

## CSS/Styling

### Methodology
- Follow **BEM** (Block Element Modifier) naming convention
- Use CSS custom properties for theming
- Mobile-first responsive design

### BEM Examples
```css
/* Block */
.product-card { }

/* Element */
.product-card__image { }
.product-card__title { }
.product-card__price { }

/* Modifier */
.product-card--featured { }
.product-card__price--sale { }
```

### CSS Custom Properties

#### Brand Colors
```css
:root {
  /* Primary Brand Colors */
  --purple-500: #A855F7;  /* Electric Purple - Primary */
  --purple-600: #9333EA;  /* Hover state */
  --purple-700: #7E22CE;  /* Active state */
  
  --pink-500: #EC4899;    /* Hot Pink - Primary */
  --pink-600: #DB2777;    /* Hover state */
  --pink-700: #BE185D;    /* Active state */
  
  --cyan-500: #06B6D4;    /* Cyan - Primary */
  --cyan-600: #0891B2;    /* Hover state */
  --cyan-700: #0E7490;    /* Active state */
  
  /* Dark Mode Base */
  --dark-700: #334155;    /* Primary dark */
  --dark-800: #1E293B;    /* Darker */
  --dark-900: #0F172A;    /* Darkest */
  
  /* Neutrals */
  --white: #FFFFFF;
  --off-white: #FAFAFA;
  --warm-white: #FFF9F5;
  --black: #000000;
  --gray-500: #6B7280;    /* Body text */
  --gray-700: #374151;    /* Headings */
  --gray-900: #111827;    /* Darkest text */
  
  /* Typography */
  --font-body: 'Inter', sans-serif;
  --font-heading: 'Playfair Display', serif;
  
  /* Spacing */
  --spacing-unit: 8px;
}
```

#### Usage Guidelines
- **Primary CTA**: Use `--purple-500` for main call-to-action buttons
- **Secondary CTA**: Use `--pink-500` for secondary actions
- **Accents**: Use `--cyan-500` for highlights and links
- **Text**: Use `--gray-900` for headings, `--gray-700` for body text
- **Backgrounds**: Use `--dark-900` for dark sections, `--warm-white` for light sections

### Responsive Design
```css
/* Mobile first */
.container {
  padding: 1rem;
}

/* Tablet */
@media screen and (min-width: 750px) {
  .container {
    padding: 2rem;
  }
}

/* Desktop */
@media screen and (min-width: 990px) {
  .container {
    padding: 3rem;
  }
}
```

### Code Organization
1. Layout properties (display, position, float)
2. Box model (width, height, margin, padding)
3. Typography (font, line-height, text-align)
4. Visual (background, border, box-shadow)
5. Misc (cursor, overflow, z-index)

---

## JavaScript

### General Principles
- Use vanilla JavaScript (ES6+)
- Keep scripts modular
- Add comments for complex logic
- Handle errors gracefully

### Code Style
```javascript
// Use const/let, not var
const productForm = document.querySelector('.product-form');
let quantity = 1;

// Use arrow functions
const updateCart = (item) => {
  // Implementation
};

// Use template literals
const message = `Added ${quantity} items to cart`;

// Async/await for promises
async function fetchProduct(handle) {
  try {
    const response = await fetch(`/products/${handle}.js`);
    const product = await response.json();
    return product;
  } catch (error) {
    console.error('Error fetching product:', error);
  }
}
```

### Event Listeners
```javascript
// Use event delegation when possible
document.addEventListener('click', (event) => {
  if (event.target.matches('.add-to-cart')) {
    handleAddToCart(event);
  }
});
```

---

## Naming Conventions

### Classes
- **Components**: `.component-name` (e.g., `.product-card`, `.hero-banner`)
- **Utilities**: `.u-utility-name` (e.g., `.u-text-center`, `.u-hide-mobile`)
- **JavaScript hooks**: `.js-hook-name` (e.g., `.js-cart-toggle`, `.js-product-form`)

### IDs
- Use sparingly, prefer classes
- Use for unique page sections (e.g., `#main-content`, `#site-header`)

### Variables (Liquid)
```liquid
{%- assign product_title = product.title -%}
{%- assign is_on_sale = product.compare_at_price > product.price -%}
```

### Variables (JavaScript)
```javascript
// camelCase for variables and functions
const productHandle = 'example-product';
const isAvailable = true;

// PascalCase for classes
class ProductForm { }
```

---

## Git Workflow

### Branch Naming
- **Features**: `feature/description` (e.g., `feature/product-quick-view`)
- **Fixes**: `fix/description` (e.g., `fix/cart-drawer-overflow`)
- **Hotfixes**: `hotfix/description` (e.g., `hotfix/checkout-button`)

### Commit Messages
Follow conventional commits:
```
feat: Add product quick view modal
fix: Resolve cart drawer overflow on mobile
docs: Update style guide with accessibility section
style: Format CSS according to style guide
refactor: Simplify product card component
test: Add tests for cart functionality
```

### Commit Structure
```
<type>: <subject>

<body (optional)>

<footer (optional)>
```

**Types**: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`

---

## Accessibility

### General Requirements
- Semantic HTML elements
- ARIA labels where needed
- Keyboard navigation support
- Color contrast ratio ≥ 4.5:1
- Focus indicators visible

### Examples

#### Semantic HTML
```html
<header>
  <nav aria-label="Main navigation">
    <ul>
      <li><a href="/">Home</a></li>
    </ul>
  </nav>
</header>

<main id="main-content">
  <article>
    <h1>Product Title</h1>
  </article>
</main>
```

#### ARIA Labels
```html
<button aria-label="Add to cart" class="icon-button">
  <svg aria-hidden="true">...</svg>
</button>

<div role="status" aria-live="polite" aria-atomic="true">
  Item added to cart
</div>
```

#### Skip Links
```html
<a href="#main-content" class="skip-to-content">
  Skip to content
</a>
```

#### Form Labels
```html
<label for="email">Email address</label>
<input type="email" id="email" name="email" required>
```

---

## Performance

### Best Practices
- Lazy load images below the fold
- Minify CSS and JavaScript
- Use responsive images with `srcset`
- Defer non-critical JavaScript
- Optimize image file sizes

### Image Optimization
```liquid
{%- liquid
  assign image_sizes = '375px, 750px, 1100px, 1500px'
  assign image_widths = '375, 750, 1100, 1500, 1780, 2000, 3000, 3840'
-%}

<img
  srcset="{{ product.featured_image | image_url: width: 375 }} 375w,
          {{ product.featured_image | image_url: width: 750 }} 750w,
          {{ product.featured_image | image_url: width: 1100 }} 1100w"
  sizes="(min-width: 750px) 50vw, 100vw"
  src="{{ product.featured_image | image_url: width: 750 }}"
  loading="lazy"
  alt="{{ product.featured_image.alt | escape }}"
>
```

---

## Code Review Checklist

Before submitting code:
- [ ] Code follows style guide conventions
- [ ] No console.log statements in production code
- [ ] Accessible (semantic HTML, ARIA labels, keyboard navigation)
- [ ] Responsive on mobile, tablet, and desktop
- [ ] Cross-browser tested (Chrome, Firefox, Safari, Edge)
- [ ] No hardcoded values (use settings or variables)
- [ ] Comments added for complex logic
- [ ] Git commit messages follow conventional commits

---

## Resources

### Shopify Documentation
- [Liquid Reference](https://shopify.dev/docs/api/liquid)
- [Theme Architecture](https://shopify.dev/docs/themes/architecture)
- [Ajax API](https://shopify.dev/docs/api/ajax)

### Tools
- [Shopify CLI](https://shopify.dev/docs/themes/tools/cli)
- [Theme Check](https://shopify.dev/docs/themes/tools/theme-check)
- [Lighthouse](https://developers.google.com/web/tools/lighthouse) (Performance & Accessibility)

---

**Last Updated**: October 2025  
**Maintained By**: Everyday AI Team
