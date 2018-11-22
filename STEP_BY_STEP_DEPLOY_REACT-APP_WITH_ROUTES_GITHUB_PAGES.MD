# allanyeznaian

step by step deploy react app

make a new repository (username.github.io) with a gitignore file node

clone the repository git clone https://github.com/username/username.github.io
into a new folder

cd username.github.io

git add --all

git commit -m "Initial commit"

git push -u origin master

npm install -u -g npm   (upgrades npm)

npm install -u -g create-react-app   (upgrades create react app)

create-react-app projectname --use-npm

cd projectname

npm install --save react-router react-router-dom

npm install gh-pages --save

code .

go to the package.json file
under "private":true,

add

"homepage": "https://username.github.io/",

inside the "scripts" object add

"predeploy": "npm run build",
"deploy": "gh-pages -d build",

*IMPORTANT IF APP WITH MULTIPLE COMPONENTS AND ROUTES

browserrouter does NOT work.
you must have this import

```
import { HashRouter, Route, Switch } from "react-router-dom";
```

and you must route your components like this

```
<HashRouter basename="https://username.github.io/">
        <Switch>
          <Route exact path="/" component={Component1} />
          <Route exact path="/example" component={Component2} />
          <Route exact path="/example2" component={Component3} />
          <Route component={() => <div>404 Not found 1</div>} />
        </Switch>
</HashRouter>
```



git add --all
git commit -m "message"

npm run deploy

and that should be it!
