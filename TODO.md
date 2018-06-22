### Trivia
- We're going with `Creating our first component`
  - Objectives: create a new component called `TriviaQuestion` that displays trivia data.
  - CSS classes you'll use:
    - .TriviaQuestion for box
    - .QuestionHeader for the question header
    - .Question for the question items.





- We're going to update app to be a little more dynamic with props
   - In the `TriviaQuestion` component, add properties for `title`, `answers` and `correctAnswerId`
   - Pass answers from your app component in `index.js`.
   - Answers should be in the following format:
  ```
      [
        { id: 1, label: "Answer 1" },
        { id: 2, label: "Answer 2" },
        { id: 3, label: "Answer 3" }
      ];
  ```
  - Create component for individual questions
  - Alongside answer data, pass a function from the existing component
    that `alerts` "Yes" or "No" if it's correct.




- State
  - Keep track of which answer was clicked in `TriviaQuestion` component.
  - If a question was answered correctly, highlight it green
  - If a question was answered incorrectly, highlight it red
  - After clicking an answer, disable additional clicks and display the word 'Verifying'
    - Simulate an API request with `setTimeout`
  - If a question is answered correctly after the timeout, display the word 'Correct!'
    instead of the question content.





- Component lifecycle
  - Move answers to state in the app component in 'index.js' + load answer data in `componentDidMount`
  - Prevent extra renders of `TriviaQuestionItem` by using `componentShouldUpdate`
    - only load if it's been selected + and it's correct.








- Cleanup
  - Pull state out of our `App` component, create a container in the `/containers` directory (which you'll need to make)
  - Isolate all state in this new container component.
  - Update `TriviaQuestion` to be a functional component









### NEW App

We're doing two exercises
- Routing exercise
  - create containers for login + movies
  - add routes
  - add links on login + movie containers to one another's routes
   with React Router's `Link` component.
```
<Link to="/path">I'm a link!</Link>
```

- Data exercise
  - Create a movie card component.
  - Load movie data on `componentDidMount` and save to container state.
  - Display a list of movie cards



- Redux exercise
  - Add dependencies for `redux` + `react-redux` + `redux-thunk`
  - Convert the container state to use Redux
  - Create `actionCreators.js`
  - Create store on `index.js` with `createStore.js`
  - Pass store to provider that wraps application.
  - Add connect to `MovieContainer`
    - Get `movies` from state + pass actionCreator for loading movies.


- Add controlled input to search for movies
  - Add actionCreator to search for movies.
  - Handle action in reducer.
  - Add controlled input to handle searches + add a button to submit a search.
  - Add actionCreators to our container and pass to new search component.



- Add `Authentication`
  - Add `formik` dependency
  - edit default route to send user to `/login`
  - add actionCreator that accepts `username` and `password`.
  - Add new reducer state value: `authenticated` + handle the action.
  - Add formik fields for username / password
  - Add validation for formik fields
  - Connect loginContainer + add onSubmit that fires off 'auth' action (bool)
  - Update action to redirect to '/movies' with:
  `history.push('/url_that_I_want_to_go_to')`
  - Update MovieContainer to send unauthenticated users back to '/login'


- Cart
  - Add action
  - Update reducer
  - Update Movie Card to allow you to add to cart.
  - Toggle some text on Movie Card to show whether or not its in the cart
  - Add cart count to Navigation by adding connect to Navigation.
