# Week 1 evidence

Keep this short. Bullet points, a small table and one diagram or code trace are enough. This is your checkpoint record, not an extra report. Replace the prompts as you work.

Name: Cristian 
Exact Unity version: 6000.3.26f1
Checkpoint commit / repository:
Current stage and anything unfinished:

## Initial prediction

Three observations the rival needs, including one it might not have:

Seeing a pickup across a gap proves / does not prove reachability because:

One question about NPC behaviour:

## One complete trace

Use one actual situation. Include the observation data, derived facts, selected task and reason, movement request/result, and how feedback affects a later decision. Identify the responsible code locations. A tiny state diagram can accompany this trace.

## Scenario record

| Scenario | Predicted result | Observed result and short evidence / remaining issue |
|---|---|---|
| Normal loop and restart |  | |
| Carrying cargo | Return To depot | It returns to the depot |
| Hidden / remembered pickup |  | |
| Target taken | It finds the next best target | It find the next closest target |
| Unreachable target | Ignore | It searches for other scrap and gives an error every 6 seconds because it tries to find a way to the unreachable scrap |
| No usable pickup | Explore | It goes around to every survey point in a loop |

Supplied test result, with any added tests identified:
Live walkthrough checked by / recording link if used:

## One correction and one independent check

The original weakness and why it happened:
What I changed and why it addresses the cause:
My counterexample or experiment: prediction, observed result, and one limitation:
It got stuck when there was a piece of scrap that was unobtainable. I fixed it by making a change in the DecisionPolicy and making it so a piece of scrap gets ignored if its blocked

## Collaboration and help

People I discussed or playtested with:
Code, sources or substantive tools/AI assistance I used, and how I verified them:
If unfinished: what works, exact reproduction steps, and the help I need:
