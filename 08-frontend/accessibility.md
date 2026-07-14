# Accessibility (a11y) Interview Guide

## Overview
Web accessibility ensures that applications are usable by everyone, including people with visual, motor, auditory, or cognitive disabilities. With increasing legal requirements (ADA compliance, WCAG guidelines), companies prioritize engineers who bake accessibility into their components from day one.

## Interview Questions

### Question 1: What is the difference between semantic HTML and ARIA? When should you use ARIA attributes?
**Difficulty:** Easy | **Frequency:** High | **Companies:** Microsoft, Apple, Government/Edu tech

**Excellent Answer:**
- **Semantic HTML:** Elements that carry inherent meaning to browsers and assistive technologies (like `<button>`, `<nav>`, `<header>`, `<ul>`). Using them provides built-in accessibility, keyboard navigation, and structural meaning for free.
- **ARIA (Accessible Rich Internet Applications):** A set of attributes (`role`, `aria-*`) used to define semantics for elements that do not naturally possess them.
**The Golden Rule of ARIA:** *No ARIA is better than bad ARIA.*
You should only use ARIA when native HTML falls short. For example, if you build a custom dropdown widget using `<div>`s (because native `<select>` styling is limited), you must use ARIA (`role="combobox"`, `aria-expanded`, `aria-activedescendant`) and manage focus via JavaScript to communicate the widget's state to screen readers.

**Common Mistakes:**
- Using ARIA redundantly (e.g., `<nav role="navigation">`).
- Adding `role="button"` to a `<div>` without also implementing keyboard event handlers (Space/Enter) and focus management.

### Question 2: How do you ensure an application is navigable for keyboard-only users?
**Difficulty:** Medium | **Frequency:** Very High | **Companies:** Accessibility-focused agencies, SaaS companies

**Excellent Answer:**
Keyboard navigation is critical for users with motor disabilities and power users. I ensure a robust keyboard experience by:
1. **Using Semantic Elements:** Relying on native focusable elements like `<a>`, `<button>`, and `<input>`.
2. **Focus Management:** Ensuring custom components (like modals or sidebars) trap focus when open, meaning pressing `Tab` cycles through the modal and doesn't bleed out into the background page. When the modal closes, focus should return to the element that triggered it.
3. **Visible Focus Indicators:** Never setting `outline: none` without providing an alternative, accessible focus style (`:focus-visible`).
4. **Skip Links:** Providing a visually hidden "Skip to main content" link at the top of the DOM that becomes visible on focus, allowing users to bypass repetitive navigation.

**Common Mistakes:**
- Using `tabindex` with values greater than 0, which breaks the logical DOM order and confuses users.
- Failing to trap focus within custom dialogs/modals.

## Real-World Applications
- **Design Systems:** Ensuring every component in a company's UI library (buttons, tooltips, dialogs) is fully WCAG AA compliant out of the box, reducing the burden on product teams.
- **Complex Widgets:** Building accessible data tables, comboboxes, and drag-and-drop interfaces that accurately announce state changes to screen readers via live regions (`aria-live`).
- **Color and Contrast:** Collaborating with design teams to ensure UI colors meet the WCAG contrast ratio requirements (4.5:1 for normal text).

## Practice Problems

| Problem | Focus Area | Difficulty |
|---------|------------|------------|
| Build an accessible Custom Modal | Focus Trapping, ARIA roles, Keyboard events | Medium |
| Refactor a `div`-based custom button | Semantic HTML, Keyboard support, Tabindex | Easy |
| Implement a Toast notification system | `aria-live`, Screen reader announcements | Medium |
| Audit a provided webpage using a screen reader (NVDA/VoiceOver) | WCAG guidelines, Practical testing | Hard |

## Hiring Manager Perspective
"Accessibility shouldn't be a checklist completed at the end of a project; it must be part of the engineering culture. I look for candidates who proactively mention testing with VoiceOver or axe DevTools. If you build a custom component in an interview and don't mention how it handles keyboard focus, I will definitely dock points."

## AI Interview Coach

**Prompt for ChatGPT/Claude/Gemini:**
> "Act as an Accessibility Auditor for a web agency. Provide me with a snippet of React code for a custom interactive widget (like a tabbed interface) built entirely with non-semantic `div`s and no keyboard support. Ask me to refactor it to meet WCAG AA standards using proper HTML and ARIA, explaining my changes."
