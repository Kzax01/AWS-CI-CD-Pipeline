# 🚀Automate, Deliver, Succeed: The CI/CD Journey Begins Here!
![Image 1](https://media.licdn.com/dms/image/v2/D4E12AQEzyGXboJ0Xig/article-cover_image-shrink_720_1280/article-cover_image-shrink_720_1280/0/1730066117374?e=1735776000&v=beta&t=Tey5IpD8OSVOjvqsV29LK7pe637QTmZEg6WcQ40I-3Y)

## 📘 Complete CI/CD Guide: From Theory to Practice

As part of my preparation for the AWS SAA and an upcoming project, I will be implementing a CI/CD solution on AWS. This article will guide us through several crucial points to understand and succeed in this implementation. I will also be sharing my experience and best practices soon! 

On the road to becoming a Cloud Security Engineer! 🎯

---

## 🌟 Introduction:
Automation is at the heart of digital transformation, and one of the pillars of this automation in software development is the use of CI/CD. Whether you're a small startup or a large enterprise, the CI/CD pipeline ensures fast, efficient, and reliable software delivery. It helps minimize human errors and accelerates the time-to-market for new features or fixes.

However, while using CI/CD brings many advantages, it also comes with its share of challenges. It's not enough to simply implement a pipeline; you need to know how to optimize and execute it properly. Inefficient tests, poorly managed secrets, or insecure deployments can quickly transform a powerful tool into a vector of risks.

## 📋 Article Structure:
### Part 1: Fundamentals and Setup:
- 🚀 What is CI/CD?
- 🔄 How does a CI/CD pipeline work?
- 🛠 Which software for which uses in the CI/CD pipeline?
- 📊 DORA metrics and performance measurement - (Not DORA the explorer 😜)
- ❌ Bad practices to avoid in a CI/CD pipeline

### Part 2: Security and Best Practices:
- 🔐 CI/CD vulnerabilities & how to address them
- 💡 Security tips for a robust pipeline

Get ready to dive into the world of secure cloud solutions and deployment automation! 🎯

---

## 🚀 What is CI/CD?
CI/CD is a common practice in software development that stands for Continuous Integration (CI) and Continuous Delivery/Deployment (CD). It automates the different stages of building, testing, and deploying an application to make the process faster, more reliable, and with fewer human errors.
- ➣ CI focuses on frequent integration of code changes into the repository, where each change is validated by automated tests to ensure no new errors are introduced.
- ➢ CD, which can mean either Continuous Delivery or Continuous Deployment, focuses on automating the deployment of changes to production or pre-production environments.

## 🔄 How do CI/CD phases work together?
![Image 2](https://media.licdn.com/dms/image/v2/D4E12AQFAynS-yd-p-Q/article-inline_image-shrink_1500_2232/article-inline_image-shrink_1500_2232/0/1730066117828?e=1735776000&v=beta&t=M3l5Un_ZzPSS5Fe4vX_0W-bJd-WV8fvShS7WwMAG-Xk)

Let's see how these phases interact within a CI/CD pipeline and which steps are crucial for ensuring effective deployment.

1. **Plan:**
   - ➞ This is the starting point. The team uses tools like Jira to plan and track tasks to be completed. Stories or tasks define the work that will be done by developers and what needs to be tested and delivered.
  
2. **Code:**
   - ➞ Developers write code and use versioning tools like GitHub or GitLab. Git branches allow working on different parts of the code without affecting the main branch. Once changes are ready, they're submitted via pull requests or merge requests.

3. **Build:**
   - ➞ Tools like Gradle or Webpack take the source code, compile (for Java for example) or transform (for JavaScript) and generate an executable product. Here, external dependencies are also managed to ensure the project is functional.
   - ➞ This step integrates perfectly into CI/CD pipelines: as soon as code is pushed, the pipeline automatically triggers to start the build phase.

4. **Testing:**
   - ➞ Jest, Playwright, or JUnit are used to automate unit tests or end-to-end tests. Once the code is compiled, these tools test the defined functionalities. If a test fails, the CI pipeline breaks, and the developer must fix the errors before continuing.

5. **Release:**
   - ➞ Tools like Buildkite and Jenkins manage the preparation of artifacts for deployment. They ensure that the version ready for deployment is properly built and tested, and that it's ready to move to the next stage of the CD pipeline.

6. **Deploy:**
   - ➞ Once validated, the code is deployed via tools like Docker, ArgoCD, or AWS Lambda. Deployment can be done in staging (pre-production) or production environments.

7. **Operate:**
   - ➞ Once deployed, the application is managed via orchestrators like Kubernetes or infrastructure as code tools like Terraform. These tools manage scaling, resource distribution, and system resilience.

8. **Monitor:**
   - ➞ Application performance is monitored in production with tools like Prometheus and Datadog. They send alerts in case of performance degradation or outages, allowing teams to react quickly.

---

## 🛠 In-Depth Explanation of Tools Used in CI/CD and Their Relevance:
![Image 3](https://media.licdn.com/dms/image/v2/D4E12AQFKeIMKx6vVng/article-inline_image-shrink_1500_2232/article-inline_image-shrink_1500_2232/0/1730066117591?e=1735776000&v=beta&t=2ZohBHpTShl8E599nVbI6Io2Xfrki4QIIMtlwVmUTys)


In a CI/CD pipeline, each phase relies on specific tools that facilitate automation, code management, testing, deployment, and application monitoring.
💭 You’ve probably seen names like Terraform, Jira, GitHub, and Jenkins; but what exactly are they?

⬇️ Down below a detailed guide on all the key services used in this process and their roles in the CI/CD cycle, complete with concrete usage examples. ⬇️

After reading this, I promise the use of such-and-such software will be much clearer 🎉

---

### ➡️ CI (Continuous Integration):
- **Plan – Jira:**
![Image 4](https://media.licdn.com/dms/image/v2/D4E12AQGzQtkP1uN0XA/article-inline_image-shrink_1500_2232/article-inline_image-shrink_1500_2232/0/1730109494791?e=1735776000&v=beta&t=3I0oE7hfGWOWPFFYrOJo3xLB9RIMdFg2lpE2g2jT8HE)

  ⇨ Jira: This is a project management and task tracking tool widely used to organize work within development teams. It's particularly useful in agile environments, allowing the creation of user stories, bug tracking, and sprint organization.
  - ↬ Example: When a developer receives a new task (ticket) in Jira to fix a bug in the application, they can track this ticket from "To Do" to "In Progress," and then to "Done." This tracking provides complete visibility into the work done.


- **Code – GitHub and GitLab:**
![github](https://media.licdn.com/dms/image/v2/D4E12AQF2RnRoZvS59w/article-inline_image-shrink_1500_2232/article-inline_image-shrink_1500_2232/0/1730108885670?e=1735776000&v=beta&t=Az8fRbNjpOXH_YdDg_5dpMhM8HG8xsuD9Q7ezihIio4) 
  
  - These two services are Git-based code management platforms that enable teams to collaborate on code, manage versions, and automate workflows via CI/CD pipelines.
  - ⇨ GitHub: Very popular, especially in the open-source community. It's often used to host code projects and facilitate collaboration through pull requests.
    - ↬ Example: In an open-source project, a developer submits a pull request with a new feature or bug fix, and other team members can review the code, discuss changes, and merge it once approved.
  - ⇨ GitLab: It offers a more integrated solution for enterprises, with comprehensive CI/CD pipelines and numerous customization options.
    - ↬ Example: On GitLab, whenever a developer pushes code to a branch, a CI pipeline can automatically run tests and build the project without needing external tools like Jenkins.


- **Build – Gradle:**
![Image 5](https://media.licdn.com/dms/image/v2/D4E12AQHcEWsPTZNVKw/article-inline_image-shrink_1000_1488/article-inline_image-shrink_1000_1488/0/1730111386992?e=1735776000&v=beta&t=eCAI5jHrRcraMdOPPKPN0HgOT5bmwq-BoFZnW4ZUKjQ)

  - ⇨ Gradle: A build tool primarily used in Java projects, but can also be utilized for other languages. It manages the compilation of source code, dependency management, and the generation of executable files (like .jar or .war files).
    - ↬ Example: In a Java project, every time a developer pushes code on GitHub, Gradle compiles the code and creates a .jar file ready for testing or deployment.


- **Test – Jest:**
![Image 6](https://media.licdn.com/dms/image/v2/D4E12AQES58o5c3Q2zQ/article-inline_image-shrink_1000_1488/article-inline_image-shrink_1000_1488/0/1730111669872?e=1735776000&v=beta&t=g8NwAgaCKaxR5g9PjjD3aVYsx2GXQdOn--r1xN1JXLY)

  - ⇨ Jest: A testing framework for JavaScript applications, particularly used for testing React components. It allows for the creation of unit tests that verify each function or component returns the correct result.
    - ↬ Example: In a React application, each new component can be tested with Jest to ensure it behaves as expected with different data sets.

---

### Now let's talk about the software that can be used within CD:
#### ➡️ CD (Continuous Delivery/Deployment):

- **Release – Jenkins:**
![Image 7](https://media.licdn.com/dms/image/v2/D4E12AQF5SumWU0NSxA/article-inline_image-shrink_1000_1488/article-inline_image-shrink_1000_1488/0/1730112198787?e=1735776000&v=beta&t=nIIGmo_WHfAHRF1080cAAq0MyEUxasDeUdYz9lwsSUM)

  - ⇨ Jenkins: A very popular tool for orchestrating CI/CD pipelines. It allows you to define build, test, and deployment steps via pipelines.
    - ↬ Example: In a Node.js project, Jenkins can be configured to install dependencies with npm install, run tests with Jest, and automatically deploy the application once tests pass.


- **Deploy – Docker & AWS Lambda:**
![Image 8](https://media.licdn.com/dms/image/v2/D4E12AQELqdxN6z-BwQ/article-inline_image-shrink_1500_2232/article-inline_image-shrink_1500_2232/0/1730114800838?e=1735776000&v=beta&t=ghYoIjd6pQfKutZryWyWN4MCeL9tN3nHecBIUXRo2cs)

  - ⇨ Docker: It allows you to create containers that package the application with all its dependencies so it can run consistently on any machine.
    - ↬ Example: A developer can create a Docker image for a Node.js application and deploy it on a Kubernetes cluster, where each container is replicated and managed automatically.
  - ⇨ AWS Lambda: A serverless computing service where you can run code without managing servers. It’s ideal for functions or microservices that don’t need a permanent infrastructure.
    - ↬ Example: An application deployed on AWS Lambda can be triggered whenever a user uploads a file to an S3 bucket, executing a function to process that file (like resizing it).


- **Operate – Kubernetes and Terraform:**
![Image 9](https://media.licdn.com/dms/image/v2/D4E12AQEcMuZPgdrpqw/article-inline_image-shrink_1500_2232/article-inline_image-shrink_1500_2232/0/1730113487708?e=1735776000&v=beta&t=fIKDI0DPk5uZkGfKR2pdIMLe-e17GKIJ6NrnmOU9ZCw)

  - ⇨ Kubernetes: A container orchestration platform that manages the deployment, scaling, and high availability of containerized applications.
    - ↬ Example: For a large-scale application, Kubernetes manages pods (units of containers), ensuring that if a pod fails, it is automatically restarted. It also balances the load among multiple pods.
  - ⇨ Terraform: An infrastructure-as-code (IaC) tool that allows you to define and provision infrastructure through configuration files. It's used to deploy infrastructure across various cloud providers like AWS, Azure, and Google Cloud.
    - ↬ Example: You can use Terraform to create a complete infrastructure, like an EKS (Elastic Kubernetes Service) cluster on AWS, simply by defining the necessary configuration file.


- **Monitor – Prometheus and Datadog:**
![Image 10](https://media.licdn.com/dms/image/v2/D4E12AQH_sTj5sGXhPQ/article-inline_image-shrink_1500_2232/article-inline_image-shrink_1500_2232/0/1730113868450?e=1735776000&v=beta&t=PeIECKNzPVAwsnrpPGYWp-JmbiXAu8mGBbGbB2SFbDA)

- ⇨ Prometheus: An open-source monitoring system that collects performance metrics from an application (CPU, memory, network usage, etc.). It also allows configuring alerts for when defined thresholds are exceeded.
    - ↬ Example: In a microservices architecture, Prometheus collects metrics from all microservices and allows the team to monitor performance in real-time and detect anomalies quickly.
  
 
 ⇨ Datadog: A monitoring and analytics platform that integrates with numerous services and offers a comprehensive view of an application’s performance.
    - ↬ Example: A web application can be monitored through Datadog to track latency and errors across multiple services, providing dashboards that visualize performance metrics.

🚨 **Note:** I kept only popular used software, but of course there are many more options available that can be utilized in CI/CD processes.

---
## 🔍 **Difference between Continuous Delivery and Continuous Deployment:**  
You may have noticed that I used the term (Continuous Delivery/Deployment) in the title. While they are often confused, it’s crucial to understand their differences. Continuous deployment can be seen as an extension of the continuous delivery concept.
![Image 11](https://media.licdn.com/dms/image/v2/D4E12AQHcVMUFZ78fhQ/article-inline_image-shrink_1500_2232/article-inline_image-shrink_1500_2232/0/1730066117252?e=1735776000&v=beta&t=L3paOEPDn6zz-RUBXlgp7i65_Yk6l_au1WIULSVcWww)


- **Continuous Delivery:** Automates the entire pipeline up to the staging or testing environment. The deployment to production then becomes a manual decision.  
  ➔ **When to use it?** Useful in regulated sectors like finance and healthcare, where a final human validation is required before moving to production.  


- **Continuous Deployment:** Here, each version is automatically deployed through the pipeline, including testing, all the way to production.  
  ➔ **When to use it?** Ideal for startups or tech companies where time to market is crucial, and robust automated testing is already in place.
---
## 📊 **DORA Metrics - DevOps Research & Assessment:**  
DORA metrics have become the standard for measuring DevOps team performance, allowing you to evaluate the efficiency of your CI/CD pipeline and identify areas for improvement.  
![Image 12](https://media.licdn.com/dms/image/v2/D4E12AQG71m3KwiKcjQ/article-inline_image-shrink_1500_2232/article-inline_image-shrink_1500_2232/0/1730066117310?e=1735776000&v=beta&t=MAxpR43w7tC2gU_WlpuXgTYhd6U3qrL0ISMk-5ksHGM)


➔ **Importance of DORA Metrics:** By integrating these metrics into your CI/CD process, you can assess your team's performance and effectively communicate the status of deployments to stakeholders. It also helps you identify weaknesses and implement continuous improvements.

🌟 **Here are the four main DORA metrics we will use in our project:**

1. **Deployment Frequency:**  
   ✦ Elite: Multiple times per day.  
   ✦ High: Between once a day and once a week.  
   ✦ Medium: Between once a week and once a month.  
   ✦ Low: Less than once a month.  
   ☞ This metric indicates how frequently code changes are released into production. A high frequency is often associated with high-performing teams.


2. **Lead Time for Changes:**  
   ✦ Elite: Less than an hour.  
   ✦ High: Between a day and a week.  
   ✦ Medium: Between a month and six months.  
   ✦ Low: More than six months.  
   ☞ This lead time measures how long it takes to go from code to production. A short lead time indicates a quick response to user needs.


3. **Change Failure Rate:**  
   ✦ Elite: 0-15%.  
   ✦ High: 16-30%.  
   ✦ Medium: 31-45%.  
   ✦ Low: >45%.  
   ☞ This measures the percentage of deployments that require a rollback or result in failures. A low failure rate is a sign of code quality.


4. **Time to Restore Service:**  
   ✦ Elite: Less than an hour.  
   ✦ High: Less than a day.  
   ✦ Medium: Less than a week.  
   ✦ Low: More than a week.  
   ☞ This metric indicates how long it takes to restore service after a failure. A quick restoration time is essential for maintaining user trust.
---
## ❌ **Common Pitfalls to Avoid in a CI/CD Pipeline:**  
When setting up a CI/CD pipeline, it’s crucial to recognize common pitfalls that can jeopardize the success of your integration and deployment strategy. Here are some frequent mistakes and how to avoid them:

- **Insufficient or Unautomated Testing:** Code errors might not be caught until production.  
  ✅ **Solution:** Integrate unit tests, integration tests, and end-to-end tests into the pipeline.
  
- **Overly Long CI/CD Pipeline:** This can slow down the delivery process, encouraging developers to skip tests.  
  ✅ **Solution:** Optimize the pipeline to reduce execution times.

- **Lack of Automatic Rollback:** Without a rollback mechanism, a faulty version can impact users.  
  ✅ **Solution:** Automate canary deployments and rollbacks.

- **Ignoring Security in the Pipeline:** Neglecting vulnerabilities can expose you to attacks.  
  ✅ **Solution:** Integrate security tools and automated verification steps.

- **Incorrect Environment Configuration:** Differences between environments can cause failures.  
  ✅ **Solution:** Use containers like Docker to ensure uniformity.

- **Not Monitoring Deployments:** This can delay problem detection.  
  ✅ **Solution:** Implement monitoring tools to track post-deployment performance.
---
## 🎯 **CONCLUSION AND KEY TAKEAWAYS:**

![Image 13](https://media.licdn.com/dms/image/v2/D4E12AQFUrVHex31YCQ/article-inline_image-shrink_1500_2232/article-inline_image-shrink_1500_2232/0/1730066117324?e=1735776000&v=beta&t=5fr-P-PYyS_p0ILphcCx-AOpZFdrPjel9CG6LTEFwYE)

Phew, that was intense, but we made it through! Kudos to you for sticking with me till the end of this first part on CI/CD pipelines in AWS! 🎉

Indeed, this is a significant step toward automation and efficiency in our development processes. Understanding and implementing CI/CD is essential for accelerating our deliveries while maintaining top-notch quality. Let’s not forget: securing these processes is equally crucial. Rapidly deploying applications is only valuable if we can protect them from threats.

### 🔥 **Summary of Key Points:**
➡ CI/CD is vital for improving speed and quality of deliveries.  
➡ Automating tests and deployments reduces human errors.  
➡ Prioritizing security is fundamental to protect our data.  
➡ Various tools exist, each with its specifics.  
➡ Staying informed and adaptable is crucial in a rapidly evolving tech landscape.  

Are you ready to explore together how to secure your deployments while keeping them agile? In the next part, we will dive into the exciting challenges of security in CI/CD pipelines. 🔒♾️

I look forward to hearing your feedback and thoughts on this article! If you think it could help someone, feel free to share it on your networks!  
Thank you.  
    - Kenza
----
📚 **Ressources Used:**
- Atlassian CI/CD Guide - Atlassian  
- AWS CI/CD Documentation - AWS Documentation  
- DevOps CI/CD Guide - DevOps.com  
- Intro to CI/CD - Codecademy  
- Understand DORA Metrics - DORA Guide  
- Continuous Delivery VS Continuous Deployment Article - Martin Fowler  

🛠️ **Tools and Tutorials:**
➡️ **CI (Continuous Integration):**
- Jira Official Site: [Jira](https://www.atlassian.com/software/jira)  
- Confluence Official Site: [Confluence](https://www.atlassian.com/software/confluence)  
- GitHub Official Site: [GitHub Documentation](https://docs.github.com/en)  
- GitLab Official Site: [GitLab Documentation](https://docs.gitlab.com/)  
- Gradle Official Site: [Gradle Guide](https://gradle.org/guides/)  
- Jest Official Site: [Jest Guide](https://jestjs.io/docs/getting-started)

➡️ **CD (Continuous Delivery/Deployment):**
- Jenkins Official Site: [Jenkins](https://www.jenkins.io/)  
- Docker Official Site: [Docker Documentation](https://docs.docker.com/)  
- AWS Lambda Official Site: [AWS Lambda Developer Guide](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html)  
- Kubernetes Official Site: [Kubernetes Documentation](https://kubernetes.io/docs/home/)  
- Terraform Official Site: [Terraform Blog](https://www.terraform.io/blog)  
- Prometheus Official Site: [Prometheus Documentation](https://prometheus.io/docs/introduction/overview/)  
- Datadog Official Site: [Monitoring 101 with Datadog](https://www.datadoghq.com/blog/monitoring-101-with-datadog/)  
----

### 💬 Let's Connect!
Thank you for taking the time to read through my article! If you'd like to connect, feel free to reach out on LinkedIn: [Kenza S. - Cyber & Cloud](https://www.linkedin.com/in/kenza-s-cyber-cloud)

### ☁️  I look forward to connecting with you!
