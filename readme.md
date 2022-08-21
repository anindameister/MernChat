- `npm init`
- `npm i express`
- `package.json` - note that the default shouldn't be just commented out because that causes a problem 
```
  "scripts": {
    "start":"node server/server.js"
  },
```
- `npm i -D nodemon` for not restarting the server over again
- we also got to have the `dotenv` with `npm i dotenv`

- Now for the sake of just testing with dummy data, we just put some data into `data/data.js`
- now, we make the corresponding changes in the `server.js` file
- now, looking at the `data.js` files, we can observe that each object contains information about the two parties having a conversation and each conversation has an `id`.
    - we would attempt to get a particular conversation and that would make us use this particular `id` assocaited to each chat
```
app.get("/api/chat/:id", (req, res) => {
    console.log(req)
})
```
- The above code gives us a huge object in the editor console and now, we are actually looking for the `params` key
- Now, we would take the `id` and try to `find` out a single chat.
- I have used `filter` in here instead of `find`

## client
- `npx create-react-app client`
- chakra ui is a component library,`https://chakra-ui.com/getting-started`. From the url we get the command for the terminal.
- In the same documentation, it is said that `index.js` and not `App.js`, we have to wrap up our `App` with chakra provider.
- If we try to make `api calls` from our frontend to backend then it is going to give `cors` error.
  - so we have just put a proxy in the `package.json` file of the `client`
- The way, we design the app is by having a login page initially and after getting past that we get into the chat page.. So now, moving from one page to the another is done by `react-router`
  - let's particular install react router dom version 5 with `npm install react-router-dom@5`
  - in order to proceed with react router dom, we need to wrap up our whole application with something called `BrowserRouter` according to the documentation in `https://v5.reactrouter.com/web/guides/primary-components`
  - now, again `react-router-dom` is used so that we can navigate from one page to another. Keeping this idea in our mind, in the `App.js` file, let's just make sure that we put the paths where the navigation needs to be done. Just one more thing, the pages are supposed to contain reusable components, so definitely it should have components and if this components can be reused or not could be decided on, later.