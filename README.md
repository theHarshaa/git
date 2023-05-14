# git

### …or create a new repository on the command line<br>
   
   
            echo "# git" >> README.md
            git init
            git add README.md
            git commit -m "first commit"
            git branch -M main
            git remote add origin https://github.com/theHarshaa/git.git
            git push -u origin main
    
### …or push an existing repository from the command line<br>
    
    
            git remote add origin https://github.com/theHarshaa/git.git
            git branch -M main
            git push -u origin main
 
# GitHub Pages
Note: this feature is available with <code>react-scripts@0.2.0</code> and higher.

## Step 1: Add <code>homepage</code> to <code>package.json</code>
### The step below is important!

### If you skip it, your app will not deploy correctly.

Open your <code>package.json</code> and add a <code>homepage</code> field for your project:

            "homepage": "https://myusername.github.io/my-app",
or for a GitHub user page:

             "homepage": "https://myusername.github.io",
or for a custom domain page:

              "homepage": "https://mywebsite.com",
Create React App uses the <code>homepage</code> field to determine the root URL in the built HTML file.

## Step 2: Install <code>gh-pages</code> and add <code>deploy</code> to <code>scripts</code> in <code>package.json</code>
Now, whenever you run <code>npm run build</code>, you will see a cheat sheet with instructions on how to deploy to GitHub Pages.

To publish it at https://myusername.github.io/my-app, run:

              npm install --save gh-pages
Alternatively you may use <code>yarn</code>:

              yarn add gh-pages
Add the following scripts in your <code>package.json</code>:

              "scripts": {
          +   "predeploy": "npm run build",
          +   "deploy": "gh-pages -d build",
              "start": "react-scripts start",
              "build": "react-scripts build",
The <code>predeploy</code> script will run automatically before <code>deploy</code> is run.

If you are deploying to a GitHub user page instead of a project page you'll need to make one additional modification:

Tweak your <code>package.json</code> scripts to push deployments to <strong>master</strong>:
              
                "scripts": {
                "predeploy": "npm run build",
             -  "deploy": "gh-pages -d build",
             +  "deploy": "gh-pages -b master -d build",
## Step 3: Deploy the site by running <code>npm run deploy</code>
Then run:

                npm run deploy
## Step 4: For a project page, ensure your project’s settings use <code>gh-pages</code>
Finally, make sure <strong>GitHub Pages</strong> option in your GitHub project settings is set to use the <code>gh-pages</code> branch:


<img width="516" alt="HUjEr9l" src="https://user-images.githubusercontent.com/124580382/236830307-be7c1784-fe98-40f5-b766-74f2a6110203.png">
gh-pages branch setting<br>

## Step 5: Optionally, configure the domain
You can configure a custom domain with GitHub Pages by adding a <code>CNAME</code> file to the <code>public/</code> folder.

Your CNAME file should look like this:

                mywebsite.com
