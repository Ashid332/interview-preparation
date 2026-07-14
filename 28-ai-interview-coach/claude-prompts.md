# Claude Prompts for Interview Coaching

Claude (especially Claude 3 Opus/Sonnet) excels at processing large amounts of text, making it perfect for deep system design evaluations, analyzing long code snippets, and nuanced behavioral feedback.

## 1. Comprehensive System Design Evaluation

**Initial Prompt:**
> "Act as a Principal Engineer at a high-growth startup. We are conducting a 1-hour System Design interview. The prompt is: 'Design a globally distributed rate limiter for a public API.'
> 
> I will provide my design in chunks. I want you to evaluate my design against the following rubric:
> 1. **Requirements Gathering:** Did I clarify scale, constraints, and use cases?
> 2. **High-Level Design:** Is the architecture sound?
> 3. **Deep Dive:** Did I effectively address bottlenecks, single points of failure, and data partitioning?
> 4. **Trade-offs:** Did I discuss the pros and cons of my technology choices?
> 5. **Communication:** Was my explanation clear and structured?
> 
> I will start by providing my requirements and high-level architecture. Please review and ask 2 tough follow-up questions about potential scaling issues."
> 
> [Insert your initial design notes here]

## 2. The STAR Story Optimizer

**Initial Prompt:**
> "I am preparing for behavioral interviews and have drafted a story about resolving a critical production outage. Here is my draft:
> 
> [Insert rough draft of story]
> 
> Please act as an expert executive communications coach. Analyze my story and rewrite it to perfectly align with the STAR (Situation, Task, Action, Result) format. 
> 
> Specific requirements:
> - Highlight the specific *actions I took* (use 'I', not 'We').
> - Quantify the results wherever possible (assume placeholders like [X]% if I forgot).
> - Make the narrative concise and impactful, aiming for a 2-minute spoken delivery.
> - Point out any red flags or negative framing in my original draft."

## 3. Take-Home Project Code Reviewer

**Initial Prompt:**
> "I have completed a take-home coding assignment for a Frontend Engineer role. The task was to build a real-time dashboard using React and WebSockets.
> 
> I am going to paste the contents of my 5 main files below. Act as a Staff Engineer reviewing this PR. 
> 
> Provide feedback on:
> 1. Architecture and state management.
> 2. Performance bottlenecks (e.g., unnecessary re-renders).
> 3. Security vulnerabilities.
> 4. Code maintainability and testing gaps.
> 
> [Paste File 1]
> [Paste File 2]
> ..."
