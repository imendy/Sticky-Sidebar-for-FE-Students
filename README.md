# Sticky Sidebar Layout in CSS

This project demonstrates how to create a sticky sidebar layout using CSS `position: sticky` and the CSS grid layout. The purpose of this project is to help frontend students understand not just how to make an element sticky, but also the role of each CSS property in achieving the effect.

## Getting Started

To experiment with the code yourself, follow the instructions below to clone the repository to your local machine.

### Cloning the Repository

1. Open your terminal (Command Prompt, Git Bash, etc.).
2. Run the following command to clone the repository:

    ```bash
    git clone https://github.com/imendy/Sticky-Sidebar-for-FE-Students.git
    ```

3. Navigate to the cloned folder:

    ```bash
    cd Sticky-Sidebar-for-FE-Students
    ```

4. Open the project in your favorite code editor (e.g., VS Code) or open the `index.html` file in a web browser to see the sticky sidebar in action.

---

## Sticky Sidebar: Key CSS Properties and Explanation

The goal is to have a sidebar that sticks to the screen when the user scrolls past it. To achieve this, we rely on a few key concepts in CSS positioning—mainly `position: sticky`.

### Example CSS:

```css
aside {
  position: sticky;
  top: var(--aside-top);
}
```

### `position: sticky;`

This is the core of the sticky sidebar effect. When an element has `position: sticky`, it behaves like relative positioning until the user scrolls past it. Once the element reaches the top of the viewport (or another specified position), it switches to fixed positioning and "sticks" in place as the user continues scrolling.

This is perfect for sidebars that you want users to have constant access to while scrolling through the rest of the page.

### `top: var(--aside-top);`

The `top` property defines where the sidebar will "stick" relative to the top of the viewport. In this case, we're using a variable `--aside-top` to control the exact distance. This ensures that when the sidebar sticks, it doesn’t press directly against the top edge of the screen but maintains a small gap (2rem in this case).

The value `top: 2rem;` creates that buffer, making the layout look nicer and less cramped.

---

## Why Use `position: sticky`?

Unlike `position: fixed`, which locks an element to a specific position in the viewport, `sticky` gives us a hybrid solution. The element remains in flow with the document until the user scrolls to a certain point, after which it becomes "fixed." This keeps the sidebar accessible without it always occupying a fixed place on the screen, which would make the design feel rigid and unnatural.

---

## Grid Layout for Sidebar and Main Content

### Example CSS:

```css
main {
  display: grid;
  grid-template-columns: 200px 1fr;
  gap: var(--gap);
}
```


### `display: grid;`

We use grid to create a two-column layout, where one column is for the sidebar, and the other is for the main content. This makes it easier to control the positioning and behavior of both elements.

The advantage of using grid layout is that it is highly flexible and responsive. We can define exactly how much space each column should take up.

### `grid-template-columns: 200px 1fr;`

This line specifies how the available space is divided between the sidebar and the main content:

- The first column (`200px`) is a fixed-width sidebar, so it stays 200 pixels wide no matter how wide or narrow the screen is.
- The second column (`1fr`) is flexible, taking up the remaining space. This ensures the main content fills the rest of the screen after accounting for the sidebar.

`gap: var(--gap);`

The `gap` property adds space between the sidebar and the main content (in this case, 2rem). This creates a clean separation between the two, making the layout easier to read and navigate.

**Why Use Grid Layout?**

The grid layout gives us control over the positioning of elements without needing to use floats or complicated margins. It also plays well with `position: sticky`, allowing the sidebar to stay within its grid cell while becoming sticky on scroll.

The fixed width for the sidebar ensures it remains a constant size, while the flexible main content area adapts to different screen sizes.


## Sidebar Scroll Behavior

**Example CSS:**

```css
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

These styles ensure that there are no unexpected margins or padding around the elements. This is important for a sticky sidebar because we want everything positioned exactly as expected when the user scrolls.

The `box-sizing: border-box;` property ensures that padding and borders are included in the element’s width and height calculations, preventing issues with layout shifts that might interfere with the sidebar's position when sticking.


```css
aside {
  max-height: 100vh;
  overflow-y: auto;
}
```

While this wasn’t explicitly in the CSS, it's a common practice to ensure that the sidebar doesn't extend beyond the viewport.

The `max-height: 100vh;` property limits the height of the sidebar to the full height of the viewport. It prevents the sidebar from extending beyond the screen, which would interfere with the sticky behavior.

The `overflow-y: auto;` property ensures the sidebar becomes scrollable if its content exceeds the viewport height, allowing users to access all the content without breaking the sticky layout.


### Summary of Key Concepts

- `position: sticky` is ideal for sidebars because it allows the element to act like a part of the page until the user scrolls past it. Once scrolled, the sidebar stays fixed at the top of the screen, ensuring it remains visible without interfering with the flow of the document.

- `top: value;` defines where the sticky element will "stick" to the viewport. This ensures the sidebar has a smooth transition into its sticky state and maintains a proper distance from the top.

- Grid layout (with `grid-template-columns`) makes it easier to manage the sidebar and main content layout, allowing for responsive design and controlling how much space each section occupies.

- The sidebar stays within its grid column but becomes sticky at the specified point, maintaining a clean and responsive design.

This breakdown focuses on how to use `position: sticky` effectively for a sidebar and why other related properties (like grid and spacing) are essential for making the layout work properly in a scrolling environment.
