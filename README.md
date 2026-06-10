# Pockverse Client Portal (B2B Frontend Layouts)

An interactive, responsive B2B e-commerce client management and packaging workflow ecosystem. Built with clean, structural **HTML5**, advanced styling layouts (**CSS3 Grid & Flexbox**), and lightweight, reactive vanilla **JavaScript**.

This portal serves as the primary hub for global accounts to coordinate packaging CAD design reviews, track large-scale commercial manufacturing runs, handle RFQ approvals, and interact with engineering teams in real-time.

---

## 🎨 Branding & Design System

The platform utilizes a modern, dark navy corporate aesthetic tailored for high-end technical enterprise software:

| Element | Color Code | Visual Application |
| :--- | :--- | :--- |
| **Primary Navy** | `#0b2545` | Main navigation header, structural footers, primary action buttons, component section headers |
| **Accent Sky Blue** | `#00aaff` | Brand typography logos, interactive main nav text focus underlines |
| **Interactive Blue** | `#007bff` / `#005f99` | Primary vector icon coloring, project box borders on hover, button click states |
| **System Canvas** | `#f5f8fa` | Soft contrast viewport background to separate content panels cleanly |
| **Workspace White** | `#ffffff` | Floating interactive cards, data tables, and user input modules |
| **Typography Matrix** | `"Poppins"`, `"Noto Sans TC"` | Dynamic font pairing matching clean English structure with high-legibility Traditional Chinese sans-serif |

---

## 📂 Core Architecture & Interface Files

The workspace is split into modular standalone templates engineered for clean separation of concerns:

### 1. Account Management System (`account.html`)
Converts the layout into a complete **My Account / Client Dashboard** environment powered by an interactive, non-refresh sidebar routing engine.
* **Packaging Designs:** Grid system parsing mock project boxes (e.g., Corrugated Runs, Gift Cases) with clean hover lift animations.
* **Order Tracking:** Manufacturing logs featuring color-coded state badges (`In Production`, `Delivered`).
* **Commercial RFQ Matrix:** Custom data grids tracking technical packaging volume parameters and quote status tiers.
* **Direct Messaging Engine:** Live workspace chat box container capturing mock message nodes, dynamically processing user submittals, and executing automated scroll resets.

### 2. Cart & Checkout Flow (`cart.html`)
* **Split View Workspace:** Employs a `7fr 4fr` CSS Grid that dynamically folds into a single stacked column view on mobile devices.
* **Live Calculations:** Native JS handlers calculating dynamic subtotals on quantity modifiers automatically.

---

## 🛠️ Technical Highlights

* **Dual-Language Accessibility:** Navigations and layout sections feature semantic dual-language formatting with clear English labels paired with Traditional Chinese sub-captions (`<span>`) for cross-border user clarity.
* **Asynchronous Tab Switching:** Utilizes clean JavaScript state management to toggle active view visibility panels (`.tab-panel`) effortlessly, preventing heavy server round-trips.
* **Responsive Breakpoints:** 
  * Desktop and Tablets (`@media max-width: 1024px`): Structural grid arrays smoothly recalculate layout distributions.
  * Mobile Displays (`@media max-width: 850px`): Sidebar nav and data content blocks automatically drop into a linear stacked format optimized for one-handed mobile scrolling.

```javascript
// Native implementation for smooth, non-refresh tab routing
function showTab(tabId, buttonElement) {
  document.querySelectorAll('.tab-panel').forEach(panel => {
    panel.style.display = 'none';
  });
  const targetPanel = document.getElementById(tabId);
  if (targetPanel) {
    targetPanel.style.display = 'block';
  }
  document.querySelectorAll('.sidebar-menu button').forEach(btn => {
    btn.classList.remove('active');
  });
  buttonElement.classList.add('active');
}
