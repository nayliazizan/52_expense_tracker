this is just exercise that i did when learning fullstack engineer at codecademy. therefore, the whole code wasnt mine. i only put a few lines to complete exercise

goal of this lesson is to learn to use MVC pattern to structure an app.

some notes briefly explain what code files are and what i did during this lesson:
1. getting started with model and controller
- controllers/index.js contain CRUD functions and get expenses by id, date. write in node.js
- models directory contain database.js and expense.sql. the 1st one connects our application to the PostgreSQL database. 2nd one define the data structure
- utils directory contain index.js. it has function for form field validation
- server.js at root. it allows us to connect and run our Express server with route middlewares
2. connecting the Model and Controller
- routes/expense.js. it has routes that access the controller’s functions
3. getting started with the view 
-- inside view/src/components
- ExpenseList.js populate expenses for given date n contains U n D functions
- LogExpense.js has C n U functions
- Model.js used to present the component exported from LogExpense.js as a model
-- or view/src/utils/index.js: houses all of the functions needed to interact with the controller from the views
-- view/src/App.js: we consider this file the “view” of our application. is where the application comes together
4. connecting the view and controller
-- view/src/App.js: inside useeffect functions, fetch expenses from the database for the current day and set them to the expenses state
-- view/src/App.js' DatePicker Component: Update the view as different dates are selected. Use the fetchExpenses() function while passing the selected date to fetch expenses for that date.
-- view/src/App.js' Modal Component: Update the function passed into the refreshExpenses prop. When this function is called, fetch and refresh the list of expenses with the currently selected date
-- view/src/components/ExpenseList.js' ExpenseList Component: Communicate with the controller to delete an entry from the model. Use the deleteExpense() function to asynchronously delete the expense from the database and update the view
-- view/src/components/LogExpense.js' LogExpense Component: Allow the user to create and update individual expenses
5. putting it all together
- should function as expected.
- make sure postgresql server is running, start express server, open terminal n run the 'npm start server' in root project folder. finally, start react server: npm run start at view directory. so total 3 servers
