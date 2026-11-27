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

In the f4 Scene, the Ai will first make an observation of where the nearest pickups are. It will then infer facts from the observation it will ignore the closest pickup as it is invisible and pick the second closest pickup as the best candidate. It will then Choose to go towards the pickup and will request the navigator script to make the navmesh agent move towards the pickup, after picking it up it will return to the depot, once returned to the depot it will observe and infer again. This time there are no viable candidates so it will survey until the remaining pickup is within line of sight. It will then go to it, pick it up and return to the depot.

## Scenario record

| Scenario | Predicted result | Observed result and short evidence / remaining issue |
|---|---|---|
| Normal loop and restart | Collects and returns | The AI will go to the closest scrap it can see and pick it up, if it is holding a pickup it will return to the depot to drop it off, if the ai can not see a pickup it will survey the map |
| Carrying cargo | Return To depot | The ai returns to the depot to  |
| Hidden / remembered pickup | Ignores it | The AI will survey the map until the hidden pickup is in view and the it will pick it up |
| Target taken | It finds the next best target | It find the next closest target |
| Unreachable target | Ignore | It searches for other scrap and gives an error every 6 seconds because it tries to find a way to the unreachable scrap |
| No usable pickup | Explore | It goes around to every survey point in a loop |

Supplied test result, with any added tests identified:
Live walkthrough checked by / recording link if used:

## One correction and one independent check


It got stuck when there was a piece of scrap that was unobtainable. I fixed it by making a change in the DecisionPolicy and making it so a piece of scrap gets ignored if its blocked

## Collaboration and help

People I discussed or playtested with:
Code, sources or substantive tools/AI assistance I used, and how I verified them:
If unfinished: what works, exact reproduction steps, and the help I need:
