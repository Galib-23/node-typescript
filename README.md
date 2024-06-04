# Creating a Node.js server with Express and Typescript
<br>

***1.** First run this command to initiate the **package.json** file*
```
npm init -y
```
***2.** Now configure the **tsconfig.json** file as like this:*
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
***3.** Configure the **nodemon.json** file for constantly watching the ./src/index.ts file*
```json
{
    "watch": ["src"],
    "ext": ".ts, .js",
    "exec": "ts-node ./src/index.ts"
}
```
***4.** Install the following dependencies*
```bash
npm i -D express body-parser cookie-parser compression cors
```
***5.** Install the types for the dependencies*
```bash
npm i -D @types/express @types/body-parser @types/cookie-parser @types/compression @types/cors
```
***6.** Create **src** folder and inside create file named **index.ts** for the entry point of server.*
<br>
<br>

###  body-parser vs express :
<hr>

Previously we used body-parser for parsing body data from request. But now it is a part of express. So, rather using:
```typescript
app.use(bodyParser.json());
```
we can simply use:
```typescript
app.use(express.json());
```

<br>
<br>

***7.** Now Let's install **mongoose** for schema validation for mongoDB*
```bash
npm i mongoose
```

***8.** Now Let's go to mongoDB and create a free cluster and copy the connection string. Then put the connection string in .env*

***9.** Connect to the database using mongoose:*
```typescript
mongoose.Promise = Promise;
mongoose.connect(process.env.MONGO_URL);
mongoose.connection.on('error', (error: Error) => {
    console.log(error)
})
```

***10.** Create the schema for various collection*