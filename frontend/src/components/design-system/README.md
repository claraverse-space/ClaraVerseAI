# ClaraVerse Design System v1.0

## Overview

A production-ready design system for ClaraVerse featuring a premium dark theme with Rose Pink accent colors. Built with React, TypeScript, and CSS custom properties for maximum flexibility and type safety.

## Installation

All design system components are already included in this project. Simply import them from the design-system folder:

```tsx
import { Button, Card, Typography } from '@/components/design-system';
```

## Quick Start

### Using Components

```tsx
import { Button, Card, Badge, Typography } from '@/components/design-system';

function MyComponent() {
  return (
    <Card variant="glass" title="Welcome" description="Get started">
      <Typography variant="h3">Hello World</Typography>
      <Button variant="primary" size="lg">
        Get Started
      </Button>
      <Badge variant="accent" dot>
        New
      </Badge>
    </Card>
  );
}
```

### Using Design Tokens

All design tokens are available as CSS custom properties:

```css
.my-component {
  background: var(--color-surface);
  padding: var(--space-8);
  border-radius: var(--radius-lg);
  color: var(--color-text-primary);
  transition: var(--transition-base);
}

.my-component:hover {
  background: var(--color-surface-elevated);
  box-shadow: var(--shadow-glow-md);
}
```

## Components

### Button

Multiple variants and sizes with loading states:

```tsx
<Button variant="primary" size="md" loading={false}>
  Click Me
</Button>

<Button variant="secondary" size="lg">
  Secondary
</Button>

<Button variant="ghost" disabled>
  Disabled
</Button>
```

**Props:**

- `variant`: 'primary' | 'secondary' | 'ghost'
- `size`: 'sm' | 'md' | 'lg' | 'xl'
- `loading`: boolean
- `fullWidth`: boolean
- All standard button HTML attributes

### Card

Three card variants with optional hover effects:

```tsx
<Card variant="glass" hoverable title="Card Title" description="Description">
  Card content
</Card>

<Card variant="feature" icon="🚀" title="Feature">
  Feature content
</Card>

<Card variant="widget">
  Widget content
</Card>
```

**Props:**

- `variant`: 'glass' | 'feature' | 'widget'
- `hoverable`: boolean (default: true)
- `icon`: ReactNode
- `title`: string
- `description`: string

### Input & Textarea

Form inputs with labels, errors, and helper text:

```tsx
<Input
  label="Email"
  type="email"
  placeholder="you@example.com"
  helperText="We'll never share your email"
  error="Email is required"
/>

<Textarea
  label="Message"
  placeholder="Your message..."
  helperText="Maximum 500 characters"
/>
```

**Props:**

- `label`: string
- `error`: string
- `helperText`: string
- All standard input/textarea HTML attributes

### Badge

Status indicators with multiple variants:

```tsx
<Badge variant="accent" dot>Active</Badge>
<Badge variant="success">Success</Badge>
<Badge variant="warning">Warning</Badge>
<Badge variant="error">Error</Badge>
<Badge variant="info">Info</Badge>
```

**Props:**

- `variant`: 'default' | 'accent' | 'success' | 'warning' | 'error' | 'info'
- `dot`: boolean
- `icon`: ReactNode

### Progress

Animated progress bars with labels:

```tsx
<Progress value={65} showLabel label="Upload Progress" />
<Progress value={100} showLabel />
```

**Props:**

- `value`: number (0-100)
- `max`: number (default: 100)
- `showLabel`: boolean
- `label`: string

### Skeleton

Loading placeholders for async content:

```tsx
<Skeleton variant="text" count={3} />
<Skeleton variant="circular" width={60} height={60} />
<Skeleton variant="rectangular" height={120} />
```

**Props:**

- `variant`: 'text' | 'circular' | 'rectangular'
- `width`: string | number
- `height`: string | number
- `count`: number

### Typography

Flexible typography with fluid sizing:

```tsx
<Typography variant="display" gradient>
  Display Text
</Typography>

<Typography variant="h1" weight="bold" align="center">
  Heading 1
</Typography>

<Typography variant="base" as="p">
  Body text
</Typography>
```

**Props:**

- `variant`: 'display' | 'h1' | 'h2' | 'h3' | 'h4' | 'h5' | 'h6' | 'xl' | 'lg' | 'base' | 'sm' | 'xs'
- `weight`: 'light' | 'normal' | 'medium' | 'semibold' | 'bold' | 'black'
- `align`: 'left' | 'center' | 'right'
- `gradient`: boolean
- `as`: ElementType (override default HTML element)

## Design Tokens

### Colors

```css
--color-accent: #e91e63; /* Rose Pink */
--color-success: #30d158; /* Green */
--color-warning: #ffd60a; /* Yellow */
--color-error: #ff453a; /* Red */
--color-info: #64d2ff; /* Blue */

--color-background: #000000;
--color-surface: rgba(255, 255, 255, 0.02);
--color-surface-elevated: rgba(255, 255, 255, 0.04);

--color-text-primary: #f5f5f7;
--color-text-secondary: #a1a1a6;
--color-text-tertiary: #6e6e73;
```

### Spacing

```css
--space-2: 0.5rem; /* 8px */
--space-4: 1rem; /* 16px */
--space-6: 1.5rem; /* 24px */
--space-8: 2rem; /* 32px */
--space-12: 3rem; /* 48px */
```

### Typography

```css
--text-display: clamp(3.5rem, 8vw, 7rem);
--text-h1: clamp(3rem, 7vw, 6rem);
--text-base: 1rem;
--text-sm: 0.875rem;
```

### Effects

```css
--shadow-glow-md: 0 10px 30px rgba(233, 30, 99, 0.3);
--radius-lg: 1rem;
--radius-full: 9999px;
--transition-base: 300ms cubic-bezier(0.4, 0, 0.2, 1);
--backdrop-blur-lg: blur(30px);
```

## Design Principles

### 1. Dark First

Everything designed for dark mode with subtle borders and glassmorphism effects.

### 2. Rose Pink Accent

Strategic use of #e91e63 for maximum visual impact on key interactions.

### 3. Smooth Animations

300ms transitions with cubic-bezier easing for Apple-like smoothness.

### 4. Glassmorphism

Backdrop blur and semi-transparent surfaces for layered depth.

### 5. Accessible

WCAG AA compliant with proper focus states and reduced motion support.

### 6. Responsive

Mobile-first design with fluid typography using CSS clamp().

## Best Practices

### Do's ✅

- Use Rose Pink (#e91e63) consistently for primary actions
- Apply smooth transitions to all interactive elements
- Use backdrop-filter for glassmorphism effects
- Keep shadows soft and subtle
- Add hover states that lift elements
- Use fluid typography with clamp()
- Maintain proper semantic HTML

### Don'ts ❌

- Don't use pure white (#fff) for text - use #f5f5f7
- Don't skip transitions on interactive elements
- Don't use harsh shadows
- Don't overuse the accent color
- Don't forget focus states for keyboard navigation
- Don't use borders thicker than 1.5px

## Showcase

Visit `/design-system` in your browser to see all components in action with interactive examples.

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## TypeScript Support

All components are fully typed with TypeScript for excellent IDE support and type safety.

## License

MIT License - See LICENSE file for details

---

**Built with ❤️ for ClaraVerse by @badboysm890**
