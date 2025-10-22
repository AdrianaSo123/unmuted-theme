# Unmuted Design System

## Brand Identity
- **Aesthetic**: Bold, Vibrant, Pop Culture - Teen drama energy
- **Tone**: Unapologetic, Fresh, Modern

## Color System
```css
:root {
  /* Primary Brand Colors */
  --primary: #A855F7;        /* Electric Purple */
  --secondary: #EC4899;      /* Hot Pink */
  --accent: #06B6D4;         /* Cyan */
  
  /* Dark Mode */
  --dark-primary: #0F172A;   /* Darkest */
  --dark-secondary: #1E293B; /* Darker */
  --dark-tertiary: #334155;  /* Primary dark */
  
  /* Neutrals */
  --background: #FAFAFA;     /* Off White */
  --surface: #FFF9F5;        /* Warm White */
  --text-primary: #111827;   /* Darkest text */
  --text-secondary: #374151; /* Headings */
  --text-body: #6B7280;      /* Body text */
}
```

## Typography Scale
```css
:root {
  /* Font Families */
  --font-heading: 'Playfair Display', serif;
  --font-body: 'Inter', sans-serif;
  
  /* Font Sizes */
  --text-xs: 0.75rem;    /* 12px */
  --text-sm: 0.875rem;   /* 14px */
  --text-base: 1rem;     /* 16px */
  --text-lg: 1.125rem;   /* 18px */
  --text-xl: 1.25rem;    /* 20px */
  --text-2xl: 1.5rem;    /* 24px */
  --text-3xl: 1.875rem;  /* 30px */
  --text-4xl: 2.25rem;   /* 36px */
  --text-5xl: 3rem;      /* 48px */
  
  /* Line Heights */
  --leading-tight: 1.25;
  --leading-normal: 1.5;
  --leading-relaxed: 1.75;
  
  /* Font Weights */
  --font-normal: 400;
  --font-medium: 500;
  --font-semibold: 600;
  --font-bold: 700;
}
```

## Spacing System
```css
:root {
  --space-1: 0.25rem;   /* 4px */
  --space-2: 0.5rem;    /* 8px */
  --space-3: 0.75rem;   /* 12px */
  --space-4: 1rem;      /* 16px */
  --space-5: 1.25rem;   /* 20px */
  --space-6: 1.5rem;    /* 24px */
  --space-8: 2rem;      /* 32px */
  --space-10: 2.5rem;   /* 40px */
  --space-12: 3rem;     /* 48px */
  --space-16: 4rem;     /* 64px */
  --space-20: 5rem;     /* 80px */
  --space-24: 6rem;     /* 96px */
}
```

## Border Radius
```css
:root {
  --radius-sm: 0.125rem;  /* 2px */
  --radius-md: 0.375rem;  /* 6px */
  --radius-lg: 0.5rem;    /* 8px */
  --radius-xl: 0.75rem;   /* 12px */
  --radius-2xl: 1rem;     /* 16px */
  --radius-full: 9999px;  /* Fully rounded */
}
```

## Shadows
```css
:root {
  --shadow-sm: 0 1px 2px 0 rgb(0 0 0 / 0.05);
  --shadow-md: 0 4px 6px -1px rgb(0 0 0 / 0.1);
  --shadow-lg: 0 10px 15px -3px rgb(0 0 0 / 0.1);
  --shadow-xl: 0 20px 25px -5px rgb(0 0 0 / 0.1);
  --shadow-2xl: 0 25px 50px -12px rgb(0 0 0 / 0.25);
}
```

## Component Patterns

### Buttons
- **Primary**: Purple background, white text
- **Secondary**: Pink background, white text
- **Tertiary**: Cyan background, white text
- **Ghost**: Transparent with colored border

### Cards
- White background with subtle shadow
- Rounded corners (--radius-lg)
- Padding: --space-6

### Navigation
- Dark background (--dark-primary)
- Purple accent on hover
- Sticky header with shadow on scroll

## Accessibility Requirements
- Minimum contrast ratio: 4.5:1 for text
- Focus indicators on all interactive elements
- Semantic HTML structure
- ARIA labels where needed
- Keyboard navigation support

## Responsive Breakpoints
```css
/* Mobile first approach */
--breakpoint-sm: 640px;   /* Small devices */
--breakpoint-md: 768px;   /* Tablets */
--breakpoint-lg: 1024px;  /* Laptops */
--breakpoint-xl: 1280px;  /* Desktops */
--breakpoint-2xl: 1536px; /* Large screens */
```

## Animation Guidelines
- Use `transition: all 0.3s ease` for smooth interactions
- Hover states should include subtle transforms
- Loading states use purple gradient animation
- Page transitions: fade in/out

## Brand Voice
- **Bold & Confident**: Don't shy away from strong statements
- **Pop Culture Savvy**: Reference trends and cultural moments
- **Inclusive**: Welcoming to all fans
- **Energetic**: Use active voice and dynamic language
