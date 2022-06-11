# [Light Bootstrap](https://appseed.us/generator/light-bootstrap-dashboard/) Flask

Open-source **Flask Dashboard** generated by `AppSeed` op top of a modern `Bootstrap` design. Designed for those who like bold elements and beautiful websites, **[Light Bootstrap](https://appseed.us/generator/light-bootstrap-dashboard/)** is ready to help you create stunning websites and webapps. **Light Bootstrap** is built with over 50 frontend individual elements, like buttons, inputs, navbars, nav tabs, cards, or alerts, giving you the freedom of choosing and combining.

- 👉 [Light Bootstrap Flask](https://flask-light-bootstrap.appseed-srv1.com/) - LIVE Demo
- 👉 [Light Bootstrap Flask](https://appseed.us/product/light-bootstrap-dashboard/flask/) - Product page
- 👉 [Complete documentation](https://docs.appseed.us/products/flask-dashboards/light-bootstrap-dashboard) - `Learn how to use and update the product`
  - ✅ [Set up the environment](https://docs.appseed.us/products/flask-dashboards/light-bootstrap-dashboard#environment)
  - ✅ [Manage App users](https://docs.appseed.us/products/flask-dashboards/light-bootstrap-dashboard#manage-app-users)
  - ✅ [Application Bootstrap Flow](https://docs.appseed.us/products/flask-dashboards/light-bootstrap-dashboard#application-bootstrap-flow)
  - ✅ [UI Assets and Templates](https://docs.appseed.us/products/flask-dashboards/light-bootstrap-dashboard#ui-assets-and-templates)
  - ✅ [Set up the MySql Database](https://docs.appseed.us/products/flask-dashboards/light-bootstrap-dashboard#set-up-the-mysql-database)
  - ✅ [Static Assets for production](https://docs.appseed.us/products/flask-dashboards/light-bootstrap-dashboard#static-assets-for-production)  
  
<br />

> Built with [Light Bootstrap Generator](https://appseed.us/generator/light-bootstrap-dashboard/)

- Timestamp: `2022-06-11 09:46`
- Build ID: `6ed92983-d231-4bea-b657-87391e4dfa60`
- **Free [Support](https://appseed.us/support/)** (registered users) via `Email` and `Discord`

<br />

> Features

- `Up-to-date dependencies`
- Database: `sqlite`
- `DB Tools`: SQLAlchemy ORM, Flask-Migrate (schema migrations)
- Session-Based authentication (via **flask_login**), Forms validation

<br />

![Light Bootstrap Dashboard - Starter generated by AppSeed.](https://user-images.githubusercontent.com/51070104/173181221-fc7697ab-e5ed-45e2-9e2b-8164e1df5b6d.png)

<br />


## ✨ Start the app in Docker

> **Step 1** - Download the code from the GH repository (using `GIT`) 

```bash
$ # Get the code
$ git clone https://github.com/appseed-projects/<YOUR_BUILD_ID>.git
$ cd <YOUR_BUILD_ID>
```

<br />

> **Step 2** - Edit `.env` and set `DEBUG=True`. This will activate the `SQLite` persistance. 

```txt
DEBUG=True
```

<br />

> **Step 3** - Start the APP in `Docker`

```bash
$ docker-compose up --build 
```

Visit `http://localhost:5085` in your browser. The app should be up & running.

<br />




## ✨ How to use it

> Download the code 

```bash
$ # Get the code
$ git clone https://github.com/appseed-projects/6ed92983-d231-4bea-b657-87391e4dfa60.git
$ cd 6ed92983-d231-4bea-b657-87391e4dfa60
```

<br />

### 👉 Set Up for `Unix`, `MacOS` 

> Install modules via `VENV`  

```bash
$ virtualenv env
$ source env/bin/activate
$ pip3 install -r requirements.txt
```

<br />

> Set Up Flask Environment

```bash
$ export FLASK_APP=run.py
$ export FLASK_ENV=development
```

<br />

> Start the app

```bash
$ flask run
```

At this point, the app runs at `http://127.0.0.1:5000/`. 

<br />

### 👉 Set Up for `Windows` 

> Install modules via `VENV` (windows) 

```
$ virtualenv env
$ .\env\Scripts\activate
$ pip3 install -r requirements.txt
```

<br />

> Set Up Flask Environment

```bash
$ # CMD 
$ set FLASK_APP=run.py
$ set FLASK_ENV=development
$
$ # Powershell
$ $env:FLASK_APP = ".\run.py"
$ $env:FLASK_ENV = "development"
```

<br />

> Start the app

```bash
$ flask run
```

At this point, the app runs at `http://127.0.0.1:5000/`. 

<br />

### 👉 Create Users

By default, the app redirects guest users to authenticate. In order to access the private pages, follow this set up: 

- Start the app via `flask run`
- Access the `registration` page and create a new user:
  - `http://127.0.0.1:5000/register`
- Access the `sign in` page and authenticate
  - `http://127.0.0.1:5000/login`

<br />

## ✨ Code-base structure

The project is coded using blueprints, app factory pattern, dual configuration profile (development and production) and an intuitive structure presented bellow:

```bash
< PROJECT ROOT >
   |
   |-- apps/
   |    |
   |    |-- home/                           # A simple app that serve HTML files
   |    |    |-- routes.py                  # Define app routes
   |    |
   |    |-- authentication/                 # Handles auth routes (login and register)
   |    |    |-- routes.py                  # Define authentication routes  
   |    |    |-- models.py                  # Defines models  
   |    |    |-- forms.py                   # Define auth forms (login and register) 
   |    |
   |    |-- static/
   |    |    |-- <css, JS, images>          # CSS files, Javascripts files
   |    |
   |    |-- templates/                      # Templates used to render pages
   |    |    |-- includes/                  # HTML chunks and components
   |    |    |    |-- navigation.html       # Top menu component
   |    |    |    |-- sidebar.html          # Sidebar component
   |    |    |    |-- footer.html           # App Footer
   |    |    |    |-- scripts.html          # Scripts common to all pages
   |    |    |
   |    |    |-- layouts/                   # Master pages
   |    |    |    |-- base-fullscreen.html  # Used by Authentication pages
   |    |    |    |-- base.html             # Used by common pages
   |    |    |
   |    |    |-- accounts/                  # Authentication pages
   |    |    |    |-- login.html            # Login page
   |    |    |    |-- register.html         # Register page
   |    |    |
   |    |    |-- home/                      # UI Kit Pages
   |    |         |-- index.html            # Index page
   |    |         |-- 404-page.html         # 404 page
   |    |         |-- *.html                # All other pages
   |    |    
   |  config.py                             # Set up the app
   |    __init__.py                         # Initialize the app
   |
   |-- requirements.txt                     # App Dependencies
   |
   |-- .env                                 # Inject Configuration via Environment
   |-- run.py                               # Start the app - WSGI gateway
   |
   |-- ************************************************************************
```

<br />



## ✨ PRO Version

> For more components, pages and priority on support, feel free to take a look at this amazing starter:

Soft UI Dashboard is a premium Bootstrap 5 Design now available for download in Flask. Made of hundred of elements, designed blocks, and fully coded pages, Soft UI Dashboard PRO is ready to help you create stunning websites and web apps.

- 👉 [Soft UI Dashboard PRO Flask](https://appseed.us/product/soft-ui-dashboard-pro/flask/) - Product Page
- 👉 [Soft UI Dashboard PRO Flask](https://flask-soft-ui-dashboard-pro.appseed-srv1.com/) - LIVE Demo 

<br >

![Soft UI Dashboard PRO - Starter generated by AppSeed.](https://user-images.githubusercontent.com/51070104/170829870-8acde5af-849a-4878-b833-3be7e67cff2d.png)

<br />

---
[Light Bootstrap](https://appseed.us/generator/light-bootstrap-dashboard/) Flask - Open-source starter generated by **[AppSeed Generator](https://appseed.us/generator/)**.
