

# Divi-Code-Module---F.A.Q-Free-to-use
Divi Code module for purposes such F.A.Q or any clickable content you need to add for revieling information in a nice way.

![GIF Preview](https://github.com/danielfrrokaj/Divi-Code-Module---F.A.Q-Free-to-use/blob/main/assets/demo.gif?raw=true)


# Divi Accordion Component

This is a customizable and reusable accordion component designed for the **Divi Theme**. It allows you to create collapsible sections with smooth animations and hover effects. The component is built using **HTML**, **CSS**, and **JavaScript**, making it easy to integrate into any Divi project.

---

## Features

- **Smooth Slide-Down Animation**: The accordion content slides down smoothly when opened.
- **Hover Effects**: The header changes background color and text color on hover.
- **Arrow Indicators**: Arrows indicate the open/close state of each accordion item.
- **Single Open Item**: Only one accordion item can be open at a time.
- **Customizable Styles**: Easily modify colors, fonts, and spacing to match your theme.

---

## How to Use

### 1. Copy & Paste this code into a Code Module

```html
<div class="accordion">
  <div class="accordion-item">
    <div class="accordion-header">
      <p>Header</p>
      <span class="arrow">▼</span>
    </div>
    <div class="accordion-content">
      <p>Paragraph</p>
    </div>
  </div>

  <div class="accordion-item">
    <div class="accordion-header">
      <p>Header</p>
      <span class="arrow">▼</span>
    </div>
    <div class="accordion-content">
      <p>Paragraph</p>
    </div>
  </div>

  <div class="accordion-item">
    <div class="accordion-header">
      <p>Header</p>
      <span class="arrow">▼</span>
    </div>
    <div class="accordion-content">
      <p>Paragraph</p>
    </div>
  </div>

  <div class="accordion-item">
    <div class="accordion-header">
      <p>Header</p>
      <span class="arrow">▼</span>
    </div>
    <div class="accordion-content">
      <p>Paragraph</p>
    </div>
  </div>

  <div class="accordion-item">
    <div class="accordion-header">
      <p>Header</p>
      <span class="arrow">▼</span>
    </div>
    <div class="accordion-content">
      <p>Paragraph</p>
    </div>
  </div>
</div>

<style>
.accordion-item {
  text-align: center;
}

.accordion-header {
  display: flex;
  justify-content: space-between; /* Push the arrow to the right */
  align-items: center; /* Center items vertically */
  padding: 15px;
  cursor: pointer;
  font-size: 18px;
  font-weight: bold;
}

.accordion-header p {
  margin: 0; /* Remove default margin */
  flex-grow: 1; /* Allow the text to take up remaining space */
  text-align: center; /* Center the text */
  color: #0077b6
}

.accordion-header:hover {
  background-color: #0077b6;
  color: white;
	border-radius: 20px;
}
.accordion-header:hover p {
  color: white; /* Ensure the p tag inside the header also turns white on hover */
}

.accordion-content {
  max-height: 0; /* Start with zero height */
  overflow: hidden; /* Hide overflow content */
  margin-bottom: 10px; /* Padding for content */
  
  transition: max-height 0.3s ease-out, padding 0.3s ease-out; /* Smooth transition */
}

.accordion-content.open {
  max-height: 200px; /* Adjust this value based on your content height */
  padding: 15px; /* Add padding when open */
}

.accordion-content p {
  margin: 0;
}

.arrow {
  font-size: 16px;
  margin-left: 10px; /* Add some spacing between the heading and the arrow */
  transition: transform 0.3s ease-out; /* Smooth arrow rotation */
  color: #0077b6;
}

.arrow.open {
  transform: rotate(180deg); /* Rotate arrow when open */
}
}
</style>
<script>
document.addEventListener('DOMContentLoaded', function () {
  const headers = document.querySelectorAll('.accordion-header');

  headers.forEach(header => {
    header.addEventListener('click', function () {
      const content = this.nextElementSibling;
      const arrow = this.querySelector('.arrow');

      // Close all other open dropdowns
      headers.forEach(otherHeader => {
        if (otherHeader !== header) {
          const otherContent = otherHeader.nextElementSibling;
          const otherArrow = otherHeader.querySelector('.arrow');
          otherContent.classList.remove('open');
          otherArrow.classList.remove('open');
        }
      });

      // Toggle the clicked dropdown
      content.classList.toggle('open');
      arrow.classList.toggle('open');
    });
  });
});
</script>
