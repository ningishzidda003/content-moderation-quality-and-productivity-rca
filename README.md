# content-moderation-quality-and-productivity-rca

## Assumptions & Limitations 
This analysis is based on simulated operational data and assumes stable staffing levels and queue allocations during the observation period. Because no production environment was available, the findings focus on process and quality indicators rather than exact operational predictions.

## Executive Summary
Productivity decreased by approximately 9% over a 2-week period, with average handling time increasing from 23 seconds to 35 seconds. Quality dropped from 93% to 84%, primarily due to increased case complexity and misalignments of agent and auditor calibrations following a policy update.

## Problem Statement
A significant drop in productivity across the team was observed following the implementation of updated content moderation guidelines that included hate speech, insults, and negative stereotypes. Agents needed additional time to interpret the new rules for edge cases that intensified with the new changes, resulting in increased handling times, higher escalation rates, and a noticeable backlog of requests. Quality scores also declined amid discord between agents’ and auditors’ thought processes.

## Impact
Metrics affected:\
• Accuracy\
• Handling Time\
• Productivity\
• Escalations

## KPI Analysis
Metric | Before | After\
Cases/day | 1100 | 1000\
Avg HT | 23.3 | 34.7\
Accuracy | 93.1 | 84.3\
Escalations (daily avg) | 25 | 41

## Event Timeline
Date | Event | Action | Owner\
Day 1 | New policy guidelines released | Team training session conducted | QA Lead\
Day 3-5 | Increase in escalated cases reported	| QA team began tracking | QA Lead\
Day 7 | AHT metrics begin rising | Monitored dashboards; flagged issue | Team Lead\
Day 10 | Quality drops below 90% | Weekly performance review called | Operations Manager\
Day 12 | RCA initiated | Data gathering & analysis started | Analyst\
Day 14 | Preliminary findings shared | Recommendations presented to QA/Operations | Analyst

## Root Cause Analysis
Why did productivity decrease and quality drop?
1. Why agents spent significantly more time per case, but their decisions were frequently flagged as incorrect by auditors, causing frustration and retrials?
2. Why did the new policy on hate speech and negative stereotyping introduce highly subjective thresholds (e.g., differentiating contextual insults from serious violations), leading to inconsistent interpretations?
3.  Why were agent and auditor interpretations misaligned because the calibration session largely covered clear, “black and white” examples, but lacked sufficient practice on the new “gray area” borderline cases?
4. Why were the calibration materials prepared under the client’s strict deadline, leaving the quality assurance team with limited time to gather a diverse set of real-world examples for the workshop?
5. Why, without a phased warm-up period, did agents apply stricter or more lenient internal heuristics than auditors, which only became visible after quality assurance scores declined a week later?

### Root Cause:
Calibrations that were not sufficiently explained before launch to quality assurance agents and auditors, combined with the lack of real-time reference tools, led to decision fatigue, slower decision-making, and a temporary decrease in alignment and quality.

## Contributing Factors
Process -> The policy was implemented all at once, without a phased “shadow” period for agents to gradually adjust.\
People -> Natural variance in risk tolerance across agents; auditors applied stricter academic standards compared to operational agents.\
Tools -> No quick reference pop-up in the tool for new definitions was available; agents had to rely on memory or external documents.\
Data -> Escalation and quality trends were reviewed only weekly; misalignment was not detected early enough.\
External Factors -> Strict implementation deadline, driven by the client, limited preparation time for comprehensive training materials.

## Corrective Actions
Action | Owner | Due Date\
Specific recalibration sessions covering the top 20 most frequently reported phrases/terms in the new policy | QA Lead | Week 1\
Update your internal knowledge base (KB) with a simple decision tree logic for subjective insults and stereotypes | QA | Week 1\
Implement a daily 15-minute meeting in the middle of the workday for agents to ask questions about ambiguous situations they encountered | Team Lead | Day 2\
Meetings to align auditor calibration criteria with operational realities (or vice versa) to ensure consistency during the moderation process | Operations Manager | Week 2\
Update the daily performance dashboard to include a “Calibration Discrepancy Rate” (agent vs. auditor alerts) | Analyst | Week 2\
Create quick quizzes at the start of the program to check agent status | QA | Week 1

## Expected Outcome
Restore quality to 93% and reduce average handling time to under 28 seconds within 3 weeks through better agent-auditor alignment, practical decision-making guides, and daily feedback loops. Also, establish a protocol for future policy updates to prevent similar declines.
