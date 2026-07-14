# Behavioral Mock Interview

## Format/Duration/Difficulty
* **Format:** Behavioral / Past Experience
* **Duration:** 45 minutes
* **Difficulty:** Medium

## Round Setup
* **Role:** Software Engineer
* **Topic:** Conflict Resolution, Leadership, Failure
* **Question:** Tell me about a time you disagreed with a senior engineer or manager on a technical approach.

## The Interview

**Interviewer:** Welcome. Today we're going to focus on your past experiences. Can you tell me about a time you had a strong technical disagreement with a senior engineer or your manager? How did you handle it?

**Candidate:** Yes. In my last role, we were building a new microservice for user notifications. The senior engineer on the team wanted to use RabbitMQ because he had extensive experience with it. However, I had done some research and prototyped a solution using Kafka, which I believed was better suited for our specific use case, which required high throughput and message replay capabilities.

**Interviewer:** So how did you approach this disagreement?

**Candidate:** I didn't want it to just be an opinion battle. I used the STAR method in my head. The Situation was the architecture choice. The Task was to agree on the best tool. My Action was to write a short design doc comparing the two specifically against our product requirements. I didn't just list pros and cons; I benchmarked both with a load test simulating our expected traffic spikes.

**Interviewer:** How did the senior engineer react to that?

**Candidate:** Initially, he was skeptical. But when I presented the data in our weekly engineering sync, showing that Kafka handled the replay requirement natively whereas RabbitMQ would require us to build a custom dead-letter queue and replay mechanism, the conversation shifted. I made sure to acknowledge his valid points about RabbitMQ's simpler operational overhead. 

**Interviewer:** What was the final result?

**Candidate:** We ultimately chose Kafka. By focusing on objective data and product requirements rather than personal preference, we reached a consensus. The senior engineer actually became a strong advocate for it once he saw the benchmarks. The service was deployed and handled our Black Friday traffic without any dropped messages.

**Interviewer:** That's a great example. Follow-up: what would you have done if, despite your data, the manager stepped in and said, "We don't have time to learn Kafka, we are using RabbitMQ"?

**Candidate:** I would have committed to the decision ("disagree and commit"). If the business constraint is time-to-market and team familiarity, that's a valid leadership call. I would have documented the potential future risks (like building the custom replay logic) in an ADR (Architecture Decision Record) so we had a paper trail, and then I would have put my full effort into making the RabbitMQ implementation as robust as possible.

## Interviewer Feedback
* **Score:** 5/5 (Strong Hire)
* **Strengths:** 
    * Used data and prototyping to resolve a dispute instead of emotion.
    * Demonstrated empathy and respect for the senior engineer's viewpoint.
    * Excellent answer to the "disagree and commit" follow-up, showing maturity and understanding of business constraints.
* **Areas for Improvement:** 
    * None. This was a textbook perfect behavioral answer.

## Improved Answer

## Hiring Manager Notes
Candidate possesses high emotional intelligence and pragmatism. Understands the balance between technical excellence and business reality. A strong culture add.
