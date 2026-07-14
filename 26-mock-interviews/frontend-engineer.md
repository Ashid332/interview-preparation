# Frontend Engineer Mock Interview

## Format/Duration/Difficulty
* **Format:** UI Component Design & Implementation
* **Duration:** 45 minutes
* **Difficulty:** Medium

## Round Setup
* **Role:** Frontend Engineer
* **Topic:** React Component Implementation
* **Question:** Build a reusable, accessible "Tabs" component in React. It should take an array of tab items (label and content) and manage its own active state.

## The Interview

**Interviewer:** Let's build a Tabs component. It's a common UI pattern. How would you approach this in React?

**Candidate:** First, I'd define the API. I'd expect an array of objects, something like `[{ id: 1, label: 'Tab 1', content: <MyContent /> }]`. The component will need to manage which tab is currently active using `useState`.

**Interviewer:** Make sense. Let's write the initial structure.

**Candidate:**
```jsx
import React, { useState } from 'react';

const Tabs = ({ items }) => {
  const [activeId, setActiveId] = useState(items[0]?.id);

  return (
    <div className="tabs-container">
      <div className="tab-headers">
        {items.map(item => (
          <button 
            key={item.id}
            onClick={() => setActiveId(item.id)}
            className={activeId === item.id ? 'active' : ''}
          >
            {item.label}
          </button>
        ))}
      </div>
      <div className="tab-content">
        {items.find(item => item.id === activeId)?.content}
      </div>
    </div>
  );
};
```

**Interviewer:** This works fundamentally. What about accessibility? How can we make this usable for keyboard users and screen readers?

**Candidate:** Good point. We should add ARIA attributes. The container for the buttons should be `role="tablist"`. The buttons themselves should be `role="tab"`, and the content area `role="tabpanel"`. We also need `aria-selected` on the active tab and `aria-controls` to link the tab to its panel. Also, keyboard navigation usually allows using arrow keys to switch tabs.

**Interviewer:** Let's implement the ARIA attributes first.

**Candidate:**
```jsx
// inside the map for buttons:
<button 
  key={item.id}
  role="tab"
  aria-selected={activeId === item.id}
  aria-controls={`panel-${item.id}`}
  id={`tab-${item.id}`}
  onClick={() => setActiveId(item.id)}
>
  {item.label}
</button>

// inside the tab content:
<div 
  role="tabpanel" 
  id={`panel-${activeId}`} 
  aria-labelledby={`tab-${activeId}`}
>
  {items.find(item => item.id === activeId)?.content}
</div>
```

**Interviewer:** Much better. What if a user wants to control the active tab from a parent component?

**Candidate:** Ah, a controlled component pattern. We'd need to accept `activeTab` and `onChange` props. We can check if `activeTab` is provided to determine if we operate in controlled or uncontrolled mode.

**Interviewer:** Great. We can stop here.

## Interviewer Feedback
* **Score:** 3.5/5 (Hire)
* **Strengths:** 
    * Quickly implemented a working solution.
    * Understood the component API design.
    * Knew the relevant ARIA attributes for accessibility.
* **Areas for Improvement:** 
    * Keyboard navigation (arrow keys) wasn't implemented, only mentioned.
    * Didn't handle edge cases initially (e.g., empty items array).

## Improved Answer
For a complete accessible implementation, keyboard events should be added:
```javascript
const handleKeyDown = (e, index) => {
  if (e.key === 'ArrowRight') {
    const nextIndex = (index + 1) % items.length;
    setActiveId(items[nextIndex].id);
    // would need refs to focus the new button
  } else if (e.key === 'ArrowLeft') {
    const prevIndex = (index - 1 + items.length) % items.length;
    setActiveId(items[prevIndex].id);
  }
};
```

## Hiring Manager Notes
Good practical React skills. Showed awareness of accessibility and advanced React patterns (controlled vs uncontrolled). Solid hire for a mid-level frontend role.
