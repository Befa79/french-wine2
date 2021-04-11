# MyWineShop

The project is a web-shop selling excellent french wine. 
Wine is produced and sold worldwide, but it is still not easy to know good quality wine. 
In France, this is part of the country culture, You will start to have your favourite type of grape (cepage), and your prefered vineyard.

This website has many purpose: 
- Sell French Wine
- Promote french wine culture
- Get to know some unique products 

 
## UX

| User ID| as a/an| I want to be able to....| So that i can...| 
| :----: | :--- | :--- | :--- |
| 1| Shopper| See a list of products| Buy product i want| 
| 2| Shopper| View product details, description, price| See the product image, price, description| 
| 3| Shopper| See the total cost of my shopping bag| Have an idea of my cost| 
| 4| Shopper| Sort list per price, rate| To have a list of the best price and/or best rate| 
| 5| Shopper| Sort per category| So i can chose the type of wine i need| 
| 6| Shopper| Sort a product per name or detail in the description| So i can chose i ""cepage"" in the description| 
| 7| Shopper| Easily purchase the products I want| With a easy page layout| 
| 8| Shopper| Have an overview of my purchases| Detailed list of all the added products in my shopping bag, so that I can make last changes easily before proceeding to payment.| 
| 9| Shopper| Fast and secure payment| Payment to be done and checked very fast, so that I won't be concerned about the safety of my card details and won't be charged incorrectly.| 
| 10| Shopper| Be notified when i do something| Receive a message when i add, delete, change an order, my account| 
| 11| Shopper| To shop with my mobile| Order some wine in the train from my phone| 
| 12| Site user| I want to reset my password if I forgot it| So i can login easily again| 
| 13| Site user| Create an account| Have a profile with my details| 
| 14| Site user| To login and logout with password| Be the only one with access to my details| 
| 15| Site user| Have a customise details| See my order history| 
| 16| Owner| I want to add products easily| so, can add product with all the details, like image| 
| 17| Owner| I want to edit or delete products easily and safely| I can change the details of a product, like the price, or delete it| 


## Features

### Top menu
* NavBar-mobile: The Navbar is  at the top and show the essential menus with hamburger style: Home/all wines/vineyard/bags/account/search
* NavBar-desktop: The desktop has the same features with logo French Wine
#### My account
* You can register/login/logout and access to your profile (your details with order history)
* As superuser you can have access to product management and add/edit/delete products

#### All wines
gives you access to all the products in the database, the features are Product_Name, Price, rate, category, image
#### Search
where you can search products with key words

#### Product detail page
When selecting a product, you will will have all the features, with a description, and you can also add the product in your shopping bag by adjusting the quantity and "add to bag"

#### Shopping Bag
The shopping bag provide an overview of all the users purchases, he can then add more quantity, or even remove the items. To confirm the order, he should click on Checkout.

#### Checkout 
The checkout page ask the users to add theirs personal, delivery, credit card details.
By puching **complete order** button, he will trigger the payment process with Stripe

### Future Features
It would be interesting to create some periodic promotion, 5 + 1 bottle of wine for free
To retain customer, create a customer status base on his orders.

## Technologies Used

#### Languages
* [HTML5](https://www.w3schools.com/html/default.asp)
* [CSS3](https://www.w3schools.com/css/default.asp)
* [Javascript](https://www.w3schools.com/js/default.asp)
* [Python3](https://www.w3schools.com/python/default.asp)
* [Jinja](https://jinja.palletsprojects.com/en/2.11.x/templates/)
#### Libraries and Framework
* [Django](https://docs.djangoproject.com/en/3.1/)
* [Bootstrap](https://getbootstrap.com/)
* [FontAwesome](https://fontawesome.com/)
* [Favicon](https://favicon.io/)
* [Google Fonts](https://fonts.google.com/)
* [JQuery](https://api.jquery.com/)
* [Gunicorn](https://docs.djangoproject.com/en/3.1/howto/deployment/wsgi/gunicorn/)
* [Psycopg2](https://pypi.org/project/psycopg2/)
* [Stripe](https://stripe.com/gb)
* [Crispy Form](https://django-crispy-forms.readthedocs.io/en/latest/)
### Tools
* [Gitpod](https://www.gitpod.io/)
* [Git](https://git-scm.com/)
* [GitHub](https://github.com/)
* [Pip](https://pip.pypa.io/en/stable/)
* [Heroku](https://heroku.com/)
* [AWS S3 Bucket](https://aws.amazon.com/)
* [Boto3](https://boto3.amazonaws.com/)
### Databases
* [Sqlite3](https://www.sqlite.org/index.html) Used with Django
* [PostgreSQL](https://www.postgresql.org/) Used with Heroku


## Testing

### - Profile & search:
| Test| Action| Expected Result| Test Result| 
| :--- | :----: | :--- | ---: |
| Search| enter text & click| find the product with text entered| Passed| 
| Empty search| no text entry| get all the products and error message | Passed| 
| Search work from the description| enter text & click| get specific products with key work in description ""merlot""| Passed| 
| register| enter text & click| get confirmation email request| Passed| 
| login| enter text & click| get your profile page when correct login| Passed| 
| wrong login| enter text & click| The username and/or password you specified are not correct.| Passed| 


### - Shopping bag:
| Test| Action| Expected Result| Test Result| 
| :--- | :----: | :--- | ---: |
| Add quantity in the bag| click or enter number| Quantity added to the shopping bag with cost calculated| Passed| 
| More 3 digits entered| enter number| nothing can't be added and message error on the field| Passed| 
| Qty changed in the bag| click or enter number| quantity changed and cost re-calculated| Passed| 
| back to shopping| click| Brings you back to the products page| Passed| 
| Remove item| click| remove the line item from the back| Passed| 
| Checkout| click| brings you to the form for the payment| Passed| 


### Checkout:
| Test| Action| Expected Result| Test Result| 
| :--- | :----: | :--- | ---: |
| Uncomplete form| click| error message when mandatory field are empty| Passed| 
| Wrong credit card| enter number| When enter a non-valid credit card number, the payment completion can't be done and an error message appears| Passed| 
| Payment| click| when all fields are correctly entered with a valid credit card number, payment should be executed| Passed| 
| Adjust bag| click| brings you back to the bag to change your order| Passed| 
| Save profile| checkbox| Your details are saved| Passed| 

### Products:
| Test| Action| Expected Result| Test Result| 
| :--- | :----: | :--- | ---: |
| add new product| enter text and click| New product added to the product list| Passed| 
| Enter a 6 digits price| enter text and click| Can't add the product + error message| Passed| 
| Edit a product| enter text and click| Change the details of a product| Passed| 
| Remove a product| click| delete a product when remove button is clicked| Passed| 

### SuperUser issue : I do encounter an issue when login with the super user, i need somehow to enter in Admin mode to be able to login. I'll try to fix this before submission

### Deployment : the Deployment had many issues:
* the postgres DB was not taken, and this is because the variables was not considered in Gitpod workspace, and the fix was found by Jo. It was needed to stop the workspace from gitpod directly and then restart the workspace
* the AWS S3 had a different version from the video and when you see this for the first time, it can get difficult
* To add the products details to postgres, it was needed to create a json file and load it. I received a perfect tuto for this from Jo and a colleague of her: 
- python3 manage.py dumpdata --exclude auth.permission --exclude contenttypes > db.json
- python3 manage.py loaddata db.json 

* Issue with postgres migration: An issue with Checkout is created due to the fact that older orders didn't have a profile attached to them. Unfortunaltely this create a bug and i can't enter in the admin/orders


## Deployment
The project is stored on **Github** and hosted on **Heroku**
#### Local Deployment
 To run this project, the following tools have to be installed:
* An IDE of your choice (I used [Gitpod](https://www.gitpod.io/) for creating this project)
* [Git](https://git-scm.com/)
* [Pip](https://pip.pypa.io/en/stable/)
* [Python3](https://www.w3schools.com/python/default.asp) With Mac it come pre installed.

You will also need to create account with:
* [Stripe](https://stripe.com/gb)
* [AWS](https://aws.amazon.com/) for the [S3 bucket](https://docs.aws.amazon.com/AmazonS3/latest/dev/Introduction.html)
* An email account of your choice. I used [gmail](https://mail.google.com/)
### Directions
1. You can clone this repository directly into you editor by pasting the following command into the terminal: https://github.com/Befa79/french-wine2
2. Or you can save a copy of this directory by clicking the green button " Clone or download" then "Download Zip" and after that extract the Zip file to your folder, change the directory to the directory file location you just created.
3. For this project i stored all  Stripe secret key in both Heroku setting and Gitpod setting. That way i could still use them for development and production. 

In `settings.py` you can set your variables like in the example below
```
import os

SECRET_KEY = os.environ.get(your secret key)
DEBUG = 'DEVELOPMENT' in os.environ
STRIPE_PUBLIC_KEY = os.getenv(your secret key
STRIPE_SECRET_KEY = os.getenv(your secret key)
STRIPE_WH_SECRET = os.getenv(your secret key)
```
For more info on how to set up the Stripe keys visit [Stripe key](https://stripe.com/docs/keys).

3. Install all requirements from the `requirements.txt` file putting this command into your terminal:
```
pip3 install -r requirements.txt
```
4. In the terminal in your IDE migrate the models to crete a database using the following commands:
```
python3 manage.py makemigrations
python3 manage.py migrate
```
5. Load the data fixture (Categories, Specials, Products) in that order using the following command in the terminal
```
python3 manage.py loaddata <fixture name>
```
6. Create a superuser, it will alow you to have access to the admin panel.
you need a username, an email, a password. Note the password won't display in the terminal but will be registered.
```
python3 manage.py createsuperuser
```
7. You can now run the the application using the following command in the terminal:
```
python3 manage.py runserver
```
8. To access the admin panel add `/admin` in the url and enter the details for the superuser you created.

#### Heroku Deployment
In order for Heroku to work properly, the local deployment steps are required.
You will also need to have installed  `gunicorn`, `dj-database-url` and `psycopg`. All of those are already in the project requirements.txt, but for future project they are essentials for Heroku to function properly. 

1. Create a `requirements.txt ` file, which will contains the list of dependencies, using the following command in the terminal:
```
pip3 freeze > requirements.txt
```
2. Create a `Procfile` and inside it type:
```
web: gunicorn whisky_shop.wsgi:application
```
3. On [Heroku](https://heroku.com/) website you can now create your **new app**, assign a unique name(try to use a name as close as possible to the project name for consistency), choose the region the closest to you and click **Create app**.
4. Go to **Resources** tab in Heroku, then in the **Add-ons** search bar look for **Heroku Postgres**, select **Hobby Dev — Free** and click **Provision*** button to add it to your project. (This is where  `dj-database-url` and `Psycopg` are required.)
5. In the Heroku **settings** click on `Reveal Config Vars` and set the following variables.

| KEY                       | VALUE              
|-----------------          | ------------------ 
| AWS_ACCESS_KEY_ID         | your AWS access key here      
| AWS_SECRET_ACCESS_KEY     | your AWS secret key here  
| DATABASE_URL              | your Postgres DB url here
| SECRET_KEY                | your secret key
| STRIPE_PUBLIC_KEY         | your stripe public key here
| STRIPE_SECRET_KEY         | your stripe secretkey here
| STRIPE_WH_SECRET          | your stripe WH secret here


6. Copy **DATABASE_URL's value**(Postrgres database URL) from the Convig Vars and temporary paste it into the default database in `settings.py`.
You can temporary comment out the current database settings code and just paste the following in `settings.py`:
```
DATABASES = {     
        'default': dj_database_url.parse("<your Postrgres database URL here>")  
    }
```
This is just a temporary set up that allows to make all the migrations required for our data in our DB to be transfer to Heroku **POstgres**. You shouldn't commit and push at this stage for security reason.

7. Here you can now follow the exact steps, 4, 5 and 6 as explain in local deployment.

8. You can remove the POstgres URL form you settings and uncomment the default DATABASE code form your settings.

9. Add your heroku app url to **ALLOWED_HOST** in the settings file and also include local host.
```
ALLOWED_HOSTS = ['your heroku app name here', 'localhost']
```
10. You can now connect Heroku to Github to automatically deploy each time you push to Github.
In Heroku **Dashboards** select 
* Deploy -> Deployment method -> Github
* link your Github repo name to Heroku
* Click **Enable automatic Deployment**
* Now you you run `git push` in the terminal, it will push to Github and Heroku.
11. After your app has been successfully deployed you can view you project by clicking on **open app**


## Credits

- http://www.vin-vigne.com/
- https://www.cdiscount.com/
- https://www.lavinia.fr/

This is the content of the webshop products (images, description)

Then i received great help from the tutors, Stackoverflow

Thanks to my mentor Brian for the good inspiration

