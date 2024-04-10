1. **What do you mean by Build?**
   A build in Jenkins refers to the process of compiling source code, running tests, and packaging the application artifacts. It involves transforming source code into an executable form or deployable package.

2. **What is CI?**
   CI stands for Continuous Integration. It's a development practice where developers integrate code into a shared repository frequently, preferably several times a day. Each integration triggers automated builds and tests, ensuring early detection of errors.

3. **How does CI work? How do people work day to day tasks?**
   CI works by automatically integrating code changes into a shared repository and running automated tests. Developers work on small increments of code, committing changes frequently. Jenkins, or any CI tool, detects these changes, triggers a build process, and provides feedback on the build status. This process ensures that issues are identified and fixed early in the development cycle.

4. **What are the Prerequisites for CI?**
   Prerequisites for CI include a version control system, automated build scripts, automated tests, and a CI server like Jenkins.

5. **Which tool do you use for CI? And how does it work?**
   Jenkins is a popular tool for CI. It works by monitoring changes in version control repositories, triggering builds, running tests, and providing feedback on the build status.

6. **What is the difference between SVN and Jenkins?**
   SVN (Subversion) is a version control system used for storing and managing source code, while Jenkins is a CI server used for automating the build and testing process.

7. **What kind of plugins have you installed and used?**
   Plugins extend Jenkins' functionality. Commonly used plugins include those for version control systems (e.g., Git, SVN), build tools (e.g., Maven, Gradle), testing frameworks, and deployment tools.

8. **Have you created Jenkins job from scratch?**
   Yes, creating Jenkins jobs from scratch involves configuring job parameters, defining source code repositories, specifying build steps, setting up post-build actions, and configuring triggers for automatic builds.

9. **Have you set up Jenkins? How did you install Jenkins?**
   Jenkins can be set up by downloading the Jenkins WAR file and running it on a Java Servlet container like Apache Tomcat. Alternatively, it can be installed using package managers like apt or yum on Linux systems.

10. **How do you start Jenkins as a service?**
    Jenkins can be started as a service using platform-specific commands. For example, on Linux, it can be started as a service using systemctl start jenkins.

11. **How do you start/stop/restart Jenkins?**
    Jenkins can be started, stopped, or restarted using platform-specific commands or through the Jenkins web interface.

12. **How do you change your port number for your Jenkins, and what is the default port?**
    By default, Jenkins runs on port 8080. You can change the port number by modifying the Jenkins configuration file (jenkins.xml or jenkins.yaml) and specifying a different port number.

13. **Where do you find default Jenkins logs?**
    Default Jenkins logs are typically located in the $JENKINS_HOME/logs directory.

14. **How do you find if the Jenkins server is running or not?**
    You can check if the Jenkins server is running by accessing the Jenkins web interface or by using platform-specific commands like systemctl status jenkins on Linux.

15. **How do you stop Jenkins when some build jobs are in progress?**
    Jenkins can be stopped gracefully by using the "Shutdown" option in the Jenkins web interface. In case of emergencies, you can also stop the Jenkins process forcefully using platform-specific commands.

16. **How do you migrate Jenkins from one machine to another?**
    To migrate Jenkins from one machine to another, you need to transfer the Jenkins home directory, which contains all configuration data, jobs, and plugins. You also need to ensure that the new machine meets the prerequisites for running Jenkins.

17. **Where does Jenkins store its configuration data?**
    Jenkins stores its configuration data, including job configurations and plugin settings, in the Jenkins home directory.

18. **What is the default Jenkins home directory? How do you change it?**
    The default Jenkins home directory is typically located at /var/lib/jenkins on Linux systems. You can change the Jenkins home directory by modifying the JENKINS_HOME environment variable or by specifying a different directory in the Jenkins configuration file.

19. **Where does Jenkins store global configuration and job-related configuration?**
    Jenkins stores global configuration settings in the config.xml file within the Jenkins home directory. Job-related configurations are stored in separate directories within the jobs directory.

20. **How do you restore the system configuration and all the jobs?**
    You can restore the system configuration and all jobs by copying the configuration files from a backup of the Jenkins home directory to the new Jenkins installation.

21. **How many job files in Jenkins?**
    The number of job files in Jenkins depends on the number of jobs configured. Each job is represented by a separate directory within the jobs directory in the Jenkins home directory.

22. **How do you create a Jenkins job? How did you set up build and deployment using Jenkins for your project?**
    To create a Jenkins job, you can use the Jenkins web interface to configure job parameters, define source code repositories, specify build steps, set up post-build actions, and configure triggers for automatic builds. Build and deployment processes can be set up using plugins and custom scripts tailored to your project requirements.

23. **What is parameterized builds?**
    Parameterized builds allow you to define parameters for a Jenkins job, such as strings, numbers, or boolean values, which can be passed to the job when it is triggered. This allows for greater flexibility and customization in job execution.

24. **What is cron tab and cron scm?**
    Cron tab is a time-based job scheduler in Unix-like operating systems, which allows users to schedule tasks to run periodically at fixed times, dates, or intervals. Cron SCM is a Jenkins plugin that allows you to schedule SCM (Source Code Management) polling using cron syntax.

25. **How do you configure security user database for your Jenkins?**
    Security settings in Jenkins can be configured through the Jenkins web interface. You can set up user accounts, define access controls, and configure authentication mechanisms such as LDAP or local user databases.

26. **Are you using LDAP for build organization?**
    LDAP (Lightweight Directory Access Protocol) can be used for centralized user authentication and authorization in Jenkins. It allows for integration with existing LDAP directories for managing user accounts and permissions.

27. **Do you take backup of Jenkins? If yes, how?**
    Yes, Jenkins backups can be taken by creating a copy of the Jenkins home directory, which contains all configuration data, jobs, and plugins. Regular backups ensure that you can restore Jenkins in case of data loss or system failure.

28. **Do you take backup only job-related configurations other than workspace?**
    Yes, it's a common practice to take backups of job-related configurations, including job definitions and plugin settings, but excluding workspace contents, which can be regenerated during builds.

29. **How do you install Jenkins plugins manually?**
    Jenkins plugins can be installed manually by downloading the plugin .hpi or .jpi file from the Jenkins website or plugin repository and uploading it through the Jenkins web interface.

30. **How do you set up distributed builds?**
    Distributed builds in Jenkins allow you to distribute build jobs across multiple Jenkins nodes, enabling parallel execution of builds. To set up distributed builds, you need to configure Jenkins nodes and ensure network connectivity between the master and slave nodes.

31. **How do you add a node to your master or how to create nodes?**
    Nodes in Jenkins represent individual machines that can execute build jobs. You can add nodes to the Jenkins master by configuring them through the Jenkins web interface or by using configuration files.

32. **How do you see the process ID and whether the Jenkins server is running or not?**
    The process ID of the Jenkins server can be obtained using platform-specific commands like ps on Unix-like systems. You can also check the status of the Jenkins server using platform-specific commands like systemctl status jenkins on Linux.

33. **What are the best practices do you follow in Jenkins?**
    Some best practices in Jenkins include:
    - Using version control for Jenkins configurations
    - Regularly backing up Jenkins data
    - Keeping Jenkins and plugins up-to-date
    - Using parameterized builds for flexibility
    - Securing Jenkins with proper authentication and authorization
    - Monitoring Jenkins performance and resource usage
    - Documenting job configurations and procedures for reproducibility
    - Implementing automated testing and quality gates in CI/CD pipelines.
