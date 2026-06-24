

# Foodi bd - Restaurant Website Recreation

This project is a high-fidelity, production-ready recreation of the **Foodi bd** restaurant landing page screenshot. It is built using **pure HTML5 and CSS3 (zero JavaScript)**, ensuring ultra-fast load times, semantic accessibility, and clean responsive behaviors across all devices.

---

## 🛠️ Technical Architecture

### 1. Zero-JS Interactive Systems
To satisfy the rule of not using JavaScript, all dynamic UI components are handled natively via CSS:
* **Mobile Dropdown Navbar**: Uses the **CSS Checkbox Hack** (`input[type="checkbox"]` combined with sibling selectors `~` and `:checked`) to toggle the mobile menu and animate the hamburger icon into an "X" cleanly.
* **Smooth Scrolling**: Implemented globally via `scroll-behavior: smooth` in CSS to allow seamless navigation when using anchor links.

### 2. Layout & Spacing Engine
* **Concentric Flexbox & Grid Systems**: Used Grid layouts for key card columns (Signature Dishes, Testimonials, Collages) and Flexbox for linear layouts (Navbar, Hero Action Rows, Ratings, Footer Columns).
* **Responsive Breakpoints**:
  * **Desktop (1200px+)**: The maximum container width is constrained to `1200px` centered inside a custom gradient backdrop (`linear-gradient`) to match the mockup's viewport frame.
  * **Tablet (768px - 1024px)**: Sections adjust grid tracks from 3-columns to 2-columns/stacked layouts, maintaining readable font sizes and appropriate paddings.
  * **Mobile (Under 768px)**: Standard single-column block layout with the mobile navbar toggle activated.

---

## 🎨 Visual Identity & Styling Details

The website is designed with a premium, modern food brand aesthetic using custom CSS variables:

* **Color Palette**:
  * `Primary Green (#198754)`: Used for primary call-to-action (CTA) buttons, list badges, hover interactions, and logo accents.
  * `Primary Yellow (#F4C430)`: Used for the navbar button, star ratings, circular plate borders, and the reservation banner background.
  * `Beige Background (#FDF8EE)`: Alternates as the base background color for sections (Hero, Why Choose Us, Dinner Plan, Features, Footer) to contrast against pure white `#FFFFFF` sections.
* **Typography**: Integrated Google Fonts' **Poppins** (`300` to `800` weights) as the primary font family for modern, clean text rendering.
* **Micro-Animations & Interactive States**:
  * **Hero Floating Effect**: A CSS `@keyframes float` animation is applied to the main chicken dish, giving it a subtle 3D hover/rotation effect.
  * **Card Lift Transitions**: Product cards, chef cards, and testimonials slide upwards (`transform: translateY(-8px)`) and transition to a deeper box-shadow (`box-shadow`) on hover to encourage interaction.
  * **Image Scaling**: Dish images scale slightly inside their container overflow on card-hover, making the layout feel alive.

---

## 📐 Custom Shapes & Collage Layouts

To replicate the organic shapes from the mockup, we designed two specific layout structures in CSS:

### 1. Concentric Yellow Rings (Plate Wrappers)
In both the **Hero** and the **Dinner Plan** sections, the circular food plates are surrounded by double concentric yellow rings:
* The outer ring is styled as an absolute pseudo-element (`::after`) with a thin yellow border.
* The inner ring is styled using container padding and another solid border directly on the wrapper, while the image itself has a thick white border to represent the plate edge.

### 2. Asymmetric Collage Grids
In the **Why Choose Us** and **Features** sections, three images are grouped in a 2-column grid. We achieved the custom arch outlines by configuring asymmetric `border-radius` variables:
* **Left Tall Image**: `border-radius: 140px 140px 20px 20px` (gives the tall arch visual).
* **Top-Right Image**: `border-radius: 100px 100px 20px 20px` (arched top-right).
* **Bottom-Right Image**: `border-radius: 20px 20px 100px 100px` (arched bottom-right).

---

## 🗂️ Project Structure

The project code is modular, separated cleanly into three main layers:

```text
FOOD WEBSITE/
├── index.html          # Semantic HTML5 layout
├── style.css           # Modern CSS3 styles, variables, transitions & media queries
└── images/             # Local visual assets (PNGs and JPGs)
    ├── logo.png
    ├── hero-food.png
    ├── pasta.jpg
    ├── chowmein.jpg
    ├── fish.jpg
    ├── chef1.jpg
    ├── chef2.jpg
    ├── customer1.jpg
    ├── customer2.jpg
    ├── customer3.jpg
    ├── feature-food1.jpg
    ├── feature-food2.jpg
    └── reservation-food.jpg
```

---

## 🔗 Navigation Routing Mapping

All action targets and links navigate cleanly to their respective viewport positions using standard CSS section IDs:

* **Navbar Menu**:
  * `Home` ➡️ `#home`
  * `About Us` ➡️ `#about`
  * `Shop` ➡️ `#menu`
  * `Contact` ➡️ `#reservation`
  * `Blog` ➡️ `#footer`
* **CTAs**:
  * **Order Now** (Navbar / Hero) ➡️ `#menu` (Dishes)
  * **Explore More** (Why Choose Us) ➡️ `#features` (Key Features)
  * **Book A Table** (Dinner Plan / CTA) ➡️ `#reservation` (Reservation)
  * **Add To Cart** (Dish Cards) ➡️ `#reservation` (Reservation)
