mkdir fedinsem
cd fedinsem
git init
echo function greet() { console.log('Hello from main branch'); } > App.js
git add App.js
git commit -m "Initial commit with greet() function"
git checkout -b feature1
echo function greet() { console.log('Hello from Alice feature'); } > App.js
git add App.js
git commit -m "Alice updates greet() in feature1"
git checkout master
git checkout -b feature2
echo function greet() { console.log('Hello from Bob feature'); } > App.js
git add App.js
git commit -m "Bob updates greet() in feature2"
git checkout master
git merge feature1
git merge feature2
git add App.js
git commit -m "Resolved merge conflict between feature1 and feature2"
git remote add origin https://github.com/<your-username>/fedinsem.git
git branch -M main
git push -u origin main
git push -u origin feature1
git push -u origin feature2
