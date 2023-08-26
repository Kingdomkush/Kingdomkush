# Jenkins

Jenkins is like a helpful robot for software developers. It handles tasks such as:

- Putting your code together
- Testing if it works
- Preparing it for use

Instead of you repeatedly doing these tasks, Jenkins automates them. This not only prevents mistakes but also saves you valuable time.

Jenkins also works seamlessly with tools that keep track of changes in your code. This improves teamwork among developers by promoting efficient collaboration.

Moreover, when you set up specific ways of doing things with Jenkins, it ensures that your software is always in good shape. This becomes crucial when you're working swiftly and want everything to go smoothly.

## Setting Up Jenkins on CentOS 7

Setting up a Jenkins server on CentOS 7 involves a series of steps.

1. **Prepare Server**
   Begin by having a CentOS 7 machine ready. This could be a virtual machine or a physical server.

2. **Install Java**
   Jenkins requires Java to run. You'll need to install it using these commands:

   ```bash
   sudo yum update
   sudo yum install java-1.8.0-openjdk
   ```

3. **Add Jenkins Repository**
    Jenkins isn't in the default CentOS repositories. You'll need to add its repository using these commands:

      ```bash
   sudo wget -O /etc/yum.repos.d/jenkins.repo http://pkg.jenkins-ci.org/redhat-stable/jenkins.repo
   sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
   ```

4. **Install Jenkins**
    The following command lets you install Jenkins

    ```bash
    sudo yum install jenkins
    ```

5. **Start jenkins**
    Initiate the Jenkins service and set it to start automatically during boot:

    ```bash
    sudo systemctl start jenkins
    sudo systemctl enable jenkins
    ```

6. **Access Web Interface:**
   Jenkins is managed through a web interface. Open your browser and go to
   > `http://your-server-ip:8080`.
7. **Unlock Jenkins:**
   To ensure security, Jenkins requires an initial admin password. Retrieve it by running:

   ```bash
   sudo cat /var/lib/jenkins/secrets/initialAdminPassword
   ```

8. **Install Plugins:**
   Jenkins offers various plugins for different functionalities. Choose the option to "Install suggested plugins" during setup.

9. **Create Admin User:**
   After plugins are installed, create an admin user with a username and password. This account is used to access Jenkins.cd
