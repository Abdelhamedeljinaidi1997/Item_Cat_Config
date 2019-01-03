# Linux-Server-Item_Cat-Config
In this project, a Linux machine on AWS needs to be configurated to support the Item Catalog websApp.

# Resource Link
1. [puplic ip :54.93.121.184](54.93.121.184)
2. [github repo : Abdelhamedeljinaidi1997/Item_Cat_Config](https://github.com/Abdelhamedeljinaidi1997/Item_Cat_Config)

## Tasks
1. Launch your Virtual Machine o AWS
2. Follow the instructions provided to SSH into your server
3. Create a new user named grader
4. Give the grader the permission to sudo
5. Update all currently installed packages
6. Change the SSH port from 22 to 2200
7. Configure the Uncomplicated Firewall (UFW) to only allow incoming connections for SSH (port 2200), HTTP (port 80), and NTP (port 123)
8. Configure the local timezone to UTC
9. Install and configure Apache to serve a Python mod_wsgi application
10. Install and configure PostgreSQL:
	- Do not allow remote connections
	- Create a new user named catalog that has limited permissions to your catalog application database
11. Install git, clone and setup your Catalog App project (from your GitHub repository ) correctly when visiting your server’s IP address in a browser. 
This app is based upon:
- [Python](https://www.python.org/)
- [Flask](http://flask.pocoo.org) 
- [SQLAlchemy](http://www.sqlalchemy.org)
- [SQLite](https://www.sqlite.org/)
- [Bootstrap v4.0.0-beta](https://getbootstrap.com/)
- [jQuery](https://jquery.com/)

A third party authentication system (Google and Facebook) is implemented to let users add, update and delete items. 

This app implements also API endpoints with responses formatted in JSON.

This web app is a project for the Udacity [Full Stack Web Developer Nanodegree](https://in.udacity.com/course/full-stack-web-developer-nanodegree--nd004/).
So, this application has been developed for an educational purpose.


## Requirements

- [Vagrant](https://www.vagrantup.com/)
- [VirtualBox](https://www.virtualbox.org/)

We assume that [Flask](http://flask.pocoo.org), [SQLAlchemy](http://www.sqlalchemy.org), 
[SQLite](https://www.sqlite.org/) 
are already installed in the virtual machine (VM).

## Set Up and run the application

Please follow these steps to set up and run the application.

Download or clone the [catalog-app](https://github.com/Abdelhamedeljinaidi1997/Item_Cat_Config) repository under `/catalog` and move this directory under your `/vagrant` directory (like that: `/vagrant/catalog`).

Launch the Vagrant VM from inside the `/vagrant` folder with:

```bash
$ vagrant up
$ vagrant ssh
```

Then move inside the catalog folder. 

```bash
$ cd /vagrant/catalog
```

Create and populate the database.

```bash
$ python data.py
```

Run the application.

```bash
$ python application.py
```

Open your web browser to this URL: http://localhost:8000



## API endpoints

| Request | Methods | What you get | 
| ------------- |-------------|---------|
| /catalog.json | GET | All categories with their items. |
| /v1/categories | GET | All categories with their items. |
| /v1/categories/*category_name* | GET | A specific category with his items. |
| /v1/categories/*category_name*/*item_title* | GET | A specific item. |



