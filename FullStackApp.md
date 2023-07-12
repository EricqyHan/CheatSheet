# How to setup a Full Stack App

## Setting up your project

```
mkdir api-project
cd api-project
npm init
npm install express --save
npm install mongodb --save
npm install ejs --save
npm install dotenv --save
```

## Connect to DB

```js
let db,
    dbConnectionStr = 'mongodb+srv://demo:demo@cluster0
    .2wapm.mongodb.net/rap?retryWrites=true&w=majority',
    dbName = 'database name'

MongoClient.connect(dbConnectionStr, { useUnifiedTopology: true })
    .then(client => {
        console.log(`Connected to ${dbName} Database`)
        db = client.db(dbName)
    })
```

## .env

```
DB_STRING =
  mongodb+srv://demo:demo@cluster0.2wapm.mongodb.net/rap?retryWrites=true&w=majority
```

## Add .env to .gitignore

```
.env
node_modules
```

## In terminal, add var to heroku

```
heroku config:set DB_STRING =
  mongodb+srv://demo:demo@cluster0.2wapm.mongodb.net/rap?retryWrites=true&w=majority
```

## Server Setup

```js
app.set("view engine", "ejs");
app.use(express.static("public"));
app.use(express.urlencoded({ extended: true }));
app.use(express.json());

app.listen(process.env.PORT || PORT, () => {
  console.log(`Server running on port ${PORT}`);
});
```

## Create EJS File

```ejs
    <h1>Current Rappers</h1>
    <ul class="rappers">
    <% for(let i=0; i < info.length; i++) {%>
        <li class="rapper">
            <span><%= info[i].stageName %></span>
            <span><%= info[i].birthName %></span>
            <span class='del'>delete</span>
        </li>
    <% } %>
    </ul>

    <h2>Add A Rapper:</h2>
```

## API - GET (READ)

```js
app.get("/", (request, response) => {
  db.collection("rappers")
    .find()
    .toArray()
    .then((data) => {
      response.render("index.ejs", { info: data });
    })
    .catch((error) => console.error(error));
});
```

### API - POST (CREATE)

```js
app.post("/addRapper", (request, response) => {
  db.collection("rappers")
    .insertOne(request.body)
    .then((result) => {
      console.log("Rapper Added");
      response.redirect("/");
    })
    .catch((error) => console.error(error));
});
```

### API - PUT (UPDATE)

```js
app.put("/addOneLike", (request, response) => {
  db.collection("rappers")
    .updateOne(
      {
        stageName: request.body.stageNameS,
        birthName: request.body.birthNameS,
        likes: request.body.likesS,
      },
      {
        $set: {
          likes: request.body.likesS + 1,
        },
      },
      {
        sort: { _id: -1 },
        upsert: true,
      }
    )
    .then((result) => {
      console.log("Added One Like");
      response.json("Like Added");
    })
    .catch((error) => console.error(error));
});
```

## API DELETE - (DELETE)

```js
app.delete("/deleteRapper", (request, response) => {
  db.collection("rappers")
    .deleteOne({ stageName: request.body.stageNameS })
    .then((result) => {
      console.log("Rapper Deleted");
      response.json("Rapper Deleted");
    })
    .catch((error) => console.error(error));
});
```

### Push to Heroku

```
heroku login -i
heroku create simple-rap-api
echo "web: node server.js" > Procfile
git add .
git commit -m "changes"
git push heroku main
```
