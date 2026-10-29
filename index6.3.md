File 1: index.html
HTML
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Assignment 6.3 - Overflow & Layout Fixing</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

  <header class="page-header">
    <h1>CSS Overflow Properties Showcase</h1>
    <p>Exploring visible, hidden, scroll, and auto overflow behaviors in fixed-size containers.</p>
  </header>

  <main class="container">

    <!-- 1. Overflow: Visible -->
    <section class="demo-section">
      <h2>1. overflow: visible (Default)</h2>
      <p>Content overflows outside the box boundaries without clipping.</p>
      <div class="box overflow-visible">
        <p>This content is taller than the container's fixed height. With <code>overflow: visible</code>, the extra text spills out of the bottom border and overlaps surrounding elements.</p>
        <p>Spillover text line 2...</p>
        <p>Spillover text line 3...</p>
      </div>
    </section>

    <!-- 2. Overflow: Hidden -->
    <section class="demo-section">
      <h2>2. overflow: hidden</h2>
      <p>Content that exceeds the container is clipped and hidden from view.</p>
      <div class="box overflow-hidden">
        <p>This content is taller than the container's fixed height. With <code>overflow: hidden</code>, any text exceeding the container box is cut off and completely invisible.</p>
        <p>Hidden text line 2...</p>
        <p>Hidden text line 3...</p>
      </div>
    </section>

    <!-- 3. Overflow: Scroll -->
    <section class="demo-section">
      <h2>3. overflow: scroll</h2>
      <p>Scrollbars are always rendered to let users view clipped content.</p>
      <div class="box overflow-scroll">
        <p>This content is taller than the container's fixed height. With <code>overflow: scroll</code>, scrollbars are added to the container whether the content overflows or not, allowing the user to scroll.</p>
        <p>Scrollable line 2...</p>
        <p>Scrollable line 3...</p>
      </div>
    </section>

    <!-- 4. Overflow: Auto -->
    <section class="demo-section">
      <h2>4. overflow: auto</h2>
      <p>Scrollbars appear only when content exceeds the container boundaries.</p>
      <div class="box overflow-auto">
        <p>This content is taller than the container's fixed height. With <code>overflow: auto</code>, scrollbars appear dynamically only if the content overflows, keeping the UI clean.</p>
        <p>Auto-scroll line 2...</p>
        <p>Auto-scroll line 3...</p>
      </div>
    </section>

  </main>

  <footer>
    <p>&copy; 2026 Web Development Assignment — Overflow & Layout</p>
  </footer>

</body>
</html>
File 2: styles.css
CSS
/* Global Reset */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: system-ui, -apple-system, sans-serif;
  background-color: #f8fafc;
  color: #1e293b;
  line-height: 1.6;
  padding: 20px;
}

.page-header {
  text-align: center;
  margin-bottom: 30px;
}

.page-header h1 {
  color: #1e3a8a;
  margin-bottom: 5px;
}

.container {
  max-width: 650px;
  margin: 0 auto;
}

.demo-section {
  background-color: #ffffff;
  padding: 20px;
  border-radius: 8px;
  border: 1px solid #cbd5e1;
  margin-bottom: 20px;
}

.demo-section h2 {
  font-size: 1.15rem;
  color: #0f172a;
  margin-bottom: 4px;
}

.demo-section p {
  font-size: 0.9rem;
  color: #64748b;
  margin-bottom: 10px;
}

/* ==========================================================================
   FIXED-SIZE CONTAINER FOR OVERFLOW TESTING
   ========================================================================== */
.box {
  height: 100px; /* Fixed height forces overflow */
  border: 2px solid #2563eb;
  padding: 10px;
  background-color: #f1f5f9;
  border-radius: 6px;
}

/* Overflow Property Variations */
.overflow-visible {
  overflow: visible;
}

.overflow-hidden {
  overflow: hidden;
}

.overflow-scroll {
  overflow: scroll;
}

.overflow-auto {
  overflow: auto;
}

code {
  background-color: #e2e8f0;
  padding: 2px 5px;
  border-radius: 4px;
  font-size: 0.85rem;
  color: #0f172a;
}

footer {
  text-align: center;
  margin-top: 40px;
  color: #64748b;
  font-size: 0.9rem;
}
Summary of Overflow Values
visible: Default behavior. Overflowing content spills out of its container and can overlap adjacent elements.

hidden: Overflowing content is clipped at the container boundary and cannot be seen or scrolled to.

scroll: Clips overflowing content and forces horizontal and/or vertical scrollbars to display permanently.

auto: Clips overflowing content and adds scrollbars only when content actually exceeds the container dimensions.