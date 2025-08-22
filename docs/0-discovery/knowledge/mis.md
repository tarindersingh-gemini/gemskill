Management Information System (MIS) Summary   

High Level Feature list (Primary and secondary purpose of application):  


Primary Purpose: 

Data collection and storage: MIS aims to gather, organize, and store relevant data and information from various sources within the organization. This includes data on inventory, finances, customer information, and other relevant metrics.  

Data processing and analysis: MIS processes the collected data to transform it into meaningful information and insights. It involves data manipulation, calculations, comparisons, and statistical analysis to generate reports and make informed decisions.  

Decision making and planning: MIS provides decision-makers with accurate, timely, and relevant information to support effective decision making. It helps in strategic planning, resource allocation, goal setting, and performance evaluation.  

Communication and collaboration: MIS facilitates the sharing and dissemination of information across different ECs and DCs of the organization. It promotes communication, collaboration, and coordination among employees, enhancing efficiency and productivity.  

Performance monitoring and control: MIS monitors and tracks key performance indicators (KPIs) and operational metrics to assess the performance of individuals, teams, and the organization. 

Secondary Purpose: 

Improved Decision Making: MIS provides timely and accurate information to decision-makers, enabling them to make informed and data-driven decisions. It helps in analyzing trends, identifying patterns, and evaluating various options, leading to more effective and efficient decision-making processes. 

Increased Operational Efficiency: MIS streamlines and automates business processes, reducing manual effort and minimizing errors. It improves productivity by providing tools and systems that enable employees to work more efficiently, saving time and resources. 

Enhanced Communication and Collaboration: MIS facilitates better communication and collaboration among employees, departments, and stakeholders. It allows for the seamless exchange of information, promotes knowledge sharing, and enables effective coordination across different functions within the organization. 

Effective Resource Management: MIS helps organizations in managing their resources, such as human resources, inventory, and finances, more effectively. It enables better planning, allocation, and utilization of resources, leading to cost savings, improved productivity, and optimized operations. 

 
BRD Link: Shared the BRD Document already with the architect group.  


Architecture diagram (for Production):  

Full stack development approach  

Interfaces designed in HTML5. 

Frontend engineering in ASP.Net Core/ MVC 5 

Backend engineering in C# supported by SQL database server and Flat Files 

Robust DR mechanism – Secondary Database Servers, Regular Data Backups, etc.

Connected systems:

HRIS – while onboard a new employee in MIS 

Frequency:  trigger on new employee onboarding 

Purpose: to get the values from HRIS to reduce the repetition of entries.   

GemBook/ContriPoint/ATS/HRIS/HPIPE/ORG CHART (All internal projects use the employee data set) 

Frequency:  as per their needs. 

Purpose:  To be in Sync with golden data source. 

Deployment: PROD 

Frontend Deployment details – Manual deployment  

Backend deployment details – Manual deployment 

 

 
