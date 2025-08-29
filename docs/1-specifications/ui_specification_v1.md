There are 3 types of users who will interact with the Skill Management System:
1. **Employees**: They will use the system to view their skill profiles, update their skills, and track their skill development plans.
2. **Managers**: They will oversee their team members' skill profiles, approve skill updates, and assign skill development plans.
3. **HR/Admin**: They will manage the overall skill database, generate reports, and ensure the system's integrity.


# User Interface for Employee
The Employee interface should be user-friendly and intuitive, allowing employees to easily navigate through their skill profiles and development plans. The main components of the Employee UI include:

## Tab 1: My Profile
- **Employee Overview**: 
    - Profile picture
    - Contact information (email, phone number)
    - Designation, department, and location.
- **Education and Experience**: 
    - Educational qualifications
    - Work experience summary
- **Certifications**: 
    - List of certifications with links to verification if available.
- **Edit Profile Button**: Allows employees to update their personal information and skills.

## Tab 2: Skill Assessment

### Job Description
- **Job Role Overview**:
    - Job Role ID and Name
    - Job Role Description
    - Delivery Council and Sub-Delivery Council
    - Designation Title and Level
    - Location and Employment Type
- **Skills Required**:
    - Mandatory Skills: List of skills required for the job role with current proficiency levels.
    - Desired Skills: List of additional skills that are beneficial for the role.
- **Key Responsibilities**: A detailed list of the employee's key responsibilities in their current role.
- **Key Performance Indicators (KPIs)**: Display the KPIs associated with the job role

### Skill Assessment
- **Skill Overview**: Visual summary of skills categorized by Strength, Skilled, Opportunity.
    - Strength: Skills where the employee excels. Rating 4 and above.
    - Skilled: Skills where the employee is competent. Rating 3.
    - Opportunity: Skills that need improvement. Rating 2 and below.

- **My Skill List**: Display(progress bar) the employee's skill ratings and comment with options to view detailed feedback and history.
    - Provide a search box to filter skills.
    - Each skill entry should show:
        - Skill Name
        - Current Skill Level (with visual indicator)
        - Last Rated Date
        - Comments from the last assessment
- **Request Skill Update Button**: Allows employees to request updates to their skill ratings, which will be reviewed by their manager.

### Tab 3: Career Development Plan
- **Development Plan Summary**: A quick overview of the employee's current development plan.
    - Current Skill Level vs. Target Skill Level for each skill in the development plan.
    - Start Date and End Date of the development plan.
    - Status of the development plan (Active, Inactive).
    - Progress of the development plan (Not Started, In Progress, Completed).

- **Detailed Development Plan**: A comprehensive view of the employee's development plan, including all skills, target levels, and timelines.
    - Each skill entry should show:
        - Skill Name
        - Current Skill Level
        - Target Skill Level
        - Start Date and End Date
        - Status (Active, Inactive)
        - Progress (Not Started, In Progress, Completed)
        - Assigned By (Manager ID / HR ID / System ID / Self)
        - Link to course or resource if available.
    - Option to filter skills by name, status and progress.
    - Sort skills by name, status, or progress.

- **Development Activities**: List of activities planned for skill development, such as training sessions, workshops, online courses, etc.
    - Each activity should include:
        - Activity Name
        - Description
        - Scheduled Date
        - Status (Not Started, In Progress, Completed)

- **Add Development Activity Button**: Allows employees to suggest new activities for their development plan, which will be reviewed by their manager.

# User Interface for Manager
The Manager interface should provide tools for overseeing their team members' skill profiles and development plans. The main components of the Manager UI include:

## Tab 1: Team Overview
- Filterable Team View: A hierarchical view of team members with options to filter by Opportunity count, skill status.
- Hierarchical View: Display team members in a tree structure based on reporting lines and count as selected in filters.
- On clicking a team member, display their skill profile and development plan similar to the Employee UI.

## Tab 2: Skill Management
- **Global Skill Repository**: A searchable list of all skills in the organization with options to add new skills.
- **Assign Skill Button**: Allows managers to assign skills to team members from the global skill repository using drag-and-drop.
- **Rate Skill Button**: Enables managers to rate a team member's skill level and provide feedback.
- **Skill Update Requests**: A section to review and approve/reject skill update requests from team members.
- **Create Development Plan Button**: Allows managers to create a skill development plan for a team member.
- **Rate Skill For Team Member Button**: Enables managers to rate a specific skill for a selected team member.
- **Track Progress Button**: Enables managers to track the progress of a team member's skill development plan. Add a tree view of the development plan with progress indicators.


## Tab 3: skill Development Plan
 - 
