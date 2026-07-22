# Node.js : Quick References

## Runtime

```bash
node --version
node app.js
node --watch app.js
node --inspect app.js
```

## NPM

```bash
npm init -y
npm install
npm install PACKAGE
npm install --save-dev PACKAGE
npm run SCRIPT
npm outdated
npm audit
```

## Modules

```javascript
import fs from "node:fs/promises";
const data = await fs.readFile("file.json", "utf8");
const parsed = JSON.parse(data);
```
