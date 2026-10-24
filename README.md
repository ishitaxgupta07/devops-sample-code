

\# Hello World Jenkins Job



\## 1. Project Overview



This project demonstrates how to create and execute a simple Jenkins job using a shell script stored in a GitHub repository. Jenkins retrieves the source code from GitHub, executes the script, and displays the output in the Console Output.



The project introduces the basic concepts of Continuous Integration (CI), source code management, automated job execution, and build verification.



\## 2. Objectives



\- Create a GitHub repository for sample code.

\- Write and commit a shell script.

\- Integrate GitHub with Jenkins.

\- Create a Jenkins Freestyle project.

\- Execute a shell script through Jenkins.

\- Verify the build result using Console Output.



\## 3. Tools and Technologies



\- \*\*Jenkins:\*\* Automation server used to execute the job.

\- \*\*Docker:\*\* Runs Jenkins in a container.

\- \*\*Git:\*\* Version control for the source code.

\- \*\*GitHub:\*\* Hosts the source code repository.

\- \*\*PowerShell:\*\* Used to create files and run Git commands.

\- \*\*Bash shell:\*\* Executes the Hello World script inside Jenkins.



\## 4. GitHub Repository



The project uses a public GitHub repository.



\- \*\*Repository name:\*\* `devops-sample-code`

\- \*\*Repository URL:\*\* https://github.com/ishitaxgupta07/devops-sample-code

\- \*\*Branch:\*\* `main`



The repository contains the `hello-world.sh` script used by the Jenkins job.



\## 5. Creating the Shell Script



A file named `hello-world.sh` was created with the following content:



```bash

\#!/bin/bash

echo "Hello, Jenkins!"

```



The first line identifies Bash as the intended interpreter. The `echo` command prints the message to the terminal.



\## 6. Git Initialization and Commit



The local project directory was initialized as a Git repository. The script was staged and committed using the following commands:



```powershell

git init

git branch -M main

git add hello-world.sh

git commit -m "Add hello-world.sh"

```



The local repository was connected to GitHub and the script was pushed to the `main` branch.



```powershell

git remote add origin https://github.com/ishitaxgupta07/devops-sample-code.git

git push -u origin main

```



These commands establish version control and publish the script to the remote repository.



\## 7. Jenkins Job Configuration



A Jenkins Freestyle project named `HelloWorld` was created.



\### Source Code Management



The job was configured to retrieve code from GitHub.



\- \*\*Source Code Management:\*\* Git

\- \*\*Repository URL:\*\* `https://github.com/ishitaxgupta07/devops-sample-code.git`

\- \*\*Branch Specifier:\*\* `\*/main`

\- \*\*Credentials:\*\* None required for read-only cloning of this public repository.



\### Build Step



Under \*\*Build Steps\*\*, the \*\*Execute shell\*\* option was selected.



The following command was entered:



```bash

sh hello-world.sh

```



Jenkins executes this command from the job's workspace after checking out the repository.



\## 8. Build Execution



The job was executed by selecting \*\*Build Now\*\* on the `HelloWorld` Jenkins job page.



Jenkins retrieved the repository, checked out the `main` branch, and executed the shell script.



\### Console Output



The relevant output from the successful build was:



```text

Cloning repository https://github.com/ishitaxgupta07/devops-sample-code.git

Checking out Revision ... (refs/remotes/origin/main)

Commit message: "Add hello-world.sh"

\+ sh hello-world.sh

Hello, Jenkins!

Finished: SUCCESS

```



The revision identifier and temporary script path may vary between builds.



\## 9. Result



The `HelloWorld` Jenkins job completed successfully.



The Console Output confirmed that:



\- Jenkins cloned the GitHub repository.

\- The `main` branch was checked out.

\- The `hello-world.sh` script was executed.

\- The expected message `Hello, Jenkins!` was printed.

\- The build finished with the status `SUCCESS`.



\## 10. Conclusion



This project demonstrates a basic Jenkins automation workflow using GitHub and a shell script. It shows how Jenkins can retrieve source code from a version-control repository, execute a configured build step, and report the result.



The successful build confirms that the GitHub integration and shell-script execution are working correctly.



\## 11. Future Enhancements



\- Configure a GitHub webhook to trigger builds when code changes.

\- Add Poll SCM to check for new commits periodically.

\- Add automated tests to the build process.

\- Create a Jenkins Pipeline using a `Jenkinsfile`.

\- Add build notifications and reporting.



