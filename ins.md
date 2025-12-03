cursor .
```

Or: Open Cursor app → File → Open Folder → Select `halcyon-website`

---

## Step 4: Configure Tailwind with Brand Colors

**Open:** `tailwind.config.ts`

**Prompt for Cursor:**
```
Update tailwind.config.ts with these exact brand colors:
- navy: '#0a0f1a'
- gold: '#bfa14a'
- ivory: '#fdfdf9'
- softgray: '#dcdcdc'

Add these font families:
- serif: ['Playfair Display', 'serif']
- sans: ['Inter', 'sans-serif']

Keep all existing Next.js config. Just extend the theme.
```

---

## Step 5: Update Global Styles

**Open:** `app/globals.css`

**Prompt for Cursor:**
```
Replace the contents of globals.css with:

1. Import Google Fonts: Playfair Display (weights 400, 500, 600, 700) and Inter (weights 400, 500, 600, 700)
2. Keep Tailwind directives (@tailwind base, components, utilities)
3. Add smooth scroll behavior to html
4. Set body background to ivory (#fdfdf9)
5. Remove any default Next.js styles

Make it clean and minimal.
```

---

## Step 6: Build Components (One by One)

### Component 1: Hero Section

**Create file:** `components/Hero.tsx`

**Prompt for Cursor:**
```
Create a Hero component for Halcyon luxury hotel platform.

Requirements:
- Full viewport height (min-h-screen)
- Navy background (#0a0f1a)
- Centered content with max-w-5xl container
- Logo placeholder: Simple gold "H" in serif font (or text "Halcyon" if no logo)
- Main heading: "Halcyon" (font-serif, text-6xl md:text-8xl, text-ivory, mb-6)
- Tagline: "Golden Hours, Redefined." (text-gold, text-xl md:text-2xl, tracking-wider, mb-8)
- Description: "The world's first curated collection of 5-star day-use experiences." (text-ivory/80, text-lg, max-w-2xl mx-auto, mb-12)
- Two CTA buttons (flex flex-col sm:flex-row gap-4):
  1. "For Hotels" - links to #partnership (bg-gold text-navy px-8 py-4 rounded-sm hover:bg-gold/90)
  2. "Join Waitlist" - links to #waitlist (border-2 border-gold text-ivory px-8 py-4 rounded-sm hover:bg-gold/10)

Use 'use client' directive.
Fully responsive, mobile-first.
Export as default.
```

---

### Component 2: Concept Section

**Create file:** `components/Concept.tsx`

**Prompt for Cursor:**
```
Create a Concept section component.

Layout:
- Section with ivory background, py-24, px-4
- Max-w-4xl container, centered
- Text-center alignment

Content:
- Small gold icon divider at top (simple SVG geometric shape, mb-8)
- Heading: "The Concept" (font-serif, text-4xl, text-navy, mb-8)
- Paragraph 1: "Halcyon connects 5-star hotels with discerning guests seeking refined daytime experiences from 9 AM to 5 PM."
- Paragraph 2: "We showcase only luxury properties, ensuring your brand is positioned alongside peers of the highest caliber."
- Both paragraphs: text-navy/80, text-lg, leading-relaxed, mb-6
- Small gold icon divider at bottom (mt-8)

Keep language aspirational and vague (no technical details).
Export as default.
```

---

### Component 3: Benefits Section

**Create file:** `components/Benefits.tsx`

**Prompt for Cursor:**
```
Create a Benefits section with cards.

Layout:
- Navy background, py-24, px-4
- Max-w-7xl container

Content:
- Heading: "Why Hotels Choose Halcyon" (font-serif, text-4xl, text-ivory, text-center, mb-16)
- Define benefits array with these 5 items:
  1. title: "Incremental Revenue", description: "Monetize daytime inventory without impacting overnight rates."
  2. title: "Premium Positioning", description: "Curated, invitation-only collection—never discount-driven."
  3. title: "High-Value Guests", description: "Executives, travelers, and locals who align with your brand."
  4. title: "Operational Ease", description: "Integrates seamlessly with your existing systems."
  5. title: "Risk-Free Model", description: "Guaranteed prepaid bookings with flexible terms."

Card Grid:
- grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8
- Each card: border border-gold/20, p-6, rounded-sm, hover:scale-105 transition-transform
- Title: text-gold, font-medium, text-xl, mb-3
- Description: text-ivory/70, leading-relaxed

Use .map() to render cards from array.
TypeScript with proper types.
Export as default.
```

---

### Component 4: Guest Profiles Section

**Create file:** `components/Guests.tsx`

**Prompt for Cursor:**
```
Create "Who Our Guests Are" section.

Layout:
- Ivory background, py-24, px-4
- Max-w-7xl container

Content:
- Heading: "Who Our Guests Are" (font-serif, text-4xl, text-navy, text-center, mb-16)
- Three guest profiles in grid (grid-cols-1 md:grid-cols-3 gap-12)

Guest profiles array:
1. title: "Executives", description: "Between meetings, seeking productive sanctuaries with private spaces for calls and presentations."
2. title: "Long-Haul Travelers", description: "Rest between flights in refined comfort."
3. title: "Locals", description: "Booking premium spa, wellness, and dining escapes."

Each profile card (text-center):
- Gold number (text-5xl, font-serif, text-gold, mb-4) - use index + 1
- Title (text-xl, font-medium, text-navy, mb-3)
- Description (text-navy/70, leading-relaxed)

Note: First profile subtly mentions "private spaces for calls" without being explicit about meeting rooms.

Export as default.
```

---

### Component 5: Partnership Form

**Create file:** `components/PartnershipForm.tsx`

**Prompt for Cursor:**
```
Create a partnership inquiry form component.

Important: Use 'use client' directive and import useForm from 'react-hook-form'
Install react-hook-form if needed: npm install react-hook-form

Layout:
- Section with id="partnership", navy background, py-24, px-4
- Max-w-2xl container, centered
- Card: bg-navy, border border-gold/20, p-8, rounded-sm

Content:
- Heading: "Join Our Flagship Collection" (font-serif, text-3xl, text-ivory, mb-4, text-center)
- Subheading: "We're curating our inaugural collection. Invitation-only partnerships." (text-ivory/70, mb-8, text-center)

Form fields (all with navy bg, border border-softgray, text-ivory, focus:border-gold):
1. Hotel Name (required) - text input
2. Your Name (required) - text input
3. Your Role (required) - dropdown: "Select role", "General Manager", "Revenue Manager", "Owner", "Other"
4. Hotel Location / City (required) - text input
5. Email (required, email validation) - email input
6. Phone (optional) - tel input
7. Message (optional) - textarea, 4 rows

Styling:
- Label above each field (text-ivory, text-sm, font-medium, mb-2)
- Inputs: w-full, rounded-sm, px-4, py-3
- Space between fields: space-y-6
- Error messages: text-red-400, text-sm, mt-1

Submit button:
- "Request Partnership Information"
- w-full, bg-gold, text-navy, py-4, rounded-sm, font-medium, text-lg, hover:bg-gold/90

Functionality:
- Use react-hook-form for validation
- onSubmit: console.log(data) and show success message
- Success message: "Thank you! We'll be in touch soon." (text-gold, text-center, font-medium, mt-4)
- Auto-hide success after 5 seconds

TypeScript with proper FormData type.
Export as default.
```

---

### Component 6: Waitlist Form

**Create file:** `components/WaitlistForm.tsx`

**Prompt for Cursor:**
```
Create a guest waitlist form component.

Important: Use 'use client' directive and import useForm from 'react-hook-form'

Layout:
- Section with id="waitlist", ivory background, py-24, px-4
- Max-w-lg container, centered

Content:
- Heading: "For Guests" (font-serif, text-3xl, text-navy, mb-4, text-center)
- Subheading: "Be among the first to access our exclusive collection." (text-navy/70, mb-8, text-center)

Form fields:
1. Name (required) - text input
2. Email (required, email validation) - email input
3. Label: "I'm interested in Halcyon for:" (text-navy, text-sm, font-medium, mb-3)
4. Checkboxes (allow multiple selection):
   - "Rest between flights"
   - "Spa & wellness"
   - "Dining experiences"
   - "Private meetings / workspace"
   - "Other"

Input styling:
- Border border-softgray, bg-white, text-navy, focus:border-gold
- Inputs: w-full, rounded-sm, px-4, py-3
- Checkboxes: w-5 h-5, text-gold accent color, space-y-2
- Checkbox labels: flex items-center space-x-3 cursor-pointer

Submit button:
- "Join Waitlist"
- w-full, bg-gold, text-navy, py-4, rounded-sm, font-medium, text-lg, hover:bg-gold/90

Functionality:
- Use react-hook-form
- onSubmit: console.log(data) and show success
- Success: "Thank you! You're on the list." (text-gold, text-center, font-medium, mt-4)

This form validates meeting room demand via checkboxes.
Export as default.
```

---

### Component 7: Footer

**Create file:** `components/Footer.tsx`

**Prompt for Cursor:**
```
Create a simple footer component.

Layout:
- Navy background, py-12, px-4
- Max-w-4xl container, centered, text-center

Content:
- Logo/Brand name: "Halcyon" (font-serif, text-2xl, text-gold, mb-4)
- Email link: "connect@halcyon.luxury" (mailto link, text-ivory, hover:text-gold, transition-colors, text-lg, block, mb-4)
- Launch text: "Launching in select cities, Q1 2025" (text-ivory/60, text-sm, mb-6)
- Social media placeholders (flex justify-center gap-6):
  * Instagram icon (SVG) - link to "#"
  * LinkedIn icon (SVG) - link to "#"
  * Both: text-ivory hover:text-gold transition-colors
  * Each w-6 h-6

Use simple SVG icons for social media (Instagram and LinkedIn paths).
Add sr-only text for accessibility.
Export as default.
```

---

## Step 7: Build Main Page

**Edit file:** `app/page.tsx`

**Prompt for Cursor:**
```
Create the main homepage by importing and composing all components.

Import these components:
- Hero from '@/components/Hero'
- Concept from '@/components/Concept'
- Benefits from '@/components/Benefits'
- Guests from '@/components/Guests'
- PartnershipForm from '@/components/PartnershipForm'
- WaitlistForm from '@/components/WaitlistForm'
- Footer from '@/components/Footer'

Layout:
Stack all components vertically in <main> tag with min-h-screen class.
No gaps between sections.
Sections alternate backgrounds naturally (navy, ivory, navy, ivory, navy, ivory, navy).

Order:
1. Hero (navy)
2. Concept (ivory)
3. Benefits (navy)
4. Guests (ivory)
5. PartnershipForm (navy)
6. WaitlistForm (ivory)
7. Footer (navy)

Export as default Home page.
Remove any boilerplate Next.js content.
```

---

## Step 8: Update Layout

**Edit file:** `app/layout.tsx`

**Prompt for Cursor:**
```
Update the layout.tsx file:

1. Keep existing RootLayout structure
2. Update metadata:
   - title: "Halcyon — Golden Hours, Redefined"
   - description: "The world's first curated collection of 5-star day-use experiences."
3. Import './globals.css'
4. Apply font-sans class to body element
5. Add 'antialiased' class to body for better font rendering
6. Keep html lang="en"

Clean, minimal layout.
