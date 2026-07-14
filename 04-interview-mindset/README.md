# Interview Mindset and Practical Behavior

An engineering interview is as much about your behavior and communication as it is about your technical competence. This section outlines practical strategies for navigating the interview environment effectively.

## 1. Clarifying Requirements
Never write code immediately. A vague prompt is a deliberate test of your ability to define scope.
* **Define Inputs/Outputs**: Explicitly state the expected data types and structures.
* **Identify Constraints**: Ask about dataset size, memory limits, and time complexity requirements.
* **Establish Edge Cases**: Check for empty inputs, negative numbers, extreme values, or invalid data.

## 2. Thinking Aloud
Silence is your enemy. The interviewer needs to understand your thought process to evaluate you or provide hints.
* **Narrate Your Logic**: "I'm considering a hash map here because we need O(1) lookups..."
* **State Assumptions**: "Assuming the array can contain duplicates..."
* **Write Pseudo-code**: Outline the algorithm structure using comments before implementing the actual logic.

## 3. Communicating Trade-offs
Engineers make decisions based on trade-offs. Show that you can evaluate multiple approaches.
* **Time vs. Space**: "We could sort this in O(N log N) with O(1) space, or use a hash set in O(N) time but O(N) space. Given the memory constraints, I will choose the sorting approach."
* **Readability vs. Micro-optimization**: Acknowledge when a slightly less optimal but highly readable approach might be preferred in production.

## 4. Handling "I Don't Know"
Hitting a mental block is common. How you react is what matters.
* **Do not bluff**: Interviewers will immediately recognize if you are guessing wildly.
* **Pivot to what you know**: "I'm not familiar with the specific syntax for a min-heap in Python off the top of my head, but logically we need a priority queue. I'll abstract this as `queue.push()` for now."
* **Work from first principles**: Try the brute-force approach first to get something working, then optimize.

## 5. Recovering from Mistakes
Mistakes happen. Your recovery demonstrates resilience and debugging skills.
* **Accept corrections gracefully**: If the interviewer points out a bug, immediately stop, review the specific line, and say, "Good catch. Let's trace through what happens at that index."
* **Dry-run your code**: Always manually trace your implementation with a small example before declaring you are finished. This catches off-by-one errors and logical flaws early.

## 6. Managing Time
Interviews are strictly time-boxed (usually 45-60 minutes).
* **Time Check**: Keep a mental (or physical) note of the time. If 15 minutes have passed and you are still discussing the optimal approach, switch to writing the brute-force solution.
* **Pacing**: Dedicate 5-10 minutes to clarification/design, 20-25 minutes to coding, and 5-10 minutes to testing/dry-running.

## 7. Asking Questions
The "Do you have any questions for me?" segment is an opportunity to show genuine interest.
* **Avoid generic questions**: Skip "What is the culture like?"
* **Focus on engineering realities**: "How does your team handle tech debt versus feature delivery?", "Can you walk me through the typical deployment pipeline for a service here?", or "What was the most challenging production incident the team faced recently?"
