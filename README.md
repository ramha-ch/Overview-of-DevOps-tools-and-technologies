# Overview-of-DevOps-tools-and-technologies

🔍 What is DevOps?

DevOps is a way of working where developers and operations teams work together to build, test, and launch software faster and better.
Before DevOps, developers made the app and gave it to the operations team to deploy. If something went wrong, both teams blamed each other. There was poor communication and slow problem-solving.
DevOps is the bridge between both teams. It helps them work as one, from writing code to running it live.

When a developer creates an app and gives it to the operations team for deployment,
and if an error occurs during deployment,
the operations team blames the development team, and vice versa.
This issue happens again and again.
There is a huge gap in feedback between both teams.
So, to fill this gap, a new concept called DevOps was introduced.
DevOps acts as a bridge and works for both the development and deployment teams.
The developer builds the code and tests it — this is called Continuous Integration (CI).
The operations team releases and deploys the app — this is called Continuous Deployment (CD).


WHY NEED 
	→ To ensure smooth and error-free application launches
	→ To improve efficiency and increase the speed of development and deployment
	→ To enhance overall product quality through continuous testing and feedback
	
CI - CD PIPELINE EXPLANATION
CODE 
Write the code of full application
TO BUILD
To run the code in the form of app.js, app.exe, or other executable files on systems like Linux,
the code must first be converted into an executable form.
You need tools like:
	•  Gradle
	•  Maven
These tools convert code from text form into binary executable files — this process is called building.
A build process often uses scripts like:

bash
./build.sh

GITHUB
For the development team, GitHub is used to write and manage the application's code.
When you want to share this code with the world, GitHub is the platform used to do that
Now, as our application requires many new features, we scale out our development team by adding more developers.
To ensure all team members can collaborate efficiently in one place, we use GitHub as a shared platform.
GitHub helps developers write, review, manage, and track code together in real time.
It also keeps a version history, so changes are safe, and team members can easily contribute without conflicts.
To allow everyone to collaborate on a shared codebase, we use platforms like GitHub, GitLab, and Bitbucket.
Using Git with these platforms, developers can easily contribute to the project with commands like:

# Clone the repository to local system
git clone https://github.com/your-team/your-project.git

# Create a new feature branch
git checkout -b feature/new-feature

# Add and commit changes
git add .
git commit -m "Add new feature"

# Push changes to remote repository
git push origin feature/new-feature

# Create a pull request (on GitHub/GitLab/Bitbucket web interface)
# as for GitHub
git push

TESTING
Before deploying any application, we must test the build thoroughly.
This helps us make sure the code works as expected, passes all test cases, and does not break any existing features.
Automated testing is often used at this stage as part of the CI (Continuous Integration) process.
TOOLS likek azure ,Puppeteer

Continuous Testing Integration
Integrates tests into CI/CD pipelines.
	• Jenkins (with plugins)
	• GitLab CI
	• GitHub Actions

Deployment CD
Docker 
Create a Docker Image After Build and Testing
Once your code is built and tested (using CI tools), it’s packaged into a Docker image. The image is a snapshot of the application and its environment, including the operating system, libraries, and configuration files needed for the app to run.

Example Dockerfile:

# Use a base image
FROM node:14

# Set the working directory inside the container
WORKDIR /app

# Copy the package.json and install dependencies
COPY package*.json ./
RUN npm install

# Copy the rest of the application code into the container
COPY . .

# Expose the port the app will run on
EXPOSE 3000

# Start the application
CMD ["npm", "start"]

This will create app by using (.) current directory 

OPERATE
Container Orchestration 
Imagine your app is running in containers, and you're handling a match like Pakistan vs Afghanistan, which doesn't have many users. But when it’s a high-profile match like Pakistan vs India, millions of users start watching, and your app might not be able to handle the load.
Even though you have containers running your app, when a lot of users come in, you need more servers to run more containers to handle the extra traffic. Without enough servers, your app might slow down or crash.
This is where Kubernetes helps. It automatically adds more containers and can even add more servers when the number of users increases. So, when the traffic spikes, Kubernetes adjusts everything to make sure your app can still handle all the users smoothly without any issues.
In simple terms, Kubernetes helps you scale up your containers and servers automatically, so your app keeps running fast and efficiently, even when millions of people are using it at once.

Terraform:
Infrastructure as Code (IaC)
Provisioning Infrastructure: This means setting up the basic resources you need to run your application, like servers, databases, and networks. It's like building the foundation of a house before you decorate it.
Terraform is a tool that helps you manage your cloud resources (like servers, databases, etc.) using code. Instead of manually setting up things like servers, you write code, and Terraform automatically creates and manages everything for you.

Why Use Terraform?
	1. Write simple code to set up your infrastructure, like creating a server.
	2. Terraform works across platforms like AWS, Azure, Google Cloud, and more.
	3.  Terraform ensures your setup is always the same, preventing mistakes.
	4.  It automatically creates, updates, or deletes resources based on your code.


	▪ You write a simple configuration file.
	▪ Terraform reads the code and sets up the resources for you.
	▪  If you update your code, Terraform automatically updates the resources.

Terraform is used for provisioning infrastructure, while Ansible is used for configuring and managing that infrastructure after it's created. Terraform handles resource creation, and Ansible handles application deployment and system configuration.
Once the resources (like servers) are set up by Terraform, Ansible is used to configure them. This means installing software, setting up services, and making sure everything is working properly.

Monitoring 

Prometheus:
Prometheus is a monitoring and alerting toolkit that collects and stores metrics (like CPU usage, memory, disk space, and more) from your applications and infrastructure.
It scrapes data from various sources (like servers, databases, or services) at regular intervals and stores it in a time-series database.

Grafana:
Grafana is a visualization tool that connects to Prometheus (and other data sources) and helps you create dashboards to display your metrics in a way that's easy to understand.

![image](https://github.com/user-attachments/assets/222ce0b9-8fa1-4977-81f2-135e5db48c5f)
