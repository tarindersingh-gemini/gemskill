# AI Innovate Hackathon

## Overview
This repository contains all templates, evaluation criteria, and agent instructions for the AI Innovate Hackathon at Gemini Private Ltd. These artifacts enable a scalable, automated, and fair evaluation process across the 6-week event.

---

## 📁 Repository Structure

```
ai-innovate/
├── README.md (this file)
├── templates/ (Participant submission templates)
│   ├── idea-submission-template.md
│   ├── midway-checkin-template.md
│   └── final-submission-template.md
├── .github/agents/ (GitHub Copilot automation agents)
│   ├── idea-validation-agent.md
│   ├── level1-proposal-review-agent.md
│   ├── final-submission-validation-agent.md
│   └── final-submission-level1-scoring-agent.md
└── evaluation/ (Human evaluation criteria and guides)
    ├── proposal-evaluation-criteria.md
    ├── proposal-level2-review-guide.md
    ├── midway-evaluation-criteria.md
    ├── final-submission-level2-mentor-shortlist-criteria.md
    └── final-submission-level3-judges-panel-rubric.md
```

---

## 🎯 Hackathon Timeline & Artifacts

### **Week 1-2: Stage 1: Marketing and Announcement**
No submission artifacts required.

---

### **Week 3: Stage 2 - Ideation**

#### 📋 For Participants:
- **Template:** [proposal-submission-template.md](templates/proposal-submission-template.md)
  - Comprehensive template for proposal submission
  - Includes: team info, problem statement, AI solution, resources, deliverables
  - Self validate using automated agent before submission.
  - Submission: Create PR to `submissions/proposals/`
  - File naming: `team-[team-name]-proposal.md`
#### 🤖 For Automation:
- **Agent:** [proposal-validation-agent.md](.github/agents/proposal-validation-agent.md)
  - Automated validation of proposal submissions
  - Checks: format, completeness, team info, placeholders, word counts, security
  - Actions: Pass/Fail/Manual Review Required

---

### **Week 3: Stage 3 - Proposal Review and Approval**

#### 📊 For Organizers & Mentors:
- **Criteria:** [proposal-evaluation-criteria.md](evaluation/proposal-evaluation-criteria.md)
  - Complete evaluation framework (100 points)
  - Weighted criteria: Innovation (25%), Feasibility (20%), Business Value (20%), Resources (15%), Team Capability (10%), Clarity (10%)
  - Approval thresholds and decision guidelines
  - Feedback templates for all outcomes

#### 🤖 For Automation (Level 1):
- **Agent:** [proposal-level1-review-agent.md](.github/agents/proposal-level1-review-agent.md)
  - Automated preliminary scoring (90 points excluding Team Capability)
  - Evaluates: Innovation, Feasibility, Business Value, Resources, Clarity
  - Provides: Auto-reject recommendations or forwards to manual review
  - Output: Detailed scoring report for mentor review

#### 👥 For Mentors (Level 2):
- **Guide:** [proposal-level2-review-guide.md](evaluation/proposal-level2-review-guide.md)
  - Comprehensive mentor manual review guide
  - Team Capability scoring rubric (10 points)
  - Validation of automated scores
  - Decision framework for approval/decline/waitlist
  - Feedback templates and best practices

---

### **Week 4: Stage 4 - Development Kickoff**
No submission artifacts required.
- Approved teams receive resources
- Communication channels established
- Development begins

---

### **Week 5: Stage 5 - Midway Check-in**

#### 📋 For Participants:
- **Template:** [midway-checkin-template.md](templates/midway-checkin-template.md)
  - Comprehensive progress reporting template
  - Sections: progress status, prototype status, challenges, risks, final plan
  - Support checkpoint (not a gate!)
  - Submission: Create PR to `submissions/midway/`
  - File naming: `team-[team-name]-midway-checkin.md`

#### 📊 For Mentors:
- **Criteria:** [midway-evaluation-criteria.md](evaluation/midway-evaluation-criteria.md)
  - Support-focused evaluation framework
  - Assessment categories: Progress Velocity (25%), Technical Approach (25%), Risk Management (25%), Resource Utilization (15%), Team Health (10%)
  - Status: On Track / Needs Support / At Risk
  - Intervention strategies and feedback templates
  - Focus: Enable success, not judge teams

---

### **Week 6: Stage 6 - Final Submission & Evaluation**

#### 📋 For Participants:
- **Template:** [final-submission-template.md](templates/final-submission-template.md)
  - Comprehensive final submission template
  - Sections: Project overview, working prototype, AI integration, technical architecture, demo materials, documentation, testing, impact, innovation, team reflection
  - Required deliverables: Working prototype, demo video, GitHub repo, documentation
  - Self validate via automated agent before submission.
  - Submission: Create PR to `submissions/final/`
  - File naming: `team-[team-name]-final-submission.md`

#### 🤖 For Automation (Validation):
- **Agent:** [final-validation-agent.md](.github/agents/final-validation-agent.md)
  - Automated validation of final submissions
  - Checks: format compliance, required deliverables, content completeness, link accessibility, security
  - Actions: Pass (proceed to scoring) / Fail (corrections required) / Manual Review
  - Triggers: On PR to `submissions/final/`

#### 🤖 For Automation (Level 1 Scoring):
- **Agent:** [final-level1-scoring-agent.md](.github/agents/final-level1-scoring-agent.md)
  - Automated preliminary scoring (50-60 points of 100)
  - Evaluates: Technical Execution (partial), AI Integration (partial), Completeness, Documentation
  - Provides: Automated scores + flags for manual review
  - Output: Preliminary scoring report for mentor evaluation

#### 👥 For Mentors (Level 2 Evaluation):
- **Criteria:** [final-level2-mentor-shortlist-criteria.md](evaluation/final-level2-mentor-shortlist-criteria.md)
  - Complete evaluation framework (100 points)
  - Criteria: Technical Execution (25), AI Integration (20), Completeness (15), Impact (15), Documentation (15), Innovation (10)
  - Process: Review, validate automated scores, complete manual scoring
  - Objective: Shortlist top 10 submissions for judges
  - Feedback templates for all teams

#### ⚖️ For Judges (Level 3 Final Selection):
- **Rubric:** [final-level3-judges-panel-rubric.md](evaluation/final-level3-judges-panel-rubric.md)
  - Enhanced evaluation framework (150 points)
  - Criteria: Innovation & Technical Excellence (45), Impact & Business Value (37.5), Execution Quality (30), Presentation (22.5), Future Potential (15)
  - Detailed judging process and voting methods
  - Winner selection and special recognition awards
  - Award: 1st place (4 iPads), 2nd-10th (Toasters)

---

## 🔄 Evaluation Flow Summary

### Stage 2: Idea Submission
```
Participant Submission
      ↓
🤖 Automated Validation Agent
      ↓
   Pass / Fail / Manual Review
      ↓
[If Pass] → Forward to Stage 3
```

### Stage 3: Proposal Review
```
Validated Idea Submission
      ↓
🤖 Level 1 Automated Review Agent (90 pts)
      ↓
Auto-Reject Recommendation / Forward to Manual
      ↓
👥 Level 2 Mentor Manual Review (+10 pts Team Capability)
      ↓
Approve / Decline / Waitlist
      ↓
[If Approved] → Provide Resources, Start Development
```

### Stage 5: Midway Check-in
```
Team Midway Submission
      ↓
👥 Mentor Review & Assessment
      ↓
Status: On Track / Needs Support / At Risk
      ↓
Provide Guidance, Support, Scope Adjustment
      ↓
Continue to Final Submission
```

### Stage 6: Final Evaluation
```
Team Final Submission
      ↓
🤖 Validation Agent
      ↓
[If Pass]
      ↓
🤖 Level 1 Automated Scoring Agent (50-60 pts)
      ↓
👥 Level 2 Mentor Evaluation (100 pts total)
      ↓
Shortlist Top 10
      ↓
⚖️ Level 3 Judges Panel (150 pts)
      ↓
Select Winner & Runners-Up
      ↓
🏆 Award Ceremony & Recognition
```

---

## 📊 Scoring Summary

### Stage 3: Proposal Evaluation (100 points)
| Criterion | Points | Evaluator |
|-----------|--------|-----------|
| Innovation & Creativity | 25 | Automated + Manual |
| Technical Feasibility | 20 | Automated + Manual |
| Business Value & Impact | 20 | Automated + Manual |
| Resource Reasonableness | 15 | Automated + Manual |
| Team Capability | 10 | Manual Only |
| Clarity & Completeness | 10 | Automated |

**Approval Threshold:** ≥60 points

---

### Stage 6 Level 2: Mentor Evaluation (100 points)
| Criterion | Points | Evaluator |
|-----------|--------|-----------|
| Technical Execution & Quality | 25 | Mentor (Automated assists) |
| AI Integration & Innovation | 20 | Mentor (Automated assists) |
| Completeness & Polish | 15 | Automated + Mentor |
| Impact & Value | 15 | Mentor |
| Documentation & Presentation | 15 | Automated + Mentor |
| Innovation & Uniqueness | 10 | Mentor |

**Top 10 Threshold:** ≥65 points

---

### Stage 6 Level 3: Judges Panel (150 points)
| Criterion | Points |
|-----------|--------|
| Innovation & Technical Excellence | 45 |
| Impact & Business Value | 37.5 |
| Execution Quality & Completeness | 30 |
| Presentation & Communication | 22.5 |
| Future Potential & Strategic Fit | 15 |

**Winner Selection:** Highest score + consensus


## 🚀 Quick Start Guides

### For Participants

**Stage 2 (Week 3):**
1. Form team (max 4 members)
2. Download: `templates/proposal-submission-template.md`
3. Complete all sections (remove placeholders!)
4. Self validate via automated agent `.github/agents/proposal-validation-agent.md`
5. Submit PR to `submissions/ideas/<team-name>-proposal.md`
6. Wait for automated validation + mentor review

**Stage 5 (Week 5):**
1. Download: `templates/midway-checkin-template.md`
2. Honestly report progress and challenges
3. Submit PR to `submissions/midway/<team-name>-midway-checkin.md`
4. Schedule call with mentor if flagged

**Stage 6 (Week 6):**
1. Download: `templates/final-submission-template.md`
2. Complete comprehensive submission
3. Ensure demo video and GitHub repo are accessible
4. Submit PR to `submissions/final/<team-name>-final-submission.md`
5. Wait for evaluation results

---

### For Organizers

**Setup Phase:**
1. Configure GitHub Copilot agents in repository
2. Set up directory structure: `submissions/proposals/`, `submissions/midway/`, `submissions/final/`
3. Brief mentors on evaluation process
4. Recruit and brief judges
5. Set up communication channels

**Stage 2-3:**
1. Deploy idea validation agent
2. Monitor submissions
3. Coordinate mentor reviews
4. Approve proposals and allocate resources

**Stage 5:**
1. Monitor midway submissions
2. Coordinate mentor support interventions
3. Adjust resources as needed

**Stage 6:**
1. Deploy validation and scoring agents
2. Coordinate mentor evaluations
3. Prepare top 10 package for judges
4. Facilitate judges panel
5. Organize award ceremony

---

### For Mentors

**Stage 3:**
1. Review: `evaluation/proposal-evaluation-criteria.md`
2. Review: `evaluation/proposal-level2-review-guide.md`
3. Conduct calibration with co-mentor
4. Review automated L1 scores
5. Complete Team Capability scoring
6. Validate/adjust automated scores
7. Make approval decisions
8. Provide feedback to all teams

**Stage 5:**
1. Review: `evaluation/midway-evaluation-criteria.md`
2. Read midway submissions
3. Assess: On Track / Needs Support / At Risk
4. Provide guidance and interventions
5. Help teams scope appropriately

**Stage 6:**
1. Review: `evaluation/final-level2-mentor-shortlist-criteria.md`
2. Watch demo videos
3. Test prototypes
4. Complete full evaluation (100 pts)
5. Shortlist top 10
6. Provide feedback to all teams

---

### For Judges

**Preparation:**
1. Review: `evaluation/stage6-level3-judges-panel-rubric.md`
2. Receive top 10 submission packages
3. Review all submissions individually
4. Watch demo videos
5. Test prototypes if possible
6. Complete individual scoring

**Judging Session:**
1. Attend judges panel meeting
2. Discuss all top 10 submissions
3. Score using 150-point rubric
4. Deliberate and reach consensus
5. Select winner and runners-up
6. Identify special recognition awards

---

## 📞 Support & Questions

- Mentor contact: [Your assigned mentor]
- General questions: #ai-innovate-hackathon channel
- Organizers: [Organizer email]
