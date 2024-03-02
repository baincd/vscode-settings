# Create New TypeScript project

```bash
git init && git commit --allow-empty -m 'Git Repo Initialized' &&

curl -sL https://www.toptal.com/developers/gitignore/api/node,visualstudiocode > .gitignore &&
git add -A && git commit -m 'Create .gitignore for Node' &&

npm init --yes &&
git add -A && git commit -m 'Create new node project' &&
npm install --save-dev typescript tsc-watch &&
git add -A && git commit -m 'Add TypeScript' &&

npm pkg set 'type=module' &&
npm pkg set scripts.start="tsc-watch --onsuccess 'node dist/index.js'" &&
echo '{'                                 > tsconfig.json &&
echo '    "compilerOptions": {'         >> tsconfig.json &&
echo '        "outDir": "./dist",'      >> tsconfig.json &&
echo '        "rootDir": "./src",'      >> tsconfig.json &&
echo '        "target": "ES6",'         >> tsconfig.json &&
echo '        "module": "Node16"'       >> tsconfig.json &&
echo '    }'                            >> tsconfig.json &&
echo '}'                                >> tsconfig.json &&
git add -A && git commit -m 'Configure TypeScript' &&

mkdir src &&
echo 'console.log("Hello World")' > src/index.ts
```
