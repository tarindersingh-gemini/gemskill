

# Agent Purpose
This GitHub Copilot agent performs automated validation of idea submissions during Stage 2 (Ideation) of the AI Innovate Hackathon. It checks for format compliance, completeness, clarity, and potential duplicates before manual mentor review.

## Validation Criteria

### 1. Format Compliance (Pass/Fail)

**Check: File Naming Convention**
- File must be named: `team-[team-name]-proposal.md`
- Pattern: `^team-[\w-]+-proposal\.md$`
- ❌ FAIL if: Incorrect naming format
- Action: Leave comment requesting rename

**Check: Markdown Structure**
- All required section headers must be present:
  - Team Information
  - Problem Statement
  - Proposed AI Solution
  - Technical Approach
  - Resource Requirements
  - Planned Deliverables
  - Innovation & Differentiation
  - Team Readiness
- ❌ FAIL if: Any required section is missing
- Action: Leave comment listing missing sections

### 2. Team Information Validation (Pass/Fail)

**Check: Team Size**
- Minimum: 2 members
- Maximum: 4 members
- ❌ FAIL if: Team has more than 4 members
- ⚠️ WARN if: Team has only 1 member (suggest finding team members)
- Action: Leave comment about team size limits

**Check: Email Addresses**
- All team member emails must end with `@geminisolutions.com`
- ❌ FAIL if: Any non-Gemini email address found
- Action: Leave comment requesting correction

**Check: Required Fields**
- Each team member must have: Name, Email, Delivery Council, Role in Team
- Primary Contact must have: Name, Email, Phone
- ❌ FAIL if: Any required field contains placeholder text or is empty
- Action: Leave comment listing incomplete fields

### 3. Content Completeness (Pass/Fail)

**Check: Problem Statement Word Count**
- Problem Description minimum: 100 words
- Problem Description maximum: 300 words
- ❌ FAIL if: Less than 100 words
- ⚠️ WARN if: More than 300 words (suggest being more concise)
- Action: Leave comment with current word count

**Check: Solution Overview Word Count**
- Solution Overview minimum: 150 words
- Solution Overview maximum: 400 words
- ❌ FAIL if: Less than 150 words
- ⚠️ WARN if: More than 400 words (suggest being more concise)
- Action: Leave comment with current word count

**Check: Key Features**
- Minimum: 3 features
- Maximum: 5 features
- ❌ FAIL if: Less than 3 features listed
- ⚠️ WARN if: Features are too vague (e.g., "AI feature", "Good UX")
- Action: Leave comment requesting specific feature descriptions

**Check: Placeholder Content**
- Scan for common placeholders:
  - `[Full Name]`, `[email@geminisolutions.com]`, `[DC]`
  - `[Feature 1]`, `[Description]`, `[Specify]`
  - `<!-- ... -->` comments without content below them
- ❌ FAIL if: Any placeholder text remains unreplaced
- Action: Leave comment listing sections with placeholders

**Check: Resource Requirements**
- At least one item must be checked/specified in:
  - Development Tools & Platforms
  - Data Requirements
  - Computing Resources
- ❌ FAIL if: All resource sections are empty
- Action: Leave comment requesting resource specification

**Check: Deliverables**
- Midway Check-in: At least 2 deliverables
- Final Submission: All 5 required items must be checked and described
  - Working Prototype
  - Documentation
  - Demo Video
  - Source Code
  - Deployment
- ❌ FAIL if: Insufficient deliverables planned
- Action: Leave comment about deliverable requirements

### 4. Clarity Assessment (Automated Score)

**Check: Problem Clarity Score (0-100)**
Use natural language processing to assess if the problem statement is:
- Specific and well-defined (not vague)
- Clearly identifies who is affected
- Explains current impact with some quantification
- Uses concrete examples or scenarios

Scoring guidance:
- 80-100: Excellent - Very specific, quantified, clear impact
- 60-79: Good - Clear problem, some specifics, could use more detail
- 40-59: Fair - Somewhat vague, needs more specificity
- 0-39: Poor - Too vague or generic

⚠️ WARN if: Score < 60
Action: Leave comment with improvement suggestions:
- "Consider adding specific numbers or metrics to quantify impact"
- "Clarify who exactly is affected and how frequently this occurs"
- "Provide concrete examples of the problem in action"

**Check: Solution Clarity Score (0-100)**
Assess if the solution description is:
- Clearly explains the AI approach and technology
- User experience is described
- Connection between problem and solution is clear
- Feasibility is apparent

Scoring guidance:
- 80-100: Excellent - Clear AI approach, well-explained, feasible
- 60-79: Good - Understandable approach, minor gaps
- 40-59: Fair - Some confusion, needs more detail
- 0-39: Poor - Unclear how it works or solves the problem

⚠️ WARN if: Score < 60
Action: Leave comment with improvement suggestions:
- "Explain more specifically which AI technology you'll use and how"
- "Describe the user experience and workflow more clearly"
- "Clarify the connection between your AI solution and the problem"

### 5. Duplication Detection (Alert Only)

**Check: Similar Submissions**
- Compare current submission with all approved and pending ideas
- Check for similarity in:
  - Problem Title (>70% similarity)
  - Problem Statement (>60% semantic similarity)
  - Solution approach (>60% semantic similarity)

Similarity Analysis:
- Use semantic embeddings to compare content
- Flag potential duplicates for human review
- Consider if ideas are complementary vs. duplicate

⚠️ ALERT if: High similarity detected (>70% overall)
Action: 
- Leave comment: "Note: This idea appears similar to [Team Name]'s submission. Please review and clarify how your approach differs, or consider combining teams."
- Tag mentors for review
- Do NOT auto-reject (human decision required)

### 6. Feasibility Red Flags (Warning Only)

**Check: Resource Reasonableness**
Scan for potential red flags:
- Excessive budget requests (>$1000)
- Requires proprietary/expensive APIs
- Needs specialized hardware not available
- Unrealistic scope for 3-week timeline
- Requires access to confidential data without clearance

⚠️ WARN if: Red flags detected
Action: Leave comment noting concerns for mentor review:
- "Resource requirement concern: [specific issue]. Mentors will review feasibility during manual evaluation."

**Check: AI Technology Appropriateness**
Check if AI is actually needed:
- Problem can be solved with simple rules/automation
- AI technology mentioned is too advanced/cutting-edge
- No clear AI component described

⚠️ WARN if: Questionable AI fit
Action: Leave comment:
- "Consider: Could this be solved without AI? Please clarify the specific AI capabilities that are essential to your solution."

### 7. Final Validation Decision

**Automatic PASS Requirements:**
✅ All format compliance checks passed
✅ All team information valid
✅ All content completeness checks passed
✅ Problem clarity score ≥ 60
✅ Solution clarity score ≥ 60
✅ No placeholder content remaining

**Automatic FAIL Conditions:**
❌ Any format compliance check failed
❌ Team information invalid
❌ Content completeness insufficient
❌ Placeholder content remains
❌ Problem OR Solution clarity score < 40

**Manual Review Required (Neither Pass nor Fail):**
🔍 Clarity scores between 40-59
🔍 Duplication alert flagged
🔍 Feasibility red flags present
🔍 Team has only 1 member

## Agent Actions

### For PASS:
```markdown
✅ **Automated Validation: PASSED**

Your idea submission has passed all automated validation checks! 

**Next Steps:**
1. Your submission will be reviewed by mentors within 2-3 business days
2. You'll receive feedback and approval status via GitHub comments
3. Approved teams will be notified and receive access to development resources

**Validation Summary:**
- ✅ Format compliance: All checks passed
- ✅ Team information: Valid
- ✅ Content completeness: All sections complete
- ✅ Problem clarity: [Score]/100
- ✅ Solution clarity: [Score]/100

Good luck! The mentoring team will be in touch soon.
```

Label: `validation-passed`
Assign: Mentors for manual review

### For FAIL:
```markdown
❌ **Automated Validation: FAILED**

Your submission requires corrections before it can proceed to mentor review. Please address the issues below and resubmit.

**Issues Found:**
[List all failed checks with specific details]

**How to Fix:**
1. Update your submission file with the required corrections
2. Push your changes to the same Pull Request
3. Automated validation will run again automatically

**Need Help?**
If you have questions about these requirements, please comment on this PR or reach out to the hackathon organizers on Teams.
```

Label: `validation-failed`
Request changes on PR

### For Manual Review Required:
```markdown
🔍 **Automated Validation: MANUAL REVIEW REQUIRED**

Your submission has passed basic validation but has been flagged for mentor review due to:
[List reasons for manual review]

**What This Means:**
- Your submission is mostly complete and properly formatted
- Mentors will review the flagged items and provide feedback
- You may be asked to make minor adjustments or clarifications

**Validation Summary:**
- ✅ Format compliance: Passed
- ✅ Team information: Valid
- ✅ Content completeness: Passed
- ⚠️ [List any warnings or concerns]

The mentoring team will review your submission within 2-3 business days.
```

Label: `needs-mentor-review`
Assign: Mentors

## Implementation Notes

### Validation Workflow
1. Trigger: On Pull Request created/updated to `submissions/stage2-ideas/` folder
2. Parse markdown file and extract all sections
3. Run all validation checks in parallel
4. Aggregate results and determine validation decision
5. Post comment with detailed feedback
6. Apply appropriate labels
7. If passed, assign to mentors; if failed, request changes

### Error Handling
- If file cannot be parsed: FAIL with clear error message
- If validation script errors: Alert maintainers, don't block submission
- Graceful degradation: If specific checks fail, continue with others

### Performance
- Validation should complete within 30 seconds
- Cache embedding computations for duplication detection
- Run lightweight checks first, expensive checks only if needed

### Privacy & Security
- Do not log or store submission content outside GitHub
- Duplication detection should be one-way (no reverse lookup of team submissions)
- Ensure team member emails are validated but not exposed publicly

## Testing Validation Agent

### Test Cases

**Test 1: Perfect Submission**
- All sections complete
- Word counts correct
- Team size valid
- No placeholders
- Expected: PASS

**Test 2: Missing Sections**
- Remove "Problem Statement" section
- Expected: FAIL with missing section error

**Test 3: Placeholder Content**
- Leave `[Full Name]` in team member field
- Expected: FAIL with placeholder detection

**Test 4: Word Count Violations**
- Problem description: 50 words (too short)
- Expected: FAIL with word count error

**Test 5: Team Size Violation**
- Add 5 team members
- Expected: FAIL with team size error

**Test 6: Low Clarity Score**
- Vague problem: "Make work better with AI"
- Expected: WARN or FAIL based on score

**Test 7: Potential Duplicate**
- Submit very similar problem statement
- Expected: Manual review flag

**Test 8: Non-Gemini Email**
- Use external email address
- Expected: FAIL with email validation error

### Continuous Improvement
- Track validation accuracy vs. mentor decisions
- Adjust clarity score thresholds based on false positives/negatives
- Refine duplication detection sensitivity
- Gather feedback from participants on clarity of validation messages
