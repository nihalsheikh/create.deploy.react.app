# Creating website app from React using vite

**some usefull websites:**<br>
to create your own logo: `logo.com`<br>
for 3D Models: `sketchfab`<br>
for email: `emailjs`
<br>
<br>

**Creating React app with vite:** <br><br>
run this cmds: <br><br>
```
npm create vite@latest ./ -- --template react<br>

npm install -D tailwindcss<br>

npx tailwindcss init<br>
```

next down one is a full cmd, don't spilt it in half:<br><br>
```
npm install --legacy-peer-deps @react-three/fiber @react-three/drei maath react-tilt react-vertical-timeline-component @emailjs/browser framer-motion react-router-dom<br>

npm install --legacy-peer-deps -D tailwindcss postcss autoprefixer<br>

npx tailwindcss init -p<br>

npm install --legacy-peer-deps three<br>

npm run dev<br><br>
```

## After building app, next steps to deploy your website/app to github pages:<br><br>

1. run this cmd: *don't forget to add `your own github username` and `repository_name`* <br>
```
git clone <repository link example: "git@github.com:<username>/<repository>.git"><br>
```
2. open terminal & move into this repository usind cd.<br>

3. copy all the files you created for the React App or create a new app from here.<br>

4. install all the dependencies once again using:<br>
`npm i`

5. open vs code in this folder using:<br>
`code .`

6. after opening vs code, run this cmd:<br>
`npm run dev`

7. configure vite.config.js file, in this file add this cmd after plugins: <br>
`base: '/<github_repository_name>'`

8. configue package.json file, in this file, add this cmds in scripts:<br>
`"deploy": "gh-pages -d dist"`
<br><br>
save all the files<br><br>

now using terminal in vs code, create the file with cmd:
`touch deploy.sh`

paste the following in deploy.sh file
////////////////Deploy.sh file start here<do not add this line>
```
#!/usr/bin/env sh

# abort on errors
set -e

# build
npm run build

# navigate into the build output directory
cd dist

# place .nojekyll to bypass Jekyll processing
echo > .nojekyll

# if you are deploying to a custom domain
# echo 'www.example.com' > CNAME

git init
git checkout -B main
git add -A
git commit -m 'deploy'

# if you are deploying to https://<USERNAME>.github.io
# git push -f git@github.com:<USERNAME>/<USERNAME>.github.io.git main

# if you are deploying to https://<USERNAME>.github.io/<REPO>
# git push -f git@github.com:nihalsheikh/<repository_name>.git main:gh-pages

cd -
```
/////////////////Deploy.sh  file end here<do not add this line><br>

9. in the above deploy.sh file edit the last '# comment', paste your own github username and repository<br>

10. save all file once again<br><br>

11. run this cmds: 
```
git status
git add .
git commit -m "deply test"
git push
```
<br> 
12. wait for a min and refresh your repository, once you have everything then do the following cmds:<br>

`npm install gh-pages --save -dev`<br><br><br>

ignore the error<br><br>

13. run cmds again one at a time:<br>
```
git status
git add .
git commit -m "update"
git push
```
<br><br>
14. after you are done with above cmds, you are ready to build:<br>
run this cmds:<br>
```
npm run build
npm run deploy
```
<br>
done. wait for a few minutes, refresh your GitHub Page<br>
you're github page should be ready...

