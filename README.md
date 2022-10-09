## MYSQL-PROJECT-ON-GOOGLE-PLAY-STORE
## SQL CASE STUDY
* create database Research_project1;

* use research_project1;

select * from playstore_apps;

##  1.category wise app_name 

* select app_name,company,category
from playstore_apps
group by app_name;
	
## 2.Date wise updated 

* select app_name,updated 
  from playstore_apps
  order by updated;



## 3 How many total apps do we have
 * select category,count(*) as app_name
 from playstore_apps
 group by category

## 4  version of app_name

* select app_name,current_version
from playstore_apps
order by current_version

alter table playstore_apps
rename column requires_android to android;



## which app requires which andrioid

* select app_name,category,requires_android
from playstore_apps
group by app_name
order by category;

## 6. which app has highest no of installs 

* select CATEGORY,count(installs) as installs
  from playstore_apps
  group by category;



## 7. which app has lowest no of installs
* select app_name,installs
  from playstore_apps
  where installs = (select min(installs)
  from playstore_apps);

## 8 size of apps

* select app_name,size
 from playstore_apps
 group by app_name

## 9 app_name and their developers

* select app_name,developer
  from playstore_apps
  group by app_name


## 10 price of in app products

* select CATEGORY,count(in_app_products) as purchase
from playstore_apps
WHERE category is  not null
group by category
order by purchase

## 11  details of each app

* select app_name,category,size,current_version,in_app_products
from playstore_apps
group by app_name

## 12 what is the average rating of all apps

* select category,avg(rating) as Avgrating
from playstore_apps
group by category


## 13

* select current_version,requires_android
from playstore_apps
where current_version > 5 and requires_android > 5 ;


## 14  type of app paid or free

* select app,category,type 
from googleplaystore
order by app;

### POWERPOINT PRESENTATION
[research ppt.pptx](https://github.com/Amitsarkar02/MYSQL-PROJECT-ON-GOOGLE-PLAY-STORE/files/9740900/research.ppt.pptx)

