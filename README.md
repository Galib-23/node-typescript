*1. First run this command to initiate the **package.json** file*
```
npm init -y
```
*2. Now configure the **tsconfig.json** file as like this:*
```javascript
{
    "compilerOptions": {
        "module": "NodeNext",
        "moduleResolution": "NodeNext",
        "baseUrl": "src",
        "outDir": "dist",
        "sourceMap": true,
        "noImplicitAny": true,
    },
    "include": ["src/**/*"]
}
```
*3. Configure the **nodemon.json** file for constantly watching the ./src/index.ts file*
```json
{
    "watch": ["src"],
    "ext": ".ts, .js",
    "exec": "ts-node ./src/index.ts"
}
```
*4. Install the following dependencies*
```bash
npm i -D express body-parser cookie-parser compression cors
```
*5. Install the types for the dependencies*
```bash
npm i -D @types/express @types/body-parser @types/cookie-parser @types/compression @types/cors
```
