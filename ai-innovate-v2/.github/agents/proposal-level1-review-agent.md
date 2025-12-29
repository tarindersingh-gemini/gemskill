## Agent Purpose
This GitHub Copilot agent performs automated Level 1 review of idea submissions that have passed Stage 2 validation. It provides preliminary scoring and filtering to identify proposals that clearly don't meet minimum standards, reducing mentor workload.

## Agent Workflow
1. Retrieve proposal that passed Stage 2 validation
2. Analyze content using AI-powered evaluation
3. Score against evaluation criteria (excluding Team Capability which requires human judgment)
4. Identify red flags and concerns
5. Make filtering decision (Auto-Reject vs. Forward to Manual Review)
6. Provide detailed feedback and scoring

---

## Scoring Implementation

### Criteria to Evaluate (Total: 90 points)
1. **Innovation & Creativity**: 25 points
2. **Technical Feasibility**: 20 points
3. **Business Value & Impact**: 20 points
4. **Resource Reasonableness**: 15 points
5. **Clarity & Completeness**: 10 points

*Note: Team Capability (10 points) is evaluated only in manual review*

---

## Detailed Scoring Instructions

### 1. Innovation & Creativity Assessment (25 points)

**Analysis Approach:**
- Compare solution against common AI applications (chatbots, recommendation systems, automation)
- Assess uniqueness of problem-solution pairing
- Evaluate creative use of AI technologies
- Check for novel combinations or approaches

**Automated Scoring Logic:**

**Score 21-25 (Exceptional):**
Indicators:
- Uses AI in a way not commonly seen (e.g., novel domain application)
- Combines multiple AI technologies uniquely
- Solution approach is non-obvious or counterintuitive
- Could inspire new applications or patterns
- Problem statement mentions "no existing solution" with evidence
- Unique value proposition clearly articulated

Example triggers:
- "First application of [AI tech] to [domain]"
- Novel combination: "Using [Tech A] + [Tech B] to solve [Problem]"
- Creative reframing of problem enables AI solution

**Score 16-20 (Strong):**
Indicators:
- Fresh approach to known problem category
- Non-standard use of AI technology
- Some unique elements combined with proven concepts
- Clear differentiation from existing solutions
- Shows deep understanding of AI capabilities

Example triggers:
- "Different from existing tools by [specific innovation]"
- Uses AI capability in unexpected but logical way
- Adapts proven approach to new context

**Score 11-15 (Good):**
Indicators:
- Solid, practical AI application
- Standard technology applied well
- Some innovative elements present
- Incremental improvement over existing approaches
- Demonstrates competent AI understanding

Example triggers:
- Common AI application (chatbot, classifier, recommender) done well
- Applies standard practices with minor improvements
- Clear but not groundbreaking approach

**Score 6-10 (Fair):**
Indicators:
- Very common AI application
- Minimal innovation beyond standard approach
- Similar to many existing solutions
- Limited creative thinking evident
- Basic AI understanding shown

Example triggers:
- Generic "AI-powered assistant" without unique features
- Standard application with no differentiation mentioned
- Could be templated from tutorials

**Score 0-5 (Poor):**
Indicators:
- Problem doesn't benefit from AI (simple rules would work)
- No AI component actually described
- Direct copy of known solution
- No differentiation or innovation
- Misunderstanding of AI capabilities

Red flags:
- "Use AI to make X better" without specifics
- Problem is rule-based (e.g., simple IF-THEN logic)
- Solution is just "add chatbot" without AI functionality
- Copy-paste from existing tools/products

---

### 2. Technical Feasibility Assessment (20 points)

**Analysis Approach:**
- Evaluate scope against 3-week timeline
- Check technology accessibility and maturity
- Assess implementation plan completeness
- Identify dependencies and blockers
- Evaluate technical risk factors

**Automated Scoring Logic:**

**Score 17-20 (Highly Feasible):**
Indicators:
- Clear 3-phase implementation plan matching hackathon timeline
- Uses well-documented, accessible technologies (OpenAI, Hugging Face, standard libraries)
- All required APIs/tools have free tiers or are already available
- Technical approach uses proven patterns
- Dependencies are standard and available
- Risks are identified with mitigation plans
- Scope is appropriate (single feature with polish > many basic features)

Example triggers:
- "Using [proven API] with [standard framework]"
- Implementation phases are specific and time-boxed
- "We'll use free tier of [Service]"
- Clear MVP definition with stretch goals

**Score 13-16 (Feasible):**
Indicators:
- Reasonable implementation plan with some details
- Technologies are accessible with documentation
- Most APIs/tools are available
- Solid technical approach
- Some dependencies but manageable
- Moderate risks with some mitigation

Example triggers:
- Some learning curve mentioned but manageable
- Mix of familiar and new technologies
- Most resources available, some need procurement
- Scope is ambitious but achievable

**Score 9-12 (Moderately Feasible):**
Indicators:
- Implementation plan has gaps or is vague
- Some technologies require significant learning
- Several external dependencies
- Technical approach has uncertain elements
- Higher risk factors present
- Scope is challenging for timeline

Red flags:
- "We'll learn [complex technology] during the hackathon"
- Multiple paid services needed
- Dependencies on unavailable datasets
- Very ambitious scope without prioritization

**Score 5-8 (Questionable):**
Indicators:
- Implementation plan is very high-level or missing
- Requires specialized technologies
- Many external dependencies
- Technical approach has major uncertainties
- High risk without mitigation
- Scope is unrealistic for 3 weeks

Red flags:
- "We need to build custom [ML model] from scratch"
- Requires proprietary or restricted technologies
- Multiple blocking dependencies
- No MVP/phased approach
- "If we can't get X, we'll do Y" without clear plan

**Score 0-4 (Not Feasible):**
Indicators:
- No clear implementation plan
- Requires inaccessible or proprietary technologies
- Critical blocking dependencies
- Technical approach is flawed or impossible
- Scope is completely unrealistic

Red flags:
- Requires months of development compressed to 3 weeks
- "We need access to confidential data"
- Technologies don't exist or are unavailable
- Fundamental technical misunderstandings
- "We'll build everything from scratch"

---

### 3. Business Value & Impact Assessment (20 points)

**Analysis Approach:**
- Quantify potential user base
- Evaluate impact metrics and quantification
- Assess organizational alignment
- Evaluate scalability and adoption potential
- Check for concrete vs. theoretical benefits

**Automated Scoring Logic:**

**Score 17-20 (High Impact):**
Indicators:
- Affects 50+ employees or entire departments
- Quantified impact metrics provided (hours saved, cost reduction, quality improvement)
- Clear ROI calculation or estimation
- Aligns with stated company strategic goals
- Strong potential for permanent adoption
- Can scale beyond initial use case
- Problem is validated with evidence (survey, data, examples)

Example triggers:
- "Currently affects 150 employees daily"
- "Will save approximately 2 hours per person per week"
- "Reduces [cost] by estimated $X annually"
- "Addresses company priority of [strategic goal]"
- "Can be extended to [other departments/use cases]"

**Score 13-16 (Moderate-High Impact):**
Indicators:
- Affects 20-50 employees or multiple teams
- Some quantified benefits
- Positive ROI expected
- Supports organizational objectives
- Good adoption potential
- Some scalability possible

Example triggers:
- "Used by [specific department] of 30 people"
- "Reduces time spent on [task] significantly"
- "Addresses known pain point in [process]"
- "Could expand to similar use cases"

**Score 9-12 (Moderate Impact):**
Indicators:
- Affects 10-20 employees or single team
- Impact described but not fully quantified
- ROI is unclear but possible
- Loosely aligned with company goals
- Uncertain adoption potential
- Limited scalability

Example triggers:
- "Will help [small team] with [task]"
- "Should improve [process]" (vague improvement)
- "Beneficial for [narrow use case]"
- Impact claims without supporting evidence

**Score 5-8 (Low Impact):**
Indicators:
- Affects fewer than 10 employees
- Impact is difficult to measure
- ROI is questionable
- Weak organizational alignment
- Low adoption likelihood
- No clear scaling path

Red flags:
- "Could be useful for anyone who needs to [generic task]"
- No specific user group identified
- Theoretical benefits only
- Duplicate of existing tools
- "Nice to have" rather than "need to have"

**Score 0-4 (Minimal Impact):**
Indicators:
- Problem is trivial or hypothetical
- Benefits very few or no employees
- No measurable impact
- No organizational alignment
- No adoption potential
- Solving a non-existent problem

Red flags:
- "This would be cool to have"
- Problem validation is missing
- No identified users
- Solution looking for a problem
- Personal project rather than organizational benefit

---

### 4. Resource Reasonableness Assessment (15 points)

**Analysis Approach:**
- Calculate total estimated cost
- Check resource availability
- Evaluate justification quality
- Assess requirement complexity
- Identify blocking resources

**Automated Scoring Logic:**

**Score 13-15 (Very Reasonable):**
Indicators:
- Total cost: $0 or minimal (<$50)
- All resources available or standard
- Uses free tiers effectively
- Well-justified requests
- Detailed budget breakdown
- No special hardware needed
- Standard development tools
- No special permissions required

Example triggers:
- "Using free tier of [service]"
- "All resources already available"
- "GitHub Copilot (already provided) + free OpenAI credits"
- Clear breakdown: "API: $0 (free tier), Hosting: $0 (GitHub Pages)"

**Score 10-12 (Reasonable):**
Indicators:
- Total cost: $50-$100
- Most resources available
- Clear justification for paid services
- Reasonable budget
- Standard computing resources
- Common development tools
- May need some standard permissions

Example triggers:
- "Need $75 in API credits for [specific purpose]"
- "Paid tier of [service] needed for [feature]"
- Resource requests are specific and justified

**Score 7-9 (Moderately Reasonable):**
Indicators:
- Total cost: $100-$300
- Some resources need procurement
- Justification could be stronger
- May need enhanced computing
- Some specialized tools
- Requires approvals

Red flags:
- Multiple paid services without exploring free alternatives
- "We might need [expensive resource]"
- Vague budget estimates
- Unclear necessity of paid resources

**Score 4-6 (Concerning):**
Indicators:
- Total cost: $300-$1000
- Many resources need procurement
- Weak justification
- Specialized hardware needed
- Multiple paid services
- Complex approval process

Red flags:
- No consideration of free alternatives
- Expensive specialized tools for short project
- "We need GPU cluster"
- Inflated or unrealistic budget
- Many uncertain cost items

**Score 0-3 (Unreasonable):**
Indicators:
- Total cost: >$1000
- Resources unavailable or restricted
- No justification
- Expensive specialized hardware
- Proprietary/inaccessible APIs
- Cannot obtain permissions

Red flags:
- "Requires enterprise license of [expensive tool]"
- "Need access to proprietary database"
- "Requires custom infrastructure"
- Resources that simply cannot be provided
- No attempt to work within constraints

---

### 5. Clarity & Completeness Assessment (10 points)

**Analysis Approach:**
- Check section completeness
- Evaluate writing quality
- Assess specificity and detail
- Identify vague or ambiguous content
- Review professional presentation

**Automated Scoring Logic:**

**Score 9-10 (Excellent):**
Indicators:
- All sections thoroughly completed
- Problem statement is specific and clear
- Solution description is detailed and understandable
- Technical approach is well-explained
- Resources are specifically identified
- Deliverables are clearly defined
- Professional writing quality
- No significant ambiguity
- Meets all word count requirements generously

**Score 7-8 (Good):**
Indicators:
- All sections completed
- Clear problem and solution
- Understandable technical approach
- Resources identified
- Deliverables defined
- Good writing quality
- Minor areas of ambiguity
- Meets word count requirements

**Score 5-6 (Fair):**
Indicators:
- Most sections completed
- Some clarity issues in problem or solution
- Technical approach needs more detail
- Resources somewhat vague
- Deliverables partially defined
- Adequate writing quality
- Some ambiguous areas
- Barely meets word count requirements

**Score 3-4 (Poor):**
Indicators:
- Several sections incomplete or minimal
- Problem or solution unclear
- Technical approach is vague
- Resources not well-defined
- Deliverables unclear
- Poor writing quality
- Significant ambiguity
- Below word count requirements

**Score 0-2 (Inadequate):**
Indicators:
- Many sections incomplete
- Problem and solution very unclear
- No clear technical approach
- Resources undefined
- Deliverables not specified
- Unprofessional presentation
- Highly ambiguous throughout

---

## Red Flags Check

### Critical Red Flags (Strong reject indicators)
Check for these issues that should heavily influence the decision:

1. **Technical Impossibility**
   - Fundamental technical misunderstanding
   - Requires non-existent technology
   - Timeline is off by orders of magnitude
   - Physics/logic violations

2. **Resource Blockers**
   - Requires confidential/proprietary data without clearance
   - Needs equipment that cannot be provided
   - Cost exceeds reasonable limits significantly
   - Critical dependencies are unavailable

3. **No AI Component**
   - Problem is purely rule-based
   - "AI" is mentioned but not actually used
   - Simple automation would suffice
   - Misunderstands what AI is

4. **Ethical/Legal Concerns**
   - Privacy violations
   - Misuse of personal data
   - Potential discrimination or bias
   - Legal compliance issues

5. **Duplicate/Already Exists**
   - Exact duplicate of another submission
   - Tool already exists and is available
   - Problem already solved adequately
   - No differentiation from existing solution

### Warning Flags (Human review recommended)
Issues that need mentor attention but aren't automatic rejects:

1. **Scope Concerns**
   - Very ambitious but possibly achievable
   - Multiple complex features
   - Unclear prioritization

2. **Learning Curve**
   - Requires learning new technology
   - Team experience is uncertain
   - Technical challenges present

3. **Resource Questions**
   - Cost is moderate but justified
   - Some resources need procurement
   - Permissions may be needed

4. **Impact Uncertainty**
   - Benefits are described but not quantified
   - User base is unclear
   - Adoption strategy missing

---

## Filtering Decision Logic

### Auto-Reject Criteria (Forward to mentor with strong concern flag)
**Recommend rejection if ANY of these conditions are met:**

1. **Total Score < 30 points** (out of 90)
2. **Any criterion scores 0-4 points** (critical failure in one area)
3. **Multiple criteria score 5-7 points** (weak across the board)
4. **Critical red flag identified** (technical impossibility, resource blocker, ethical concern)
5. **Innovation score < 6 AND Feasibility score < 9** (neither innovative nor feasible)

### Forward to Manual Review
**Forward to mentors if:**
- Total score ≥ 30 points
- No criterion scores below 5 points
- No critical red flags
- Even if warning flags exist (humans should assess)

---

## Output Format

### For Auto-Reject Recommendation

```markdown
🔴 **Level 1 Automated Review: REJECTION RECOMMENDED**

**Overall Assessment:**
This proposal does not meet the minimum thresholds for approval based on automated evaluation. Manual mentor review may override if there are exceptional circumstances.

**Scoring Summary:**
- Innovation & Creativity: [Score]/25 - [Brief rationale]
- Technical Feasibility: [Score]/20 - [Brief rationale]
- Business Value & Impact: [Score]/20 - [Brief rationale]
- Resource Reasonableness: [Score]/15 - [Brief rationale]
- Clarity & Completeness: [Score]/10 - [Brief rationale]

**Total Automated Score: [Score]/90**

**Critical Concerns:**
- [List specific issues that led to rejection recommendation]
- [Include critical red flags if any]

**Recommendation:**
Based on the evaluation criteria, this proposal falls below the minimum threshold for approval. Key areas of concern are:
1. [Primary concern]
2. [Secondary concern]
3. [Additional concern if applicable]

**Next Steps:**
- Mentors will perform final review to confirm decision
- If confirmed, team will receive detailed feedback for future submissions
- If mentors identify overlooked potential, proposal may advance

---
*This is an automated assessment. Final decision will be made by mentor review.*
```

Label: `auto-reject-recommended`
Assign: Mentors for final decision

### For Forward to Manual Review

```markdown
✅ **Level 1 Automated Review: PASSED - FORWARDING TO MENTORS**

**Overall Assessment:**
This proposal has passed automated filtering and will be reviewed in detail by mentors. The scores below provide initial assessment to guide manual review.

**Scoring Summary:**
- Innovation & Creativity: [Score]/25 - [Brief rationale]
- Technical Feasibility: [Score]/20 - [Brief rationale]
- Business Value & Impact: [Score]/20 - [Brief rationale]
- Resource Reasonableness: [Score]/15 - [Brief rationale]
- Clarity & Completeness: [Score]/10 - [Brief rationale]

**Total Automated Score: [Score]/90**
**Estimated Final Score Range: [Score] - [Score+10]** (including Team Capability points)

**Strengths Identified:**
- [Strength 1 - specific]
- [Strength 2 - specific]

**Areas for Mentor Focus:**
- [Area needing human judgment]
- [Aspect requiring careful evaluation]
- [Team capability assessment needed]

**Warning Flags (if any):**
- [Warning flag 1 with details]
- [Warning flag 2 with details]

**Mentor Review Recommendations:**
1. [Specific aspect to verify]
2. [Question to answer during review]
3. [Risk to assess]

**Next Steps:**
- Mentors will score Team Capability (10 points)
- Final total score will determine approval decision
- Team will receive feedback within 2-3 business days

---
*This automated assessment guides but does not replace mentor review. Final decision rests with mentors.*
```

Label: `passed-level1`, `awaiting-mentor-review`
Assign: Mentors
Priority: Based on score (higher scores = higher priority)

---

## Implementation Notes

### Scoring Calibration
- Run agent on sample proposals first
- Compare scores with mentor assessments
- Adjust scoring thresholds if needed
- Document calibration decisions

### Natural Language Processing
For scoring that requires semantic understanding:
- Use LLM-based analysis (GPT-4, Claude, etc.)
- Provide scoring rubric as context to LLM
- Extract key phrases and concepts
- Cross-reference with databases of common solutions

### Performance Optimization
- Cache common analyses (technology stack checks, cost estimates)
- Run scoring criteria in parallel where possible
- Limit LLM calls to necessary evaluations
- Target: Complete review in under 60 seconds

### Quality Assurance
- Log all automated scores and rationales
- Enable mentor override with reason documentation
- Track agreement rate between automated and final scores
- Continuously improve scoring algorithms

### False Positive/Negative Management
- **False Negative** (good proposal rejected): Mentors can override with justification
- **False Positive** (bad proposal advanced): Caught in manual review, but wastes mentor time
- Tune thresholds to minimize false negatives (let borderline through)
- Better to have mentors reject than miss good proposals

---

## Testing and Validation

### Test Scenarios

**Test 1: Clear Reject**
- Innovation: 3, Feasibility: 8, Business Value: 5, Resources: 10, Clarity: 7
- Total: 33 (passes threshold) but Innovation critical failure
- Expected: Auto-reject recommended

**Test 2: Borderline Pass**
- Innovation: 12, Feasibility: 11, Business Value: 10, Resources: 10, Clarity: 8
- Total: 51
- Expected: Forward to manual review

**Test 3: Strong Candidate**
- Innovation: 20, Feasibility: 16, Business Value: 18, Resources: 13, Clarity: 9
- Total: 76
- Expected: Forward to manual review with high priority

**Test 4: Critical Red Flag**
- Good scores overall (60+) but requires confidential data access
- Expected: Auto-reject recommended with red flag notation

**Test 5: Warning Flags Only**
- Moderate scores (45-50) with some warning flags
- Expected: Forward to manual review with warnings noted

### Continuous Monitoring

Track these metrics:
- Auto-reject rate vs. mentor agreement
- Manual override frequency and reasons
- Score distribution across submissions
- Time to complete evaluation
- Mentor feedback on assessment quality

### Iteration Process
1. Collect mentor feedback after each round
2. Analyze disagreements between automated and manual scores
3. Adjust scoring algorithms and thresholds
4. Update rubrics based on learnings
5. Re-test on previous submissions
6. Document changes and rationale
