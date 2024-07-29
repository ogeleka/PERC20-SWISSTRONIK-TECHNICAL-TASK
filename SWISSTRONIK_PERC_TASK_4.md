# Guide to Complete Swisstronik PERC Task 4 🧵

For convenience, it is better to do the first and second technical tasks before doing this. You have to get test tokens and understand how to find your way around Codespace, which I won't be covering here. @dxzenith did that already, link below:
[Swisstronik Testnet Guide](https://github.com/dxzenith/Swisstronik-Testnet?tab=readme-ov-file).

## Using Codespace
1. Navigate to your GitHub repository.
2. Click on the "Code" button (green button near the top-right).
3. Select the "Codespaces" tab.
4. Click "Create codespace on main" to launch a new Codespace.

Once your Codespace is ready, you'll see a VS Code-like interface in your browser. This is where we'll perform all our tasks.

## Using the Terminal in Codespaces

The terminal in Codespaces is your command center for executing the necessary commands. Here's how to use it effectively:

1. Look for the "Terminal" option in the top menu bar of your Codespace.
2. Click on it and select "New Terminal" to open a terminal window.
3. The terminal will appear at the bottom of your screen, ready for your commands.

When you see a command in this guide, simply type or copy-paste it into the terminal and press Enter to execute.

After pasting this command and pressing Enter, you should see response printed in your terminal.

Now that you're set up, let's dive into the Swisstronik PERC Task 4!

## Task Steps

1️⃣ **Clone the Repository**

Open your terminal in Codespace and type:

```bash
git clone https://github.com/ogeleka/PERC20-SWISSTRONIK-TESTNET.git
```
This command downloads the project files to your computer. 📂


**2️⃣ Navigate to Project Folder**

Go into the project folder with:
```bash
cd PERC20-SWISSTRONIK-TESTNET
```

**3️⃣ Copy Environment File**

Copy the sample environment file by typing:
```bash
cp 'dot env-sample' .env
```

**4️⃣ Edit Environment File**

Open the file to edit:
```bash
nano .env
```
Replace PRIVATE_KEY=input here with your private key. 🔑
it should look like this PRIVATE_KEY=237484885884992929jrj44n54 delete those stuff written in front of it.
To save, press Ctrl + X, then Y, then Enter. ✅

**5️⃣ Install Dependencies**

Install the necessary libraries:
```bash
npm install
```

**6️⃣ Compile the Project**

Compile the smart contract code:
```bash
npx hardhat compile
```
**7️⃣ Deploy the Contract**

Deploy the smart contract to the Swisstronik network:
```bash
npx hardhat run scripts/deploy.js --network swisstronik
```
Copy the deployed contract address shown in the output and save it some where. 📋

**8️⃣ Update Mint Script**

Edit the mint script to use your deployed contract address:
```bash
nano scripts/mint.js
```
delete the deployed address in the script and input yours.

**9️⃣ Run Mint Script**

Run the mint script:
```bash
npx hardhat run scripts/mint.js --network swisstronik
```
Copy the output shown and save it some where. u will need it later.

**1️⃣0️⃣ Update Transfer Script**

Edit the transfer script to use your deployed contract address:

```bash
nano scripts/transfer.js
```
delete the deployed address in the script and input yours.

**1️⃣1️⃣ Run Transfer Script**

Run the transfer script:
```bash
npx hardhat run scripts/transfer.js --network swisstronik
```
Copy the transaction hash shown in the output. 📋

**1️⃣2️⃣ Clean Up Environment File**

Remove your public key from the environment file:
```bash
nano .env
```
Delete your public key, then save and exit by pressing Ctrl + X, then Y, then Enter. ✅

## 1️⃣3️⃣ Push to GitHub

**change the 3rd and 4th line to your github username, and email**
```bash
sudo apt update
sudo apt install git
git config --global user.name "UR_USERNAME"
git config --global user.email "UR_EMAIL"
git init
git add .
git commit -m "Initial commit"
```
**Remove the existing origin remote and add your own:**
```bash
git remote remove origin
```
**Add a new remote repository: make sure you edit this properly**
you need, ur githubuser name your github token, and the remote repository URL
```bash
git remote add origin https://your_github_username:your_github_token@github.com:your_username/your_repo.git
```
to generate github token: log in ur github homepage; go to setting; Developer settings; Click on Personal access tokens under Access tokens.
Click the Generate new token button; Enter a Note to describe the token's purpose;Select the Scopes or permissions you need. select repo for repository access);Click Generate token.;

The URL **https://github.com/your_username/your_repo.git** is the remote repository URL on GitHub.Create a Repository: Log in to GitHub, go to the new repository page, and fill in the repository details such as name(any of you choice) and description(anything you want). Click Create repository.

Obtain the Repository URL: After creating the repository, you'll be redirected to the repository page. Click the Code button and copy the URL under the HTTPS tab.

Use the URL: This URL, in the format https://github.com/your_username/your_repo.git, is used to clone or set the remote origin for your local Git repository. it will look like this **git@github.com:chukwuyenum1/swisstronik04.git**

**And your complete remote repository should look something like this**


**git remote add origin https://chukwuyenum1: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gitgit@github.com:chukwuyenum1/swisstronik04.git**



**Check the remote repository with:**
```bash
git remote -v
```
you will see ur remote repository with fetch and push if you do everything right.

**Push your changes to GitHub:**
```bash
git push origin main
```

just as you did with the first 2 task copy those stuff i ask you to save. go and summit them on ur testnet page.


**that's all for now do well to follow😉**
