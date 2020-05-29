Config Folfer:
Config.json: This helps sequilize know our data base. 

Passport.js:
The main intention of this file is to take user email information by requiring passport & local strategy. We will then use our database to find user email and password. If there is no user/ incorrect password found the inccorect email /password message will be displayed.



Models Folder:
Index.js:The main intention of this file is to set up sequlize with our atabase to use the sequelize ORM. This file is basically boilerplate. At the top of the file we are just requiring all our modules.


User.js:The main intention of this file is to create the user table model in our database. The sequlize.define portion of this code allows you to create the table and its columns which are defined through DataType.
Lines 22-31, are here to check the passwords stored in the database.

Public Folder:
Login:The main intention of this file is to create the email form to log in to and its inputs and save the values of them in userData object.Lines 1-6 set up jquery and creates elemnts of form. Lines 8-12 set up our form, gives it an event on submit and saves values from form. Lines 15-23, returns values as long as they are put into input, and then clears the form. Lines 26-37, allows us to post our userData object data to database and then redirects user to that memebrs page or else run error.


Members:This files just gets user data from database and renders the html on the page through the jquery element.
Signup:The main intention of this file is to create a signup form. Basicaly the same way the login was created. In this file we use post method to send sign up object to database or run error if anything goes wrong.

Login.html:Basic html page that setups login form. Page allows you to use jquery and links to the login.js file.
Members.html:This our members page which is rendered by our userdata that was saved to database in sign up form. Page holds html template to be rendered by correct user data.
Signup.html: This html page is our sign up page. The file will allow user to sign up as memebr and save as apart of our database. 

Routes:
api-routes.js: This file creates our HTTP request to our data base. 1st POST route  allows us post our login entry to databse and then database returns rendred members page.2nd Post route: creates user model in our database.1st get route redirects user to root page by logging out.2nd get route reads user data and responds with body of req.body.

html-routes.js: this file's main intention is to create get routes to redirect the user to the root,members, and login pages.

Server.js: This file creates our serever and syncs our database to sequelize. We require our module express, session, and passport. Then the middleware is setup lines 12-19. Next we require our html and api routes. The last lines syncs our database.

