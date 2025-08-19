Creating and uploading a GitHub repository from Ubuntu is straightforward. Follow these steps:

### **Step 1: Install Git (if not installed)**

Open a terminal and run:

```bash
sudo apt update
sudo apt install git -y
```

Verify installation:

```bash
git --version
```

### **Step 2: Configure Git (if not already configured)**

Set up your name and email:

```bash
git config --global user.name "Your Name"
git config --global user.email "your-email@example.com"
```

### **Step 3: Create a GitHub Repository**

1. Go to [GitHub](https://github.com/) and log in.
2. Click the "+" icon in the top-right and select **New repository**.
3. Enter a repository name and optional description.
4. Choose visibility (**Public** or **Private**).
5. Click **Create repository**.

### **Step 4: Create a Local Repository in Ubuntu**

Navigate to the folder where you want to create the project:

```bash
cd /path/to/your/project
```

Initialize Git in the folder:

```bash
git init
```

Add a README file:

```bash
echo "# My Project" > README.md
```

Stage and commit files:

```bash
git add .
git commit -m "Initial commit"
```

### **Step 5: Connect Local Repository to GitHub**

Copy the repository URL from GitHub and run:

```bash
git remote add origin https://github.com/your-username/your-repository.git
```

Verify the remote:

```bash
git remote -v
```

### **Step 6: Push the Code to GitHub**

Run:

```bash
git branch -M main
git push -u origin main
```

If prompted, enter your GitHub username and password or use a **Personal Access Token** (if GitHub requires it).

### **Step 7: Verify on GitHub**

Go to your GitHub repository page and refresh to see your uploaded files.

Let me know if you need help with authentication or setting up SSH keys! 🚀