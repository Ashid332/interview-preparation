# Software Engineer Mock Interview

## Format/Duration/Difficulty
* **Format:** Coding / Algorithms
* **Duration:** 45 minutes
* **Difficulty:** Medium

## Round Setup
* **Role:** Backend Software Engineer
* **Topic:** Data Structures and Algorithms (Arrays/Hash Maps)
* **Question:** Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to `target`. You may assume that each input would have exactly one solution, and you may not use the same element twice. You can return the answer in any order.

## The Interview

**Interviewer:** Hi, welcome. Today we have a coding problem. Have you read the prompt? Given an array of integers and a target sum, find the indices of two numbers that add up to the target.

**Candidate:** Yes, I've read it. So, to clarify, there will always be exactly one solution?

**Interviewer:** Correct.

**Candidate:** And the array can contain negative numbers?

**Interviewer:** Yes, it can.

**Candidate:** Okay. The most straightforward way would be to check every pair of numbers. I could use two nested loops. The outer loop picks a number, and the inner loop looks for the remaining value. That would be O(n^2) time complexity and O(1) space.

**Interviewer:** That's a valid approach. Can we do better in terms of time complexity?

**Candidate:** Yes. To optimize, I can use a hash map to store the numbers I've seen so far along with their indices. As I iterate through the array, for each number, I calculate the `complement` which is `target - current_number`. If the `complement` is already in my hash map, I've found my pair. 

**Interviewer:** Sounds good. Let's see the code for that.

**Candidate:** 
```python
def two_sum(nums, target):
    seen = {}
    for i, num in enumerate(nums):
        complement = target - num
        if complement in seen:
            return [seen[complement], i]
        seen[num] = i
    return []
```

**Interviewer:** What is the time and space complexity of this approach?

**Candidate:** The time complexity is O(n) because we traverse the list containing n elements exactly once. Each lookup in the table costs only O(1) time. The space complexity is also O(n) because the hash map stores at most n elements.

**Interviewer:** Looks solid. What if the array is already sorted?

**Candidate:** If it's sorted, we could use a two-pointer approach. One pointer at the beginning, one at the end. We sum them up. If the sum is greater than the target, we decrement the right pointer. If it's less, we increment the left pointer. That would take O(n) time and O(1) space. But since we need to return indices, sorting the array first would mess up the original indices, so we'd have to store them, which brings space back to O(n). But if we just needed the numbers, two pointers would be O(1) space.

**Interviewer:** Great observation. I'm happy with this.

## Interviewer Feedback
* **Score:** 4/5 (Strong Hire)
* **Strengths:** 
    * Clarified requirements before starting.
    * Stated the brute force solution first to establish a baseline.
    * Successfully optimized to O(n) using a hash map.
    * Handled the follow-up question well, showing depth of knowledge.
* **Areas for Improvement:** 
    * Could have explicitly walked through an example using the optimal code before declaring it finished to catch any silly syntax errors, though none were present here.

## Improved Answer
The candidate's answer was already excellent. A slight improvement in communication would be walking through a dry run:
"Let's trace this with `nums = [2, 7, 11, 15]` and `target = 9`.
- First iteration: `num = 2`, `i = 0`. `complement = 7`. 7 not in `seen`. `seen[2] = 0`.
- Second iteration: `num = 7`, `i = 1`. `complement = 2`. 2 is in `seen`. We return `[seen[2], 1]`, which is `[0, 1]`. Correct."

## Hiring Manager Notes
Candidate demonstrated clear communication and strong fundamental knowledge of data structures. They didn't jump straight into coding but thought through the problem and trade-offs. Proceed to next round.
