Hi, my name is Vengala Rao Rangisetty. I'm currently based in Hyderabad, and I completed my graduation in 2021 from Sri Mittapalli College of Engineering. After graduation I have placed in Mphasis as a fresher and I have around 4 years of experience in IT, as a DevOps Engineer. During this period, I mainly work on setting up CI/CD pipelines using Jenkins and Shell scripting to automate code build, test, and deployment processes. I also manage cloud infrastructure using AWS services like EC2, S3, IAM, and VPC through CloudFormation.

I also handle batch job scheduling with Control-M and cronjobs, and set up monitoring tools like CloudWatch, Splunk to track system health and performance.

My background also includes working with Git for version control, managing incidents and changes using Jira and Remedy, and troubleshooting issues on both Linux and Windows servers.

Throughout my tenure based upon my interest I have completed AWS, Azure and GCP Associate level Certifications.


-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Ansible 
1.Do you have exposure in Ansible? How you used in your project?

Yes, I have hands-on experience with Ansible in my project for automating configuration management and application deployments.
In my  project I used Ansible mainly to automate repetitive tasks on Linux servers. For example, I created Ansible playbooks to:
Install packages like httpd, nginx, or custom monitoring agents across multiple servers.
Also, Ansible was integrated into our CI/CD pipeline using Jenkins. After every code push, Jenkins would trigger an Ansible playbook to deploy the updated code or restart services in dev or UAT environments.
This helped reduce manual errors and saved a lot of time during deployments.

2. What is YAML and Why is it used in Ansible?

YAML stands for “YAML Ain’t Markup Language.” It’s a human-readable data serialization format, and it's used in Ansible to write playbooks, inventory files, and variable files.
Ansible uses YAML because it's:
Easy to read and write — even for people who aren’t developers.
Structured with indentation, which makes the flow of tasks clear.
Supports complex data types like dictionaries (key-value pairs) and lists, which is helpful when defining variables, tasks, and roles.

4. What is an Inventory file?
   
An inventory file in Ansible is a file that lists the managed hosts or servers where tasks will be executed. It defines the target machines and can group them logically—for example, webservers, dbservers, or dev, prod, etc.
There are two main types of inventory:
Static Inventory – A simple .ini or .yaml file where you manually list IPs or hostnames.
Dynamic Inventory – Used in cloud environments like AWS or Azure, where the inventory is pulled in real-time using plugins or scripts. For example, we used the AWS EC2 dynamic inventory plugin to pull instance details based on tags.

4.what are ansible facts how do you use them?

Ansible facts are system properties gathered from hosts. They help in conditional logic in playbooks. E.g., using ansible_os_family to decide package managers.
These facts include details like:
IP address
OS type and version
Hostname

5. Write a playbook for installing nginx server?
- name: Install and start NGINX
  hosts: webservers
  become: yes
  tasks:
    - name: Install NGINX
      apt:
        name: nginx
        state: present
    - name: Start and enable NGINX
      service:
        name: nginx
        state: started
        enabled: yes
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Linux ---
1.	what command would you use to check disk usage in a Linux server. 
(df -h)
2.	How do you check CPU and memory usage in Linux?  -- (Top, htop, vmstat, free-h)
   
•	vmstat reports information about processes, memory, paging, block IO, traps, and cpu activity.
•	The top command in Linux displays real-time information about system processes and resource usage. It is commonly used to monitor CPU and memory usage, process states, and system load.
•	The free command in Linux displays the amount of free and used memory in the system. It displays the total amount of free and used physical and swap memory along with the buffer used by the kernel.

4. can you name the command to find the hidden files in Linux server --   ls -a
   
6. How do you check system logs in Linux? where are they stored?  -- (stored cat/var/log/syslog, To
   
8. How you give permission to a file and could you name the command? chmod 755
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
SQL --
1.explain DDL and DML commands?

DDL commands are used to define and manage database structure, like tables, schemas, indexes, etc.

CREATE - Creates a new table, view, or database
ALTER - Modifies an existing table (e.g., add/remove columns)
DROP - Deletes a table or database permanently
TRUNCATE - Removes all data from a table but keeps the structure

DML commands are used to manipulate the data inside tables (insert, update, delete, retrieve)

SELECT – Retrieves data (though technically part of DQL, often grouped with DML)
INSERT - Adds new data into a table
UPDATE - Modifies existing data
DELETE - Removes data from a table

2.what are indexes? 

it helps the database find rows faster without scanning the entire table. Speed up data retrieval on columns.

3.How would you find the second highest salary table from a employee table?


SELECT MAX(salary) AS SecondHighestSalary
FROM employees
WHERE salary < ( SELECT MAX(salary) FROM employees);

SELECT DISTINCT salary
FROM employees
ORDER BY salary DESC
LIMIT 1 OFFSET 1;

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Jenkins--
1.How you schedule job in Jenkins?

In Jenkins, we schedule jobs using the “Build periodically” option with a CRON syntax

Schedule	CRON Format	      Meaning

Every 15 mins	 H/15 * * * *	    Runs every 15 minutes

Every day at 2 AM	 0 2 * * *	    Runs daily at 2 AM

Every Sunday at 1 AM	   0 1 * * 0	     Weekly on Sunday

Every weekday at 6 PM	   0 18 * * 1-5	      Mon–Fri at 6 PM

2.Explain CI CD in Jenkins?

CI/CD in Jenkins means automating the process of building, testing, and deploying code. CI (Continuous Integration) is when Jenkins automatically pulls the latest code from Git, builds it, and runs tests whenever a developer pushes changes. CD (Continuous Delivery or Deployment) is when, after successful testing, Jenkins automatically deploys the application to environments like Dev, UAT, or Production. This helps reduce manual work and errors. 
In my project, I used Jenkins to set up CI/CD pipelines that build the code using Maven, run test cases, and deploy the application using Ansible. This made our releases faster and more reliable.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Docker --
 1.what is docker?
 
Docker is an open-source platform designed to streamline the process of building, deploying, and running applications using containers.

 2.diff between Cmd and entry point 
 
CMD defines the default command or arguments that will be executed when a container starts. It provides a default behavior that can be easily overridden.
ENTRYPOINT defines the primary executable that will always run when a container starts. It sets a fixed command that is not typically overridden at runtime.

CMD -- we can pass arguments 
Entry point -- we pass commands that are executable


