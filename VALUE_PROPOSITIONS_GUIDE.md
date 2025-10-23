# Value Propositions Section - Usage Guide

## Overview
The Value Propositions section displays your key value propositions in a responsive 3-column grid with Font Awesome icons.

## File Location
`/sections/value-propositions.liquid`

## Features
- ✅ Responsive 3-column grid (mobile: 1 column, tablet: 2 columns, desktop: 3 columns)
- ✅ Font Awesome icon support
- ✅ Gradient icon backgrounds (purple to pink)
- ✅ Hover animations with lift effect
- ✅ Fade-in animations with staggered delays
- ✅ Fully customizable through Shopify theme editor
- ✅ Accessibility features (reduced motion support)

## How to Add to Your Store

### Method 1: Through Theme Editor
1. Go to **Online Store > Themes > Customize**
2. Click **Add section**
3. Select **Value Propositions**
4. The section will appear with 3 default value propositions

### Method 2: Add to a Template
Add this code to any template file (e.g., `index.json`):

```json
{
  "type": "value-propositions",
  "settings": {
    "heading": "Why Choose Unmuted"
  },
  "blocks": [
    {
      "type": "value_prop",
      "settings": {
        "icon": "brain",
        "title": "Smart Analysis, Actually Funny",
        "description": "We don't just recap—we analyze. Critical thinking that doesn't put you to sleep."
      }
    }
  ]
}
```

## Customization Options

### Section Settings
- **Section Heading**: Optional heading above the value propositions
- **Color Scheme**: Choose from your theme's color schemes

### Block Settings (Each Value Proposition)
- **Icon**: Font Awesome icon name (without 'fa-' prefix)
- **Title**: The main heading for this value proposition
- **Description**: Detailed description text

## Font Awesome Icons

### Popular Icon Names
Here are some icon names you can use (enter without the 'fa-' prefix):

**General:**
- `brain` - Brain icon
- `users` - Multiple users
- `lightbulb` - Light bulb
- `heart` - Heart
- `star` - Star
- `bolt` - Lightning bolt
- `shield` - Shield
- `rocket` - Rocket

**Media & Communication:**
- `video` - Video camera
- `microphone` - Microphone
- `headphones` - Headphones
- `podcast` - Podcast
- `comments` - Comments/chat
- `bullhorn` - Megaphone

**Learning & Education:**
- `graduation-cap` - Graduation cap
- `book` - Book
- `pencil` - Pencil
- `chalkboard-teacher` - Teacher at chalkboard

**Social & Community:**
- `user-friends` - Friends
- `hands-helping` - Helping hands
- `handshake` - Handshake
- `people-group` - Group of people

**Quality & Trust:**
- `check-circle` - Check mark in circle
- `award` - Award/medal
- `gem` - Diamond/gem
- `crown` - Crown

### Finding More Icons
Visit [Font Awesome Icons](https://fontawesome.com/icons) to browse all available icons.
- Use the **free** icons only
- Copy the icon name (e.g., "fa-brain" → use "brain")

## Default Content
The section comes pre-configured with these three value propositions:

1. **Smart Analysis, Actually Funny** (brain icon)
2. **Multiple POVs, Real Representation** (users icon)
3. **Media Literacy Made Fun** (lightbulb icon)

## Styling Details

### Colors
- Icon background: Purple to pink gradient
- Card background: White
- Title color: Dark gray (#111827)
- Description color: Medium gray (#4B5563)

### Spacing
- Section padding: 4rem (64px) top and bottom
- Card gap: 48px on desktop
- Card padding: 1.5rem (24px)

### Responsive Breakpoints
- **Mobile** (< 750px): 1 column, 48px gap
- **Tablet** (750px - 989px): 2 columns, 40px gap
- **Desktop** (≥ 990px): 3 columns, 48px gap

## Animation Details
- **Fade-in animation**: Cards fade in from bottom with 30px offset
- **Staggered delays**: 0.1s, 0.2s, 0.3s for each card
- **Hover effect**: Cards lift 8px on hover with enhanced shadow
- **Reduced motion**: Animations disabled for users with motion sensitivity

## CSS Classes Reference

### Main Classes
- `.value-props` - Section wrapper
- `.value-props__container` - Content container
- `.value-props__heading` - Optional section heading
- `.value-props-grid` - Grid container
- `.value-prop-card` - Individual card
- `.value-prop-icon` - Icon container
- `.value-prop-title` - Card title
- `.value-prop-description` - Card description

## Tips for Best Results

1. **Keep titles short**: 3-7 words work best
2. **Description length**: 20-40 words for optimal readability
3. **Icon selection**: Choose icons that clearly represent your value prop
4. **Consistency**: Use similar description lengths for visual balance
5. **Number of cards**: 3 cards work best, but 2-4 are supported

## Troubleshooting

### Icons not showing?
- Verify Font Awesome is loaded (check line 304 in `layout/theme.liquid`)
- Ensure icon name is correct (no 'fa-' prefix)
- Check icon is available in Font Awesome 6.0.0 free version

### Layout issues?
- Clear browser cache
- Check for CSS conflicts with other sections
- Verify the section is added to a valid template

### Animation not working?
- Check if user has reduced motion enabled in browser
- Verify CSS is loading correctly
- Check browser console for errors

## Support
For more customization options or issues, refer to:
- Shopify theme documentation
- Font Awesome documentation
- Your theme's support resources
