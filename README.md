# mail-list

## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn run serve
```

### Compiles and minifies for production
```
yarn run build
```
This project goes with the mail-server and is the frontend using bootstrap & axios, to access the API and post the user data (first/last name & email) to the server, and uses vue-toasts for errors and success.
It has one form with three boxes for uploading this data. 

It displays the error in the toast.

It gets verification from the server that the form is correct before uploading the data, and notifies the user upon error/success. When the email is registered in the mysql database, an email is sent.

Todo: Clean up form handling.
