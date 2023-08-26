# ✨GitHub

## GitHub is a platform that offers

- **Version Control:** It helps individuals and teams keep track of changes to their code projects over time.

- **Collaboration:** GitHub provides tools for developers to work together on projects. These tools include features like:

- **Code Hosting:** Storing and managing code repositories online.
  - **Pull Requests:** A way to propose and review changes before merging them.
  - **Issue Tracking:** Tracking and managing tasks, bugs, and discussions related to the project.

- **Widely Used:** GitHub is widely adopted by developers to collaborate on both open-source and private software projects.

## Setting Up SSH Key with GitHub on CentOS 7

> SSH keys provide a secure way for your computer to communicate with GitHub without repeatedly entering your credentials.

### Here's how to establish this connection

- #### Generate an SSH Key Pair

    Start by generating a pair of cryptographic keys – a private key and a corresponding public key. The private key remains on your computer, while the public key is shared with GitHub.

    ```bash
    ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
    ```

    This creates a new SSH key, using the provided email as a label.

    ```bash
    > Generating public/private ALGORITHM key pair.
    ```

- #### Adding your SSH key to the ssh-agent

    Start the ssh-agent in the background.

    ```bash
    $ eval "$(ssh-agent -s)"
    > Agent pid 12345
    ```

    Add your SSH private key to the ssh-agent.

    ```bash
    ssh-add ~/.ssh/id_rsa
    Identity added: /home/user/.ssh/id_rsa (/home/user/.ssh/id_rsa)
    ```

- #### Add Public Key to GitHub

   Register the public key with your GitHub account. This authenticates your computer. When your computer initiates communication with GitHub, it presents the public key, enabling GitHub to verify the connection.

    Copy the SSH public key to your clipboard.

    ```bash
    $ cat ~/.ssh/id_ed.pub
    # Then select and copy the contents of the id_ed12345.pub file
    # displayed in the terminal to your clipboard
    ```

- #### Adding a new SSH key to your account

    **Access GitHub Settings**
    > Log in to your GitHub account and go to "Settings" by clicking on your profile picture in the upper-right corner, then selecting "Settings".

    **SSH and GPG Keys:**
    > In the left sidebar, click on "SSH and GPG keys".

    **Add New SSH Key**
    > Click on the "New SSH key" button.

    **Title and Key:**
    > Give your SSH key a title to identify it (e.g., "Home Laptop"). Paste the copied public key into the "Key" field.

    **Add Key:**
    > Click the "Add SSH key" button to save the key.

    **Confirm Password:**
    > If prompted, enter your GitHub password to confirm the action.

    **SSH Key Added:**
    > Once added, the new SSH key will appear in the list of keys associated with your account.

- #### Test Connection

    > To ensure everything is set up correctly, use the `ssh -T git@github.com` command in your terminal to test the SSH connection. You should receive a message confirming your authentication.

    ```bash
    ssh -T git@github.com
    Hi Kingdomkush! You've successfully authenticated, but GitHub does not provide shell access.
    ```

#### Your new SSH key is now associated with your GitHub account, enabling secure and convenient interactions between your computer and GitHub repositories

## Cloning a Repository

```css
> Cloning a repository means making a copy of a project from a place like GitHub to your own computer. 
>It's like getting a copy of someone's code to work on or use. Cloning gives you all the code and history, so you can start working or exploring right away.
```

### Terminal

```bash
git clone git@github.com:Kingdomkush/class.git

Cloning into 'class'...
Warning: Permanently added the ECDSA host key for IP address '1.1.1.1' to the list of known hosts.
remote: Enumerating objects: 134, done.
remote: Counting objects: 100% (134/134), done.
remote: Compressing objects: 100% (97/97), done.
remote: Total 134 (delta 17), reused 75 (delta 10), pack-reused 0
Receiving objects: 100% (134/134), 21.28 KiB | 0 bytes/s, done.
Resolving deltas: 100% (17/17), done.
```
