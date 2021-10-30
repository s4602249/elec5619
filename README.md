# ELEC5619 Sport Fields Reservation System

## Used libraries and their versions:

| Library     | Version       |
|:-----------:|:-------------:|
| Spring Boot | 2.0.4.RELEASE |
| JDK         | 13.0.8        |
| Bootstrap   | 5.1.0         |
| jquery      | 3.6.0         |
| MySQL       | 5.6           |

<br>

## Working functionalities of the project:
## User
### 1. Register: 
- Users can register with username, password, phone, e-mail, secret question and answer.
- Dynamic check whether the email and username has already been registered by other users. *(Ajax)*
- The password is encrypted by *PasswordEncoder*.
### 2. Login: 
- Users can login with correct username, password and captcha. User login page with option to switch role (user or admin).
- Set session attribute: store user information in session.
- Remember me: store username and password in cookie.
### 3. Find Password: 
Users can click ‘Forget password?’ on Login page to go to Find Password page. Users can retrieve the password by inputting username, correct answer for secret question and new password. 
### 4. Logout: 
A link on the navigation bar of each page enables the user to logout.
### 5. View & Edit Profile: 
Display the user information that can be edited including phone, e-mail, secret question and answer, with a ‘Submit’ button available to save any change to profile.
### 6. Fitness calculator: 
Users can input age, weight, height and then click the ‘Calculate’ button to get the BMI and health condition. *(external API called form back end & Ajax)*
### 7. Top up: 
Users can input the amount of money and card information to top up their account.
### 8. Check Balance: 
Users can check their account balance.
### 9. Home Page: 
Display the overview information (name, description and admin) of all sports fields, with a ‘View’ button available for each field to view the detail information.
### 10. Search Sports Fields: 
Users can input keywords in the search bar on home page to search for the related sports fields. *(Ajax)*
### 11. View Sports Fields Information: 
Users can click the ‘View’ button to check the specific sports fields information including field name, address, description, manager phone number, marks, comments, reserve condition and etc.
### 12. View Sports Fields Location: 
Users can click the ‘Location’ button on each sports field information page to open a google map with the location marker of the sports field. *(external API called from front end)*
### 13. Comment: 
Users can input and submit comments on any sports field.
### 14. Mark: 
Users can input and submit marks for any sports field.
### 15. Reserve Sports Fields: 
Users can reserve a sports field if the button shows ‘Reserve’. If the button shows ‘Reserved’, the sports field is reserved and users cannot make a reservation for this field. Users need to top up first and make sure the account balance is enough before making a reservation.

<br>

## Admin
### 1. Register: 
- Admin can register with username, password, phone and e-mail.
- Dynamic check whether the email and username has already been registered by other users. *(Ajax)*
- The password is encrypted by *PasswordEncoder*.
### 2. Login: 
- Admin can login with correct username, password and captcha. Admin login page with option to switch role (user or admin).
- Set session attribute: store admin information in session.
### 3. Logout: 
A link on the navigation bar of each page enables the admin to logout.
### 4. View Profile: 
Display the admin information including phone and e-mail.
### 5. Home Page: 
Display the overview information (name, description and admin) of all sports fields, with a ‘View’ button available for each field to view the detail information.
### 6. Search Sports Field: 
Admin can input keywords in the search bar to search for the related sports fields. *(Ajax)*
### 7. Upload Sports Fields: 
Admin can upload a new sports field with the required information including field picture, field name, manager phone number, field address and description.
### 8. View Sports Field Information: 
Admin can click the ‘View’ button to check the specific sports fields information including field name, address, description, manager phone number, marks, comments and etc.
### 9. Edit Sports Fields: 
Admin can click the ‘Edit’ button on each sports field information page. The edit page display the field information that can be edited including field name, manager phone number, address and description, with the ‘Save Change’ button available to save any change to the field.
### 10. Delete Sports Field: 
Admin can click the ‘Delete’ button on each sports field information page to delete the sports field from the database along with the related reservation.
### 11. Manage The Reservation: 
Admin can view all reservation records on the page. Admin can cancel any reservation record.

<br>

## Authentication
If the session attributes is null, it will retain in the login page.

<br>

## A quick guide on how to run the application
### 1. Download
Download this project, unzip and open it with an IDE (e.g. IntelliJ IDEA).
### 2. Configure
To run our project, the `database` and project `configuration file` must be re-implemented firstly. 
#### Database
- Our project use `Google MySQL Cloud Service` as the database.
- Database manager needs to choose a cloud database provider and remember the IP address for your database instance. In the instance, you need to create a new database *(Our project created database called `elec5619`)*.
- The version of this database must be `MySQL 5.6` *(Or you need to change the `config file` in the project to match with your database version)*.
- The database manager must create a new user and grant the read/write rights to this user.

#### Project
- You need to access the `application.properties` files in the `src` path.
- Please set up the `datasource.url`, `username` and `password` refer to the following structure:
```properties
spring.datasource.url=jdbc:mysql://34.132.234.105:3306/elec5619?useSSL=false
spring.datasource.username=elec5619
spring.datasource.password=admin
```
*(If you plan to use another database version, you also need to re-config the `database driver name`. You may also need to set the firewall on the cloud service to allow this project access database.)*
<br>
<br>

- If you plan use the local database, please remove the following code in the `application.properties` file:
```properties
spring.jpa.database-platform=org.hibernate.dialect.MySQL5InnoDBDialect
```
*(It uses for `Google MySQL Cloud Service` to run the hibernate.)*
<br>
<br>

### 3. Run
- Run `'Springboot2WebappJspApplication.class'`.
- Open a browser and go to `http://localhost:8080/`.


