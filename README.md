# GitHub Setup and Commands

## View Configured Name and Email
To see the currently configured Git username and email (if any):
```bash
git config --global --list
```

## Set Up GitHub Email and Username Locally
### Set Username:
```bash
git config --global user.name "Your Name"
```
### Set Email:
```bash
git config --global user.email "useremail@gmail.com"
```

## Push Project from Local to Remote Repository
### Initialize Git and Push to Remote:
1. **Initialize Git in your project folder:**
   ```bash
   git init
   ```
2. **Add all files to staging:**
   ```bash
   git add .
   ```
3. **Commit your changes:**
   ```bash
   git commit -m "Initial commit"
   ```
4. **Rename the default branch to `main` (optional):**
   ```bash
   git branch -M main
   ```
5. **Add the remote repository:**
   ```bash
   git remote add origin <repository-link>
   # Use SSH link for better security (recommended)
   ```

### Generate and Add SSH Key to GitHub
1. **Generate an SSH key (if not already created):**
   ```bash
   ssh-keygen -o -t rsa -b 4096 -C "your_email@example.com"
   ```
   - Follow the prompts to save the key (default location is recommended).
   - Enter a passphrase (optional but recommended).

2. **Copy the SSH public key:**
   ```bash
   cat ~/.ssh/id_rsa.pub
   ```
   - Copy the entire output.

3. **Add the SSH key to your GitHub account:**
   - Log in to your GitHub account.
   - Go to **Settings > SSH and GPG keys**.
   - Click **New SSH key**.
   - Paste the copied key into the **Key** field and give it a **Title**.
   - Click **Add SSH key**.

4. **Test the connection:**
   ```bash
   ssh -T git@github.com
   ```
   - You should see a success message if the setup is correct.

### Push to Remote:
```bash
git push -u origin main
```

## View Commit and Tag History
- **View Commit List:**
  ```bash
  git log
  ```
- **View All Tags:**
  ```bash
  git tag
  ```

## Create and Push a Tag
### Create a Tag:
```bash
git tag v1.1 -m "Version 1.1 release"
```
### Push the Tag:
```bash
git push origin v1.1
```

## Delete a File from Git
### Remove File from Git:
```bash
git rm --cached filename.txt
```
- Then delete the file from the working directory manually.

## Create and Switch to a Branch
### Create a Branch:
```bash
git checkout -b branch_name
# Or
git switch -c branch_name
```
### Switch to an Existing Branch:
```bash
git switch branch_name
```

## View All Branches
- **Local Branches:**
  ```bash
  git branch
  ```
- **Include Remote Branches:**
  ```bash
  git branch --all
  ```

## Delete a Branch
```bash
git branch -d branch_name
```

## Merge Two Branches
- **Recommendation:** Pull changes before merging.
- Merge:
  ```bash
  git merge branch_name
  ```
