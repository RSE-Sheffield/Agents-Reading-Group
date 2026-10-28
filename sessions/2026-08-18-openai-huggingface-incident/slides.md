---
marp: true
theme: uos
paginate: true
---

<style>
/* Screenshot slides: heading across the top, picture on the left, notes beside it */
/* Text slides start at the top, as in the original */
section.top, section.shot {
  align-content: start;
}
section.top h2 {
  margin-top: 0.4em;
}
section.shot {
  display: block;
  padding: 44px 64px 40px;
}
section.shot h2 {
  font-size: 34px;
  line-height: 1.3;
  margin: 0 0 18px;
}
section.shot p {
  font-size: 25px;
  line-height: 1.45;
  margin: 0 0 1em;
  color: #444;
}
section.shot img {
  float: left;
  width: 70%;
  margin: 0 36px 0 0;
}
</style>

<!-- _class: lead -->

![width:220px](images/UOSLogo_Primary_White_RGB.png)

# OpenAI HuggingFace

18/08/2026
Edwin Brown
Breakdown of <https://www.youtube.com/watch?v=87DyyMV0kCY>

---

<!-- _class: small top -->

<style scoped>
p { font-size: 22px; color: #444; }
</style>

## What happened?

On July 16th, HuggingFace disclosed an attack on their systems by some AI agents: <https://huggingface.co/blog/security-incident-july-2026>

Meanwhile, July 8th -19th, OpenAI are internally fighting an attack on their own infrastructure.

On July 21st July, OpenAI realise it is there model responsible : <https://openai.com/index/hugging-face-model-evaluation-security-incident/>

On 27th July, we had a [technical debrief](https://huggingface.co/blog/agent-intrusion-technical-timeline) from huggingface about the incident from their perspective

On 7th August, a presentation was made from [openAI about the incident at blackhat](https://www.youtube.com/watch?v=87DyyMV0kCY) from their perspective

---

<!-- _class: top -->

## Timeline

Timeline : <https://simonwillison.net/2026/Aug/7/openai-timeline/>

---

<!-- _class: lead -->

# Setup

---

<!-- _class: shot -->

<style scoped>
img { width: 76%; }
</style>

## Research Infrastructure

![](images/research-infrastructure.png)

---

<!-- _class: shot -->

## Problem started back during training. . . (May)

![](images/training-impossible-task.png)

Forced to try to access the internet due to impossible task

---

<!-- _class: shot -->

## Realises it has write access to package manager leading to communication with other agents as they try to reason through their tasks

![](images/package-manager-message-board.png)

---

<!-- _class: shot -->

## Then we have the first exploit found -> They now have access to the internet and crucially it has been written to the message board!

![](images/ssrf-internet-access.png)

This all happens undetected

---

<!-- _class: shot -->

## Now, fast forward to June 11th, OpenAI start training a new experimental model and later finds a RCE exploit

![](images/artifactory-rce-agent-thinking.png)

What alignment had this model undergone at this point? - They keep saying ‘highly persistent’

---

<!-- _class: shot -->

## Agent activity causes an outage and OpenAI become aware of the incident

![](images/artifactory-outage.png)

---

<!-- _class: lead -->

# The actual incident

---

<!-- _class: shot -->

## Agents quickly re-establish communication via writing directory names and start working on ExploitGym tasks

![](images/main-incident-exploitgym.png)

---

<!-- _class: shot -->

<style scoped>
p:first-of-type img { width: 50%; margin-right: 24px; }
p:last-of-type img { float: right; width: 46%; margin: 0; }
</style>

## Message board is incredible. . .

![](images/inter-agent-collaboration.png)

Happy to help others at first even if it doesn’t benefit their task. Also, paranoid and tensions take place (overwriting each other files, etc.)

![](images/agent-thinking-help-peer.png)

---

<!-- _class: shot -->

<style scoped>
img { width: 76%; }
</style>

## But most importantly, they are keen to share exploits

![](images/collective-intelligence.png)

---

<!-- _class: shot -->

## And Finally, the motivation. .

---

<!-- _class: shot -->

## And now the actual exploits -> One on OpenAI infrastructure and one on Huggingface infrastructure

![](images/openai-infrastructure-attack.png)

---

<!-- _class: shot -->

## First they get remote code execution in Artifactory

![](images/artifactory-rubygems-rce.png)

Complicated attack designed to get admin token access to the Artifactory.

Required understanding of RubyGems and Artifactory and joining them together.

---

<!-- _class: shot -->

## Then they escalate privileges throughout the entire container. Ends up with admin cluster control.

![](images/openai-infrastructure-privesc.png)

Not clear to me why they felt the need to do this? Was it required for the huggingface attack?

---

<!-- _class: shot -->

## Now the huggingface attack

![](images/huggingface-infrastructure-attack.png)

Detailed write up [here](https://huggingface.co/blog/agent-intrusion-technical-timeline).

---

<!-- _class: lead -->

# Response

---

<!-- _class: shot -->

## First, huggingface release a blog saying they’ve been attacked and OpenAI ask whether they’re impacted by this. . which is very funny

![](images/reach-out-to-hugging-face.png)

---

<!-- _class: shot -->

## Then OpenAI find they’ve been exploited and start responding. .

![](images/initial-incident-detection.png)

Part of that response was to contact HF saying we’ve seen your secrets leaked in our attack, please revoke. .

---

<!-- _class: shot -->

## And then the penny drops. . (July 20th)

![](images/incident-detection-july-20.png)

But HF reply saying we’ve already revoked because they were involved in the attack we reported last week. . .

This is when they realise its the same attack

---

<!-- _class: top -->

## To Conclude

1. OpenAI are validating on cyber-gmn a model and give it an impossible task
2. To solve task, model decides it would be beneficial to find answers online
3. It breaks out of its sandbox using previously left messages from other agentic runs a month previously
4. Hacks into HuggingFace to try and get access to the test solutions of the benchmark it is trying to beat.

---

<!-- _class: lead -->

# Their Final Thoughts

---

<!-- _class: shot -->

<style scoped>
img { width: 76%; }
</style>

## They (unsurprisingly) argue that agentic defence has to be ramped up

![](images/agentic-sdlc-defense.png)

---

<!-- _class: top -->

## Discuss. . .

- What does this mean for cyber security?
