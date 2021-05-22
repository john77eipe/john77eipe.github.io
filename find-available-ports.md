## Find ports that are used or available
Run the command `netstat -anob` as admin.

To find which application is using a particular port you can filter out the results,
`netstat -anob | findstr "8080"`