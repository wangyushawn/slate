---
title: API Reference

language_tabs:
  - HTTP
  - java

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Staffum API 2.0 Document based on Staffum Server 3.0. Server #3.0 has migrate **Slots** from google calendar to SQL database.
# Entity

## Position
> The **Position** JSON structured like this:

```json
{
  "id": 32,
  "title": "SALES",
  "level": 0,
  "authorityLevel": "STORE_ASSOCIATE",
  "privilege": {
    "title": null,
    "viewOnDuty": true,
    "viewOnCall": true,
    "viewTodayNumbers": true,
    "viewMonthNumbers": true,
    "viewAnnualNumbers": true,
    "viewSalesGoal": true,
    "viewBudget": true,
    "viewActualSales": true,
    "viewLaborCost": true,
    "viewHistogram": true,
    "viewSchedules": true,
    "editSchedules": true,
    "includeLabors": true,
    "reviewSchedules": true,
    "publishSchedules": true,
    "doubleApproval": false,
    "viewRequests": true,
    "reviewRequests": true,
    "viewTeam": true,
    "editTeam": true,
    "viewTeamCompensation": true,
    "viewTeamRanking": true,
    "viewReports": true,
    "viewSetting": true,
    "editSetting": true,
    "level": 0
  },
  "sales": true
}
```

### Description
The description of position of the Corporate

### Attributes
Attribute       | Description
--------------- | ---------------
id				| The ID of the Position
title			| The title of the Position
level 			| The priority level of the Position
authorityLevel	| The Authority Level of the Position. E.g.: **_STORE_MANAGER_**, **_STORE_ASSOCIATE_**, **_DISTRICT_MANAGER_**
privilege		| The **Privilege** of the Position
sales			| Whether the Position is a sales-like position


## Staff Infos
> The **Staff Infos** JSON structured like this:

```json
{
  "uid": 32,
  "name": "alpha11",
  "email": "alpha11@calendar.percolata.com",
  "phone": "4084751649",
  "corporateId": 1,
  "districtId": null,
  "weeklyMaxHours": 40,
  "weeklyMinHours": 0,
  "wages": 15,
  "wagesType": "HOURLY",
  "commission": 0.1,
  "field": false,
  "employmentStatus": "FULLTIME",
  "position": {
    "id": 32,
    "title": "SALES",
    "level": 0,
    "authorityLevel": "STORE_ASSOCIATE",
    "privilege": {
      "title": null,
      "viewOnDuty": true,
      "viewOnCall": true,
      "viewTodayNumbers": true,
      "viewMonthNumbers": true,
      "viewAnnualNumbers": true,
      "viewSalesGoal": true,
      "viewBudget": true,
      "viewActualSales": true,
      "viewLaborCost": true,
      "viewHistogram": true,
      "viewSchedules": true,
      "editSchedules": true,
      "includeLabors": true,
      "reviewSchedules": true,
      "publishSchedules": true,
      "doubleApproval": false,
      "viewRequests": true,
      "reviewRequests": true,
      "viewTeam": true,
      "editTeam": true,
      "viewTeamCompensation": true,
      "viewTeamRanking": true,
      "viewReports": true,
      "viewSetting": true,
      "editSetting": true,
      "level": 0
    },
    "sales": true
  },
  "avatar": null
}
```

### Description
The details of a Employee, including email, name, phone, weeklyMinHours and others

### Attributes
Attribute       	| Description
------------------- | ---------------
uid					| The User Id of the Employee
name				| The name of the Employee
email				| The email of the Employee
phone				| The phone of the Employee
corporateId			| The ID of the Corporate the Employee belongs to
districtId			| The ID of the District the Employee work at
weeklyMaxHours		| The Weekly Max working hours of the Employee
weeklyMinHours		| The Weekly Min working hours of the Employee
wages 				| The wages of the Employee
wagesType			| The Type of the Wages. **_MONTHLY_**, **_WEEKLY_**, **_HOURLY_**, **_BI_WEEKLY_**, **_BI_MONTHLY_**, **_ANNUALLY_**
commission			| The commission rate of the Employee
field				| Whether the Employee is a on field worker
employmentStatus	| The Employee's Employment Status. E.g.: **_FULLTIME_**, **_PARTTIME_**, **_SUSPEND_**
position			| The **Position** of the Employee
avatar				| The avatar of the Employee


## Periodic Sales Plan
> The **Periodic Sales Plan** JSON structured like this:

```json
{
  "from": "2016-06-30T17:00:00-07:00",
  "to": "2016-07-31T17:00:00-07:00",
  "productGoal": 245361.0,
  "serviceGoal": 232156.0
}
```

### Description
The periodic financial Sales plan of store, indicates the sales goal of the certain period for store.

### Attributes
Attribute       | Description
--------------- | ---------------
from            | the certain period from date,  __ISO RFC3336__ Date with zone offset.
to              | the certain period to date,  __ISO RFC3336__ Date with zone offset.
productGoal     | the product goals within the certain period for the store
serviceGoal     | the service goals withnin the certain period for the store

## Periodic Labors Plan
> The **Periodic Labors Plan** JSON structured like this:

```json
{
  "from": "2016-07-01T00:00:00-07:00",
  "to": "2016-08-01T00:00:00-07:00",
  "budget": 2750.5,
  "laborHour": 475.25
}
```

### Description
The periodic financial labors plan of store, indicates the labor budget of the certain period for store.

### Attributes
Attribute       | Description
--------------- | ---------------
from            | the certain period from date,  __ISO RFC3336__ Date with zone offset.
to              | the certain period to date,  __ISO RFC3336__ Date with zone offset.
budget          | the money budget amount within the certain period for the store
laborHours      | the labor hours budget amount withnin the certain period for the store

## Store Details
> The **Store Details** JSON structured like this:

```json
{
  "bizHours": [
    {
      "storeId": 1,
      "type": "OPEN",
      "mon": "08:00:00",
      "tues": "08:00:00",
      "wed": "08:00:00",
      "thur": "08:00:00",
      "fri": "08:00:00",
      "sat": "08:00:00",
      "sun": "09:00:00"
    },
    {
      "storeId": 1,
      "type": "CLOSE",
      "mon": "21:00:00",
      "tues": "21:00:00",
      "wed": "21:00:00",
      "thur": "21:00:00",
      "fri": "21:00:00",
      "sat": "21:00:00",
      "sun": "18:00:00"
    }
  ],
  "timeZone": "America/Los_Angeles",
  "address": "949 Industrial Ave, Palo Alto, CA 94303",
  "name": "Percolata",
  "icon": null,
  "schedulers": null,
  "trafficFormula": null,
  "storeId": 1,
  "locationId": 39,
  "districtId": 1,
  "corporateId": 1
}
```

### Description
The details information of Store, including Store Open&Close hours, time zone, location and others.

### Attributes
Attribute       | Description
--------------- | ------------
bizHours        | The Open & Close hours of Store
timeZone        | The time zone ID of the store location. "US/Pacific"
address         | The address of the store
name            | The name of the store
icon            | The path of Store Icon
schedulers      | The scheduler algorithm which is used by store
trafficFormula  | The traffic formula of the store
storeId         | The ID of the Store
locationId      | The location ID of the store
districtId      | The District ID for the store location
corporateId     | The Corporate ID of the store

## Privilege 
> The **Privilege** JSON structured like this:

```json
{
  "title": null,
  "viewOnDuty": true,
  "viewOnCall": true,
  "viewTodayNumbers": true,
  "viewMonthNumbers": true,
  "viewAnnualNumbers": true,
  "viewSalesGoal": true,
  "viewBudget": true,
  "viewActualSales": true,
  "viewLaborCost": true,
  "viewHistogram": true,
  "viewSchedules": true,
  "editSchedules": true,
  "includeLabors": true,
  "reviewSchedules": true,
  "publishSchedules": true,
  "doubleApproval": false,
  "viewRequests": true,
  "reviewRequests": true,
  "viewTeam": true,
  "editTeam": true,
  "viewTeamCompensation": true,
  "viewTeamRanking": true,
  "viewReports": true,
  "viewSetting": true,
  "editSetting": true,
  "level": 0
}
```

### Description
The **Privilege** shows all the authority and priority of the Employee

### Attributes
Attribute             | Description
--------------------- | ------------
title                 | The **Title** of the Employee
viewOnDuty            | Whether the Employee has authority to view [On duty] on Application
viewOnCall            | Whether the Employee has authority to view [On Call] on Application
viewTodayNumbers      | Whether the Employee has authority to view [Today Performance] on Application
viewMonthNumbers      | Whether the Employee has authority to view [Monthly Performance] on Application
viewAnnualNumbers     | Whether the Employee has authority to view [Annual Performance] on Application
viewSalesGoal         | Whether the Employee has authority to view [Sales Goal] on Application
viewBudget            | Whether the Employee has authority to view [Labor Budget] on Application
viewActualSales       | Whether the Employee has authority to view [Actual Sales] on Application
viewLaborCost         | Whether the Employee has authority to view [Labor Cost] on Application
viewHistogram         | Whether the Employee has authority to view [Histogram] on Schedules Page
viewSchedules         | Whether the Employee has authority to view [Schedules] on Schedules Page
editSchedules         | Whether the Employee has authority to edit [Schedules] on Schedules Page
includeLabors         | Whether the Employee should be included into labors calculation
reviewSchedules       | Whether the Employee has authority to review [Schedules Plan]
publishSchedules      | Whether the Employee has authority to publish [Schedules] on Schedules Page
doubleApproval        | Whether the Schedules Plan from Employee need a Double Approval
viewRequests          | Whether the Employee has authority to view Requests Page
reviewRequests        | Whether the Employee has authority to review a Normal Request
viewTeam              | Whether the Employee has authority to view Team Page
editTeam              | Whether the Employee has authority to edit Staffing roster
viewTeamCompensation  | Whether the Employee has authority to view the compensation of the staffs
viewTeamRanking       | Whether the Employee has authority to view the ranking of the staffs
viewReports           | Whether the Employee has authority to view Reports Page
viewSetting           | Whether the Employee has authority to view Setting Page
editSetting           | Whether the Employee has authority to edit Settings 
level                 | The Position Level of the Employee

## Access Control List
> The **Access Control List** JSON structured like this:

```json
{
  "uid": 34,
  "corporateId": null,
  "initialized": true,
  "authorityLevel": null,
  "authorities": [
    "ROLE_STORE_MANAGER",
    "ROLE_STORE_ASSOCIATE"
  ],
  "districtACLs": [
    17,
    1,
    2,
    3
  ],
  "storesMap": {
    "1": {
      "bizHours": [
        {
          "storeId": 1,
          "type": "OPEN",
          "mon": "08:00:00",
          "tues": "08:00:00",
          "wed": "08:00:00",
          "thur": "08:00:00",
          "fri": "08:00:00",
          "sat": "08:00:00",
          "sun": "09:00:00"
        },
        {
          "storeId": 1,
          "type": "CLOSE",
          "mon": "21:00:00",
          "tues": "21:00:00",
          "wed": "21:00:00",
          "thur": "21:00:00",
          "fri": "21:00:00",
          "sat": "21:00:00",
          "sun": "18:00:00"
        }
      ],
      "timeZone": "America/Los_Angeles",
      "address": "949 Industrial Ave, Palo Alto, CA 94303",
      "name": "Percolata",
      "icon": null,
      "schedulers": null,
      "trafficFormula": null,
      "storeId": 1,
      "locationId": 39,
      "districtId": 1,
      "corporateId": 1
    },
    "2": {
      "bizHours": [
        {
          "storeId": 2,
          "type": "OPEN",
          "mon": "09:00:00",
          "tues": "09:00:00",
          "wed": "09:00:00",
          "thur": "09:00:00",
          "fri": "09:00:00",
          "sat": "09:00:00",
          "sun": "10:00:00"
        },
        {
          "storeId": 2,
          "type": "CLOSE",
          "mon": "22:00:00",
          "tues": "22:00:00",
          "wed": "22:00:00",
          "thur": "22:00:00",
          "fri": "22:00:00",
          "sat": "22:00:00",
          "sun": "19:00:00"
        }
      ],
      "timeZone": "America/Los_Angeles",
      "address": "2656 Richmond Ave, New York, NY 10314",
      "name": "Test - San Francisco",
      "icon": null,
      "schedulers": "{\"SIMPLE\": \"GL\", \"LINEAR OPTIMIZER\": \"SHAUN\"}",
      "trafficFormula": null,
      "storeId": 2,
      "locationId": 507,
      "districtId": 2,
      "corporateId": 1
    },
    "3": {
      "bizHours": [
        {
          "storeId": 3,
          "type": "OPEN",
          "mon": "09:00:00",
          "tues": "09:00:00",
          "wed": "09:00:00",
          "thur": "09:00:00",
          "fri": "09:00:00",
          "sat": "09:00:00",
          "sun": "10:00:00"
        },
        {
          "storeId": 3,
          "type": "CLOSE",
          "mon": "22:00:00",
          "tues": "22:00:00",
          "wed": "22:00:00",
          "thur": "22:00:00",
          "fri": "22:00:00",
          "sat": "22:00:00",
          "sun": "19:00:00"
        }
      ],
      "timeZone": "America/Los_Angeles",
      "address": "111 Powell St, San Francisco, CA 94102",
      "name": "UniQlo 508",
      "icon": null,
      "schedulers": null,
      "trafficFormula": null,
      "storeId": 3,
      "locationId": 508,
      "districtId": 3,
      "corporateId": 1
    }
  },
  "privilege": {
    "title": null,
    "viewOnDuty": true,
    "viewOnCall": true,
    "viewTodayNumbers": true,
    "viewMonthNumbers": true,
    "viewAnnualNumbers": true,
    "viewSalesGoal": true,
    "viewBudget": true,
    "viewActualSales": true,
    "viewLaborCost": true,
    "viewHistogram": true,
    "viewSchedules": true,
    "editSchedules": true,
    "includeLabors": true,
    "reviewSchedules": true,
    "publishSchedules": true,
    "doubleApproval": false,
    "viewRequests": true,
    "reviewRequests": true,
    "viewTeam": true,
    "editTeam": true,
    "viewTeamCompensation": true,
    "viewTeamRanking": true,
    "viewReports": true,
    "viewSetting": true,
    "editSetting": true,
    "level": 0
  },
  "expiredAt": "2016-07-20T12:25:46.447+0000",
  "storeManager": false
}
```

### Description
The **Access Control List** of the Users, it shows the roles, privileges, authority and others.

### Attributes
Attribute       | Description
--------------- | ------------
uid             | The User's ID
corporateId     | The ID of Corporate User belongs to
initialized     | Whether the basic information of User has been initialized.
authorityLevel  | The Authority Level of User
authorities     | A List of Authorities of User
districtACLs    | All the District ID User has authority on
storesMap       | The **Stores Details** that User could manage
privilege       | The **Privilege** of the User
expiredAt       | The expiration time of the token
storeManager    | Whether the User is a Store Manager

## Daily Labors And Cost
> The **Daily Labors & Cost** JSON structured like this:

```json
{
    "date": "2016-06-24T00:00:00Z",
    "hours": 48.0,
    "cost": 743.5
}
```

### Description
The **actual** daily labor hours and cost of a Store

### Attributes
Attribute   	| Description
--------------- | ------------
date            | The date of the **_Daily Labors & Cost_**
hours           | The accumulative labor hours of the date from a store
cost            | The accumulative labor cost of the date from a store

## Daily Sales
> The **Daily Sales** JSON structured like this:

```json
{
    "date": "2016-06-24T00:00:00Z",
    "sales": 10743.43
}
```

### Description
The **actual** daily sales of a Store

### Attributes
Attribute   	| Description
--------------- | ------------
date            | The date of the **_Daily Sales_**
sales           | The accumulative sales of the date from a store

## Retail Performance
> The **Retail Performance** JSON structured like this:

```json
{
    "districtId": 0,
    "basicMetrics": {
      "walkIn": 41883,
      "walkBy": 85545,
      "goal": 651800.5999999999,
      "sales": 653809.073638916,
      "validSales": 638004.703207016,
      "lastTermSales": 700264.045396544,
      "transactionsCount": 7496,
      "validTCount": 7408,
      "budget": 42666.01000000008,
      "laborHours": 1451.25,
      "laborCost": 11134.900000000005,
      "lastTermCost": 0.0,
      "efficientSlots": 545,
      "elapseSlots": 9107,
      "updatedAt": "2016-07-20T06:29:06.233Z"
    },
    "completionRate": 1.003081423427527,
    "captureRate": 0.3286797250211884,
    "laborEfficiency": 0.05984407598550565,
    "usedBudgetRate": 0.26097823536815334,
    "shopperYield": 15.233023021441062,
    "atv": 86.12374503334449,
    "conversion": 0.17687367189551848
}
```

### Description
The retail performance is a bunch of metrics to evaluate the performance of the store.

### Attributes
Attribute   	|   Sub-Attribute 	| Description
--------------- | ----------------- | ------------
districtId  	|               	| The ID of the retail district
completionRate	|               	| A metric to evaluate how well the retailer fulfilling the sales goal
captureRate		|					| A metric to evaluate how well the retailer attracting customers
laborEfficiency |					| A metric to evaluate how well the retailer allocating labors according the traffic
usedBudgetRate	|					| A metric to show the percentage of used budget
shopperYield	|					| A metric to show the overall performance of retailer
atv				|					| A metric to show the average transaction value of the retailer
conversion		|					| A metric to evaluate how well the retailer creating profit
basicMetrics	|					| A bunch of basic metrics to show the performance of retailer
				| walkIn			|
				| walkBy			|
				| goal				|
				| sales 	        |
				| validSales 		|
				| lastTermSales 	|
				| transactionsCount |
				| validTCount 		|
				| budget 			|
				| laborHours 		|
				| laborCost 		|
				| lastTermCost 		|
				| efficientSlots 	|
				| elapseSlots 		|
				| updatedAt 		|

## Cache
> The **Cache** JSON structured like this:

```json
{
    "date": "2016-06-24T00:00:00Z",
    "cache": "... the edits you want to save in here ..."
}
```

### Description
The edits cache is for front-end to help user[Manager] temporarily store the schedules edits.

### Attributes
Attribute   | Description
----------- | ------------
date        | The date of availability. __ISO RFC3336__ Date with zone offset.
cache       | The free text contains schedules edits from user[Manager]

## Slot
> The **Slot** JSON structured like this:

```json
{  
    "id":209,
    "date":"2016-06-24T00:00:00Z",
    "dayOfWeek":"FRIDAY",
    "type":"SCHEDULE",
    "offType":null,
    "source":"PUBLISHED",
    "owner":{  
       "uid":1696,
       "name":"fengping",
       "email":"fengping.hu@percolata.com",
       "phone":"18600613412"
    },
    "available":{  
       "from":"2016-06-24T10:00:00Z",
       "to":"2016-06-24T18:00:00Z",
       "repeat":"NONE"
    },
    "shift":{  
       "from":"2016-06-24T10:00:00Z",
       "to":"2016-06-24T18:00:00Z",
       "location":{  
          "corporateId":1,
          "districtId":3,
          "name":"UniQlo 508",
          "address":"111 Powell St, San Francisco, CA 94102"
       },
       "breaks":[  
          {  
             "type":"PAID",
             "start":"2016-06-24T12:00:00Z",
             "end":"2016-06-24T14:00:00Z"
          }
       ]
    },
    "createdAt":"2016-06-19T18:51:23Z",
    "updatedAt":"2016-06-24T08:05:23Z"
 }
```
### Description

A **Slot** is a time slot for a employee representing its schedule of a specific day. It could be a **_AVAILABILITY_**, **_SHIFT_** or **_DAY OFF_**. 

<aside class="warning">
Restricts: A employee can only have one for **Slot** each day.
</aside>

### Attributes
Attribute   | Sub-Attribute | Sub-sub-Attrs	| Description
----------- | ------------- | ------------- | ------------
id          |               |				| Unique ID of the **Slot**.
date        |               |				| The date of the **Slot** belongs to.
dayOfWeek   |               |				| The day of week of the date.
type        |               |				| The type of the **Slot**, **_AVAILABILITY_**, **_SCHEDULE_**, **_DAYOFF_**, **_OCCUPIED_**.
offType     |               |				| The request-off type
source      |               |				| A status representing the source of **Slot**, **_PUBLISHED_**, **_EDITED_**, **_GENERATED_**.
owner       |               |				| The attributes explicit the owner of **Slot**
            | uid           |				| The __uid__ of the owner
            | name          |				| The full name of the owner
            | email         |				| The email address of the owner
            | phone         |				| The phone number of the owner
available   |               |				| Attribute that representing owner's availability of the __date__
            | from          |				| The from date time of availability. __ISO RFC3336__ Date with zone offset. E.g.: 2006-01-01T00:00:00Z.
            | to            |				| The to date time of availability. __ISO RFC3336__ Date with zone offset. E.g.: 2006-01-01T00:00:00Z.
            | repeat        |				| A flag representing whether the availability is repeat. **_WEEKLY_**, **_NONE_**
shift       |               |				| Attribute that representing owner's shift time of the __date__
            | from          |				| The from date time of shift. __ISO RFC3336__ Date with zone offset. E.g.: 2006-01-01T00:00:00Z.
            | to            |				| The to date time of shift. __ISO RFC3336__ Date with zone offset. E.g.: 2006-01-01T00:00:00Z.
            | location      |				| The work location of the shift
            |       		| corporateId	| The Corporate ID of the shift location
            |       		| districtId	| The District ID of the shift location
            |       		| name			| The Name of the shift location
            |       		| address		| The Address of the shift location
            | breaks	    |				| A list of breaks indicates break times in this shift
            |       		| type			| The **_Type_** of the break. **_PAID_**, **_UNPAID_**
            |       		| start			| The start date time of the break. __ISO RFC3336__ Date with zone offset. E.g.: 2006-01-01T00:00:00Z.
            |       		| end			| The end date time of the break. __ISO RFC3336__ Date with zone offset. E.g.: 2006-01-01T00:00:00Z.
createdAt   |               |               | The creation date time of the **Slot**
updatedAt   |               |               | The update date time of the **Slot**

# ACL (Access Control List)

## Get ACL of User

> The **Response** JSON structured like this:

```json
{  
  "messages": [
    "ACLs has been fetched!"
  ],
  "success": true,
  "result": {
	    "uid": 34,
	    "corporateId": null,
	    "initialized": true,
	    "authorityLevel": null,
	    "authorities": [
	      "ROLE_STORE_MANAGER",
	      "ROLE_STORE_ASSOCIATE"
	    ],
	    "districtACLs": [
	      17,
	      1,
	      2,
	      3
	    ],
	    "storesMap": {
	      "1": {
	        "bizHours": [
	          {
	            "storeId": 1,
	            "type": "OPEN",
	            "mon": "08:00:00",
	            "tues": "08:00:00",
	            "wed": "08:00:00",
	            "thur": "08:00:00",
	            "fri": "08:00:00",
	            "sat": "08:00:00",
	            "sun": "09:00:00"
	          },
	          {
	            "storeId": 1,
	            "type": "CLOSE",
	            "mon": "21:00:00",
	            "tues": "21:00:00",
	            "wed": "21:00:00",
	            "thur": "21:00:00",
	            "fri": "21:00:00",
	            "sat": "21:00:00",
	            "sun": "18:00:00"
	          }
	        ],
	        "timeZone": "America/Los_Angeles",
	        "address": "949 Industrial Ave, Palo Alto, CA 94303",
	        "name": "Percolata",
	        "icon": null,
	        "schedulers": null,
	        "trafficFormula": null,
	        "storeId": 1,
	        "locationId": 39,
	        "districtId": 1,
	        "corporateId": 1
	      },
	      "2": {
	        "bizHours": [
	          {
	            "storeId": 2,
	            "type": "OPEN",
	            "mon": "09:00:00",
	            "tues": "09:00:00",
	            "wed": "09:00:00",
	            "thur": "09:00:00",
	            "fri": "09:00:00",
	            "sat": "09:00:00",
	            "sun": "10:00:00"
	          },
	          {
	            "storeId": 2,
	            "type": "CLOSE",
	            "mon": "22:00:00",
	            "tues": "22:00:00",
	            "wed": "22:00:00",
	            "thur": "22:00:00",
	            "fri": "22:00:00",
	            "sat": "22:00:00",
	            "sun": "19:00:00"
	          }
	        ],
	        "timeZone": "America/Los_Angeles",
	        "address": "2656 Richmond Ave, New York, NY 10314",
	        "name": "Test - San Francisco",
	        "icon": null,
	        "schedulers": "{\"SIMPLE\": \"GL\", \"LINEAR OPTIMIZER\": \"SHAUN\"}",
	        "trafficFormula": null,
	        "storeId": 2,
	        "locationId": 507,
	        "districtId": 2,
	        "corporateId": 1
	      },
	      "3": {
	        "bizHours": [
	          {
	            "storeId": 3,
	            "type": "OPEN",
	            "mon": "09:00:00",
	            "tues": "09:00:00",
	            "wed": "09:00:00",
	            "thur": "09:00:00",
	            "fri": "09:00:00",
	            "sat": "09:00:00",
	            "sun": "10:00:00"
	          },
	          {
	            "storeId": 3,
	            "type": "CLOSE",
	            "mon": "22:00:00",
	            "tues": "22:00:00",
	            "wed": "22:00:00",
	            "thur": "22:00:00",
	            "fri": "22:00:00",
	            "sat": "22:00:00",
	            "sun": "19:00:00"
	          }
	        ],
	        "timeZone": "America/Los_Angeles",
	        "address": "111 Powell St, San Francisco, CA 94102",
	        "name": "UniQlo 508",
	        "icon": null,
	        "schedulers": null,
	        "trafficFormula": null,
	        "storeId": 3,
	        "locationId": 508,
	        "districtId": 3,
	        "corporateId": 1
	      }
	    },
	    "privilege": {
	      "title": null,
	      "viewOnDuty": true,
	      "viewOnCall": true,
	      "viewTodayNumbers": true,
	      "viewMonthNumbers": true,
	      "viewAnnualNumbers": true,
	      "viewSalesGoal": true,
	      "viewBudget": true,
	      "viewActualSales": true,
	      "viewLaborCost": true,
	      "viewHistogram": true,
	      "viewSchedules": true,
	      "editSchedules": true,
	      "includeLabors": true,
	      "reviewSchedules": true,
	      "publishSchedules": true,
	      "doubleApproval": false,
	      "viewRequests": true,
	      "reviewRequests": true,
	      "viewTeam": true,
	      "editTeam": true,
	      "viewTeamCompensation": true,
	      "viewTeamRanking": true,
	      "viewReports": true,
	      "viewSetting": true,
	      "editSetting": true,
	      "level": 0
	    },
	    "expiredAt": "2016-07-20T12:25:46.447+0000",
	    "storeManager": false
	  }
	}
}
```

This endpoint retrieves current user's ACL, it contains its authorities, position, level and others.

### HTTP Request

**_GET_** `/api/v2/acl`

## Refresh ACL of User
> The **Response** JSON structured like this:

```json
{  
  "messages": [
    "ACLs has been fetched!"
  ],
  "success": true,
  "result": {
	    "uid": 34,
	    "corporateId": null,
	    "initialized": true,
	    "authorityLevel": null,
	    "authorities": [
	      "ROLE_STORE_MANAGER",
	      "ROLE_STORE_ASSOCIATE"
	    ],
	    "districtACLs": [
	      17,
	      1,
	      2,
	      3
	    ],
	    "storesMap": {
	      "1": {
	        "bizHours": [
	          {
	            "storeId": 1,
	            "type": "OPEN",
	            "mon": "08:00:00",
	            "tues": "08:00:00",
	            "wed": "08:00:00",
	            "thur": "08:00:00",
	            "fri": "08:00:00",
	            "sat": "08:00:00",
	            "sun": "09:00:00"
	          },
	          {
	            "storeId": 1,
	            "type": "CLOSE",
	            "mon": "21:00:00",
	            "tues": "21:00:00",
	            "wed": "21:00:00",
	            "thur": "21:00:00",
	            "fri": "21:00:00",
	            "sat": "21:00:00",
	            "sun": "18:00:00"
	          }
	        ],
	        "timeZone": "America/Los_Angeles",
	        "address": "949 Industrial Ave, Palo Alto, CA 94303",
	        "name": "Percolata",
	        "icon": null,
	        "schedulers": null,
	        "trafficFormula": null,
	        "storeId": 1,
	        "locationId": 39,
	        "districtId": 1,
	        "corporateId": 1
	      },
	      "2": {
	        "bizHours": [
	          {
	            "storeId": 2,
	            "type": "OPEN",
	            "mon": "09:00:00",
	            "tues": "09:00:00",
	            "wed": "09:00:00",
	            "thur": "09:00:00",
	            "fri": "09:00:00",
	            "sat": "09:00:00",
	            "sun": "10:00:00"
	          },
	          {
	            "storeId": 2,
	            "type": "CLOSE",
	            "mon": "22:00:00",
	            "tues": "22:00:00",
	            "wed": "22:00:00",
	            "thur": "22:00:00",
	            "fri": "22:00:00",
	            "sat": "22:00:00",
	            "sun": "19:00:00"
	          }
	        ],
	        "timeZone": "America/Los_Angeles",
	        "address": "2656 Richmond Ave, New York, NY 10314",
	        "name": "Test - San Francisco",
	        "icon": null,
	        "schedulers": "{\"SIMPLE\": \"GL\", \"LINEAR OPTIMIZER\": \"SHAUN\"}",
	        "trafficFormula": null,
	        "storeId": 2,
	        "locationId": 507,
	        "districtId": 2,
	        "corporateId": 1
	      },
	      "3": {
	        "bizHours": [
	          {
	            "storeId": 3,
	            "type": "OPEN",
	            "mon": "09:00:00",
	            "tues": "09:00:00",
	            "wed": "09:00:00",
	            "thur": "09:00:00",
	            "fri": "09:00:00",
	            "sat": "09:00:00",
	            "sun": "10:00:00"
	          },
	          {
	            "storeId": 3,
	            "type": "CLOSE",
	            "mon": "22:00:00",
	            "tues": "22:00:00",
	            "wed": "22:00:00",
	            "thur": "22:00:00",
	            "fri": "22:00:00",
	            "sat": "22:00:00",
	            "sun": "19:00:00"
	          }
	        ],
	        "timeZone": "America/Los_Angeles",
	        "address": "111 Powell St, San Francisco, CA 94102",
	        "name": "UniQlo 508",
	        "icon": null,
	        "schedulers": null,
	        "trafficFormula": null,
	        "storeId": 3,
	        "locationId": 508,
	        "districtId": 3,
	        "corporateId": 1
	      }
	    },
	    "privilege": {
	      "title": null,
	      "viewOnDuty": true,
	      "viewOnCall": true,
	      "viewTodayNumbers": true,
	      "viewMonthNumbers": true,
	      "viewAnnualNumbers": true,
	      "viewSalesGoal": true,
	      "viewBudget": true,
	      "viewActualSales": true,
	      "viewLaborCost": true,
	      "viewHistogram": true,
	      "viewSchedules": true,
	      "editSchedules": true,
	      "includeLabors": true,
	      "reviewSchedules": true,
	      "publishSchedules": true,
	      "doubleApproval": false,
	      "viewRequests": true,
	      "reviewRequests": true,
	      "viewTeam": true,
	      "editTeam": true,
	      "viewTeamCompensation": true,
	      "viewTeamRanking": true,
	      "viewReports": true,
	      "viewSetting": true,
	      "editSetting": true,
	      "level": 0
	    },
	    "expiredAt": "2016-07-20T12:25:46.447+0000",
	    "storeManager": false
	  }
	}
}
```

This endpoint refreshes and retrieves current user's ACL.

### HTTP Request

**_GET_** `/api/v2/acl/refresh`

## Get Store Details

> The **Response** JSON structured like this:

```json
{  
  "messages": [
    "ACLs has been fetched!"
  ],
  "success": true,
  "result": {
	  "bizHours": [
	    {
	      "storeId": 1,
	      "type": "OPEN",
	      "mon": "08:00:00",
	      "tues": "08:00:00",
	      "wed": "08:00:00",
	      "thur": "08:00:00",
	      "fri": "08:00:00",
	      "sat": "08:00:00",
	      "sun": "09:00:00"
	    },
	    {
	      "storeId": 1,
	      "type": "CLOSE",
	      "mon": "21:00:00",
	      "tues": "21:00:00",
	      "wed": "21:00:00",
	      "thur": "21:00:00",
	      "fri": "21:00:00",
	      "sat": "21:00:00",
	      "sun": "18:00:00"
	    }
	  ],
	  "timeZone": "America/Los_Angeles",
	  "address": "949 Industrial Ave, Palo Alto, CA 94303",
	  "name": "Percolata",
	  "icon": null,
	  "schedulers": null,
	  "trafficFormula": null,
	  "storeId": 1,
	  "locationId": 39,
	  "districtId": 1,
	  "corporateId": 1
	}
}
```
This endpoint refreshes and retrieves current user's ACL.

### HTTP Request

**_GET_** `/api/v2/acl/stores/{districtid}`

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.

# Schedules

## Get Schedules of Store

> The **Response** JSON structured like this:

```json
{  
   "messages":[  
      "SCHEDULES FOR STORE HAVE BEEN PULLED SUCCESSFULLY"
   ],
   "success":true,
   "result":{  
      "from":"2016-06-21T00:00:00Z",
      "to":"2016-06-28T00:00:00Z",
      "schedules":[  
         {  
            "id":206,
            "date":"2016-06-21T00:00:00Z",
            "dayOfWeek":"TUESDAY",
            "type":"DAYOFF",
            "offType":null,
            "source":"PUBLISHED",
            "owner":{  
               "uid":1696,
               "name":"fengping",
               "email":"fengping.hu@percolata.com",
               "phone":"18600613412"
            },
            "available":{  
               "from":"2016-06-21T09:00:00Z",
               "to":"2016-06-21T22:00:00Z",
               "repeat":"NONE"
            },
            "shift":null,
            "createdAt":"2016-06-15T03:18:50Z",
            "updatedAt":"2016-06-24T08:05:23Z"
         },
         {  
            "id":208,
            "date":"2016-06-23T00:00:00Z",
            "dayOfWeek":"THURSDAY",
            "type":"AVAILABILITY",
            "offType":null,
            "source":"PUBLISHED",
            "owner":{  
               "uid":1696,
               "name":"fengping",
               "email":"fengping.hu@percolata.com",
               "phone":"18600613412"
            },
            "available":{  
               "from":"2016-06-23T10:00:00Z",
               "to":"2016-06-23T18:00:00Z",
               "repeat":"NONE"
            },
            "shift":null,
            "createdAt":"2016-06-19T18:50:59Z",
            "updatedAt":"2016-06-24T08:05:23Z"
         },
         {  
            "id":209,
            "date":"2016-06-24T00:00:00Z",
            "dayOfWeek":"FRIDAY",
            "type":"SCHEDULE",
            "offType":null,
            "source":"PUBLISHED",
            "owner":{  
               "uid":1696,
               "name":"fengping",
               "email":"fengping.hu@percolata.com",
               "phone":"18600613412"
            },
            "available":{  
               "from":"2016-06-24T10:00:00Z",
               "to":"2016-06-24T18:00:00Z",
               "repeat":"NONE"
            },
            "shift":{  
               "from":"2016-06-24T10:00:00Z",
               "to":"2016-06-24T18:00:00Z",
               "location":{  
                  "corporateId":1,
                  "districtId":3,
                  "name":"UniQlo 508",
                  "address":"111 Powell St, San Francisco, CA 94102"
               },
               "breaks":[  
                  {  
                     "type":"PAID",
                     "start":"2016-06-24T12:00:00Z",
                     "end":"2016-06-24T14:00:00Z"
                  }
               ]
            },
            "createdAt":"2016-06-19T18:51:23Z",
            "updatedAt":"2016-06-24T08:05:23Z"
         },
         {  
            "id":null,
            "date":"2016-06-22T00:00:00Z",
            "dayOfWeek":"WEDNESDAY",
            "type":"AVAILABILITY",
            "offType":null,
            "source":"PUBLISHED",
            "owner":{  
               "uid":1695,
               "name":"Yidong zhang",
               "email":"yidong.m8@percolata.com",
               "phone":"112233"
            },
            "available":{  
               "from":"2016-06-22T01:00:00Z",
               "to":"2016-06-22T23:00:00Z",
               "repeat":"WEEKLY"
            },
            "shift":null,
            "createdAt":"2016-07-19T15:25:09.682Z",
            "updatedAt":"2016-07-19T15:25:09.682Z"
         }
      ],
      "staffing":[  
      ]
   }
}
```

This endpoint retrieves all Schedules within the from & to range. The staffing list would contains the information of employee who is inactived but has schedules in the range.

### HTTP Request

**_GET_** `/api/v2/m/schedules/{districtid}`

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.

### Query Parameters
Parameter   | Value Type | Description
----------- |:----------:| -----------
from        |  *String*  | (Included) ISO RFC3336 Date with zone offset. E.g.: 2006-01-01T00:00:00Z.
to          |  *String*  | (Excluded) ISO RFC3336 Date with zone offset. E.g.: 2006-01-02T00:00:00Z.

<aside class="warning">
Restricts: [to] date must be after [from]
</aside>

## Update Schedules of Store

> The **Response** JSON structured like this:

```json
{  
   "messages":[  
      "SCHEDULES HAVE BEEN UPDATED SUCCESSFULLY!"
   ],
   "success":true,
   "result":
}
```

This endpoint publish all the updates of schedules for store.

### HTTP Request

**_POST_** `/api/v2/m/schedules/{districtid}`

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.

> The **Request Body** Json structured like this:

```json
{  
   "from":"2016-06-21T00:00:00Z",
   "to":"2016-06-28T00:00:00Z",
   "schedules":[  
      {  
         "id":206,
         "date":"2016-06-21T00:00:00Z",
         "dayOfWeek":"TUESDAY",
         "type":"DAYOFF",
         "offType":null,
         "source":"PUBLISHED",
         "owner":{  
            "uid":1696,
            "name":"fengping",
            "email":"fengping.hu@percolata.com",
            "phone":"18600613412"
         },
         "available":{  
            "from":"2016-06-21T09:00:00Z",
            "to":"2016-06-21T22:00:00Z",
            "repeat":"NONE"
         },
         "shift":null,
         "createdAt":"2016-06-15T03:18:50Z",
         "updatedAt":"2016-06-24T08:05:23Z"
      },
      {  
         "id":208,
         "date":"2016-06-23T00:00:00Z",
         "dayOfWeek":"THURSDAY",
         "type":"AVAILABILITY",
         "offType":null,
         "source":"PUBLISHED",
         "owner":{  
            "uid":1696,
            "name":"fengping",
            "email":"fengping.hu@percolata.com",
            "phone":"18600613412"
         },
         "available":{  
            "from":"2016-06-23T10:00:00Z",
            "to":"2016-06-23T18:00:00Z",
            "repeat":"NONE"
         },
         "shift":null,
         "createdAt":"2016-06-19T18:50:59Z",
         "updatedAt":"2016-06-24T08:05:23Z"
      }
   ]
} 
```

### Request Body
Field       | Description
 ---------- | -----------
from        | **(Included)** ISO RFC3336 Date with zone offset. E.g.: 2006-01-01T00:00:00Z.
to          | **(Excluded)** ISO RFC3336 Date with zone offset. E.g.: 2006-01-02T00:00:00Z.
schedules   | A list of **_Slot_** Objects that contains the updates you want to publish

## Get Caches of Schedules Edits

> The **Response** JSON structured like this:

```json
{  
   "messages":[  
      "SCHEDULES HAVE BEEN UPDATED SUCCESSFULLY!"
   ],
   "success":true,
   "result": [
   		{
		    "date": "2016-06-24T00:00:00Z",
		    "cache": "... the edits you want to save in here ..."
		},
		{
		    "date": "2016-06-25T00:00:00Z",
		    "cache": "... the edits you want to save in here ..."
		}
   ]
}
```

This endpoints retrieves Schedules Edits of User[Manager] within the period.

### HTTP Request

**_GET_** `/api/v2/m/schedules/{districtid}/caches`

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.

### Query Parameters
Parameter   | Value Type | Description
----------- |:----------:| -----------
from        |  *String*  | (Included) ISO RFC3336 Date with zone offset. E.g.: 2006-01-01T00:00:00Z.
to          |  *String*  | (Excluded) ISO RFC3336 Date with zone offset. E.g.: 2006-01-02T00:00:00Z.

<aside class="warning">
Restricts: [to] date must be after [from]
</aside>

## Deposit Caches of Schedules Edits

> The **Response** JSON structured like this:

```json
{  
   "messages":[  
      "SCHEDULES HAVE BEEN UPDATED SUCCESSFULLY!"
   ],
   "success":true,
   "result":
}
```

This endpoints deposits Schedules Edits of User[Manager] temporarily.

### HTTP Request

**_POST_** `/api/v2/m/schedules/{districtid}/caches`

> The **Request Body** Json structured like this:

```json
[
	{
	    "date": "2016-06-24T00:00:00Z",
	    "cache": "... the edits you want to save in here ..."
	},
	{
	    "date": "2016-06-25T00:00:00Z",
	    "cache": "... the edits you want to save in here ..."
	}
]
```

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.

### Request Body
Field       | Description
 ---------- | -----------
caches      | A list of daily caches 


## Get all Shifts of current date from the Store

> The **Response** JSON structured like this:

```json
{  
   "messages":[  
      "SCHEDULES HAVE BEEN UPDATED SUCCESSFULLY!"
   ],
   "success":true,
   "result": [
   		{  
            "id":209,
            "date":"2016-06-24T00:00:00Z",
            "dayOfWeek":"FRIDAY",
            "type":"SCHEDULE",
            "offType":null,
            "source":"PUBLISHED",
            "owner":{  
               "uid":1696,
               "name":"fengping",
               "email":"fengping.hu@percolata.com",
               "phone":"18600613412"
            },
            "available":{  
               "from":"2016-06-24T10:00:00Z",
               "to":"2016-06-24T18:00:00Z",
               "repeat":"NONE"
            },
            "shift":{  
               "from":"2016-06-24T10:00:00Z",
               "to":"2016-06-24T18:00:00Z",
               "location":{  
                  "corporateId":1,
                  "districtId":3,
                  "name":"UniQlo 508",
                  "address":"111 Powell St, San Francisco, CA 94102"
               },
               "breaks":[  
                  {  
                     "type":"PAID",
                     "start":"2016-06-24T12:00:00Z",
                     "end":"2016-06-24T14:00:00Z"
                  }
               ]
            },
            "createdAt":"2016-06-19T18:51:23Z",
            "updatedAt":"2016-06-24T08:05:23Z"
         },
         {  
            "id":209,
            "date":"2016-06-25T00:00:00Z",
            "dayOfWeek":"FRIDAY",
            "type":"SCHEDULE",
            "offType":null,
            "source":"PUBLISHED",
            "owner":{  
               "uid":1697,
               "name":"Shawn",
               "email":"shawn.wang@percolata.com",
               "phone":"18600613412"
            },
            "available":{  
               "from":"2016-06-25T10:00:00Z",
               "to":"2016-06-25T18:00:00Z",
               "repeat":"NONE"
            },
            "shift":{  
               "from":"2016-06-25T10:00:00Z",
               "to":"2016-06-25T18:00:00Z",
               "location":{  
                  "corporateId":1,
                  "districtId":3,
                  "name":"UniQlo 508",
                  "address":"111 Powell St, San Francisco, CA 94102"
               },
               "breaks":[  
                  {  
                     "type":"PAID",
                     "start":"2016-06-25T12:00:00Z",
                     "end":"2016-06-25T14:00:00Z"
                  }
               ]
            },
            "createdAt":"2016-06-19T18:51:23Z",
            "updatedAt":"2016-06-25T08:05:23Z"
         }
     ]
}
```

This endpoint fetch all Shifts of current date from the Store.

### HTTP Request

**_GET_** `/api/v2/m/schedules/{districtid}/onduty`

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.

## Get all Available of current date from the Store

> The **Response** JSON structured like this:

```json
{  
   "messages":[  
      "SCHEDULES HAVE BEEN UPDATED SUCCESSFULLY!"
   ],
   "success":true,
   "result": [
   		{  
            "id":208,
            "date":"2016-06-23T00:00:00Z",
            "dayOfWeek":"THURSDAY",
            "type":"AVAILABILITY",
            "offType":null,
            "source":"PUBLISHED",
            "owner":{  
               "uid":1696,
               "name":"fengping",
               "email":"fengping.hu@percolata.com",
               "phone":"18600613412"
            },
            "available":{  
               "from":"2016-06-23T10:00:00Z",
               "to":"2016-06-23T18:00:00Z",
               "repeat":"NONE"
            },
            "shift":null,
            "createdAt":"2016-06-19T18:50:59Z",
            "updatedAt":"2016-06-24T08:05:23Z"
        },
   		{  
            "id":null,
            "date":"2016-06-22T00:00:00Z",
            "dayOfWeek":"WEDNESDAY",
            "type":"AVAILABILITY",
            "offType":null,
            "source":"PUBLISHED",
            "owner":{  
               "uid":1695,
               "name":"Yidong zhang",
               "email":"yidong.m8@percolata.com",
               "phone":"112233"
            },
            "available":{  
               "from":"2016-06-22T01:00:00Z",
               "to":"2016-06-22T23:00:00Z",
               "repeat":"WEEKLY"
            },
            "shift":null,
            "createdAt":"2016-07-19T15:25:09.682Z",
            "updatedAt":"2016-07-19T15:25:09.682Z"
        }
     ]
}

```

This endpoint fetch all Availability of current date from the Store.

### HTTP Request
**_GET_** `/api/v2/m/schedules/{districtid}/oncall`

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.

## Copy Schedules to certain week

This endpoint will copy certian schedules to a furture week

### HTTP Request
**_POST_** `/api/v2/m/schedules/{districtid}/copy`

> The **Request Body** Json structured like this:

```json
{  
   "from":"2016-06-21T00:00:00Z",
   "to":"2016-06-28T00:00:00Z",
   "schedules":[  
      {  
         "id":206,
         "date":"2016-06-21T00:00:00Z",
         "dayOfWeek":"TUESDAY",
         "type":"DAYOFF",
         "offType":null,
         "source":"PUBLISHED",
         "owner":{  
            "uid":1696,
            "name":"fengping",
            "email":"fengping.hu@percolata.com",
            "phone":"18600613412"
         },
         "available":{  
            "from":"2016-06-21T09:00:00Z",
            "to":"2016-06-21T22:00:00Z",
            "repeat":"NONE"
         },
         "shift":null,
         "createdAt":"2016-06-15T03:18:50Z",
         "updatedAt":"2016-06-24T08:05:23Z"
      },
      {  
         "id":208,
         "date":"2016-06-23T00:00:00Z",
         "dayOfWeek":"THURSDAY",
         "type":"AVAILABILITY",
         "offType":null,
         "source":"PUBLISHED",
         "owner":{  
            "uid":1696,
            "name":"fengping",
            "email":"fengping.hu@percolata.com",
            "phone":"18600613412"
         },
         "available":{  
            "from":"2016-06-23T10:00:00Z",
            "to":"2016-06-23T18:00:00Z",
            "repeat":"NONE"
         },
         "shift":null,
         "createdAt":"2016-06-19T18:50:59Z",
         "updatedAt":"2016-06-24T08:05:23Z"
      }
   ]
} 
```

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.

### Request Body
Field       | Description
 ---------- | -----------
from        | **(Included)** ISO RFC3336 Date with zone offset. E.g.: 2006-01-01T00:00:00Z.
to          | **(Excluded)** ISO RFC3336 Date with zone offset. E.g.: 2006-01-02T00:00:00Z.
schedules   | A list of **_Slot_** Objects that contains the updates you want to publish


# Retail Performance 

## fetch Overall Performance of Store within the period

> The **Response** JSON structured like this:

```json
{
  "messages": [
    "ANNUALLY PERFORMANCE HAS BEEN CALCULATED SUCCESSFULLY ..."
  ],
  "success": true,
  "result": {
    "districtId": 0,
    "basicMetrics": {
      "walkIn": 41883,
      "walkBy": 85545,
      "goal": 651800.5999999999,
      "sales": 653809.073638916,
      "validSales": 638004.703207016,
      "lastTermSales": 700264.045396544,
      "transactionsCount": 7496,
      "validTCount": 7408,
      "budget": 42666.01000000008,
      "laborHours": 1451.25,
      "laborCost": 11134.900000000005,
      "lastTermCost": 0.0,
      "efficientSlots": 545,
      "elapseSlots": 9107,
      "updatedAt": "2016-07-20T06:29:06.233Z"
    },
    "completionRate": 1.003081423427527,
    "captureRate": 0.3286797250211884,
    "laborEfficiency": 0.05984407598550565,
    "usedBudgetRate": 0.26097823536815334,
    "shopperYield": 15.233023021441062,
    "atv": 86.12374503334449,
    "conversion": 0.17687367189551848
  }
}
```

This endpoint retrieves the retail performances of a store.

### HTTP Request

**_GET_** `/api/v2/m/performance/{districtid}`

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.

### Query Parameters
Parameter   | Value Type | Description
----------- |:----------:| -----------
from        |  *String*  | (Included) ISO RFC3336 Date with zone offset. E.g.: 2006-01-01T00:00:00Z.
to          |  *String*  | (Excluded) ISO RFC3336 Date with zone offset. E.g.: 2006-01-02T00:00:00Z.

## fetch actual labors & cost of store

### HTTP Request
> The **Response** JSON structured like this:

```json
{
  "messages": [
    "ANNUALLY PERFORMANCE HAS BEEN CALCULATED SUCCESSFULLY ..."
  ],
  "success": true,
  "result": [
		{
		    "date": "2016-06-24T00:00:00Z",
		    "hours": 48.0,
		    "cost": 743.5
		},
		{
		    "date": "2016-06-25T00:00:00Z",
		    "hours": 58.0,
		    "cost": 1043.5
		}
	]
}
```

This endpoint fetch the actual labor hours & cost within the period

**_GET_** `/api/v2/m/performance/{districtid}/labors`

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.

### Query Parameters
Parameter   | Value Type | Description
----------- |:----------:| -----------
from        |  *String*  | (Included) ISO RFC3336 Date with zone offset. E.g.: 2006-01-01T00:00:00Z.
to          |  *String*  | (Excluded) ISO RFC3336 Date with zone offset. E.g.: 2006-01-02T00:00:00Z.

## fetch actual sales of store
> The **Response** JSON structured like this:

```json
{
  "messages": [
    "ANNUALLY PERFORMANCE HAS BEEN CALCULATED SUCCESSFULLY ..."
  ],
  "success": true,
  "result": [
		{
		    "date": "2016-06-24T00:00:00Z",
		    "sales": 10743.43
		},
		{
		    "date": "2016-06-25T00:00:00Z",
		    "sales": 10743.43
		}
	]
}
```

This endpoint fetch the actual sales within the period

### HTTP Request
**_GET_** `/api/v2/m/performance/{districtid}/sales`

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.

### Query Parameters
Parameter   | Value Type | Description
----------- |:----------:| -----------
from        |  *String*  | (Included) ISO RFC3336 Date with zone offset. E.g.: 2006-01-01T00:00:00Z.
to          |  *String*  | (Excluded) ISO RFC3336 Date with zone offset. E.g.: 2006-01-02T00:00:00Z.

# Financial Plans

## Fetch Financial Labor Plan
> The **Response** JSON structured like this:

```json
{
  "messages": [
    "LABOR PLAN HAS BEEN FETCHED SUCCESSFULLY FOR STORE#3"
  ],
  "success": true,
  "result": {
    "from": "2016-07-01T00:00:00-07:00",
    "to": "2016-08-01T00:00:00-07:00",
    "budget": 0,
    "laborHour": 0
  }
}
```

This endpoint will fetch the labor plan of the store within the period, which indicates the labor budget of the store for a certain period

### HTTP Request
**_GET_** `/api/v2/m/financial/{districtid}/budget`

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.

### Query Parameters
Parameter   | Value Type | Description
----------- |:----------:| -----------
from        |  *String*  | (Included) ISO RFC3336 Date with zone offset. E.g.: 2006-01-01T00:00:00Z.
to          |  *String*  | (Excluded) ISO RFC3336 Date with zone offset. E.g.: 2006-01-02T00:00:00Z.


## Fetch Financial Sales Plan
> The **Response** JSON structured like this:

```json
{
  "messages": [
    "SALES PLAN HAS BEEN FETCHED SUCCESSFULLY FOR STORE#3"
  ],
  "success": true,
  "result": {
    "from": "2016-06-30T17:00:00-07:00",
    "to": "2016-07-31T17:00:00-07:00",
    "productGoal": 0,
    "serviceGoal": 0
  }
}
```

This endpoint will fetch the sales plan of the store within the period, which indicates the sales goal of the store for a certain period.

### HTTP Request
**_GET_** `/api/v2/m/financial/{districtid}/goal`

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.

### Query Parameters
Parameter   | Value Type | Description
----------- |:----------:| -----------
from        |  *String*  | (Included) ISO RFC3336 Date with zone offset. E.g.: 2006-01-01T00:00:00Z.
to          |  *String*  | (Excluded) ISO RFC3336 Date with zone offset. E.g.: 2006-01-02T00:00:00Z.

# Team & Staffing

## Fetch Staffing roster of Store
> The **Response** JSON structured like this:

```json
{
  "messages": [
    "STAFFING HAS BEEN FETCHED SUCCESSFULLY FOR STORE#3"
  ],
  "success": true,
  "result": [
        {
          "uid": 32,
          "name": "alpha11",
          "email": "alpha11@calendar.percolata.com",
          "phone": "4084751649",
          "corporateId": 1,
          "districtId": null,
          "weeklyMaxHours": 40,
          "weeklyMinHours": 0,
          "wages": 15,
          "wagesType": "HOURLY",
          "commission": 0.1,
          "field": false,
          "employmentStatus": "FULLTIME",
          "position": {
            "id": 32,
            "title": "SALES",
            "level": 0,
            "authorityLevel": "STORE_ASSOCIATE",
            "privilege": {
              "title": null,
              "viewOnDuty": true,
              "viewOnCall": true,
              "viewTodayNumbers": true,
              "viewMonthNumbers": true,
              "viewAnnualNumbers": true,
              "viewSalesGoal": true,
              "viewBudget": true,
              "viewActualSales": true,
              "viewLaborCost": true,
              "viewHistogram": true,
              "viewSchedules": true,
              "editSchedules": true,
              "includeLabors": true,
              "reviewSchedules": true,
              "publishSchedules": true,
              "doubleApproval": false,
              "viewRequests": true,
              "reviewRequests": true,
              "viewTeam": true,
              "editTeam": true,
              "viewTeamCompensation": true,
              "viewTeamRanking": true,
              "viewReports": true,
              "viewSetting": true,
              "editSetting": true,
              "level": 0
            },
            "sales": true
          },
          "avatar": null
        }
    ]
}
```

This endpoints will fetch the staffing roster of the stores, which includes details of employee like wages, position, email, phone and others.

### HTTP Request
**_GET_** `/api/v2/m/staffing/{districtid}`

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.


## Update Informations of Staff
> The **Response** JSON structured like this:

```json
{
  "messages": [
    "STAFFING HAS BEEN FETCHED SUCCESSFULLY FOR STORE#3"
  ],
  "success": true,
  "result": null
}
```

### HTTP Request
**_PUT_** `/api/v2/m/staffing/{districtid}`

> The **Request Body** Json structured like this:

```json
{
  "uid": 32,
  "name": "alpha11",
  "email": "alpha11@calendar.percolata.com",
  "phone": "4084751649",
  "districtId": null,
  "weeklyMaxHours": 40,
  "weeklyMinHours": 0,
  "wages": 15,
  "wagesType": "HOURLY",
  "commission": 0.1,
  "field": false,
  "employmentStatus": "FULLTIME",
  "position": {
    "id": 32
  }
}
```

This endpoint will update some information of the employee

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.

### Request Body
Field       		| optional? | Description
------------------- | --------- | ---------------
uid					|			| The User Id of the Employee
name				|			| The name of the Employee
email				| optional	| The email of the Employee
phone				| optional	| The phone of the Employee
districtId			|			| The ID of the District the Employee work at
weeklyMaxHours		| optional	| The Weekly Max working hours of the Employee
weeklyMinHours		| optional	| The Weekly Min working hours of the Employee
wages 				| optional	| The wages of the Employee
wagesType			| optional	| The Type of the Wages. **_MONTHLY_**, **_WEEKLY_**, **_HOURLY_**, **_BI_WEEKLY_**, **_BI_MONTHLY_**, **_ANNUALLY_**
commission			| optional	| The commission rate of the Employee
field				| optional	| Whether the Employee is a on field worker
employmentStatus	|			| The Employee's Employment Status. E.g.: **_FULLTIME_**, **_PARTTIME_**
position			| optional	| The **Position** of the Employee

# Retail Traffic

## Fetch Store Traffic
> The **Response** JSON structured like this:

```json
{
  "messages": [
    "TRAFFICS HAVE BEEN FETCHED SUCCESSFULLY!"
  ],
  "success": true,
  "result": [
    {
      "occupancy": 0,
      "walkin": 0,
      "walkOut": 1,
      "time": "2016-01-01T18:00:00.000+0000",
      "timeISO": "2016-01-01T10:00:00Z"
    },
    {
      "occupancy": 1,
      "walkin": 1,
      "walkOut": 2,
      "time": "2016-01-01T18:15:00.000+0000",
      "timeISO": "2016-01-01T10:15:00Z"
    }
  ]
}
```

This endpoint will fetch all the traffic of the store within the period

### HTTP Request
**_GET_** `/api/v2/m/traffics/{districtid}`

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.

### Query Parameters
Parameter   | Value Type | Description
----------- |:----------:| -----------
from        |  *String*  | (Included) ISO RFC3336 Date with zone offset. E.g.: 2006-01-01T00:00:00Z.
to          |  *String*  | (Excluded) ISO RFC3336 Date with zone offset. E.g.: 2006-01-02T00:00:00Z.



## Fetch Store Customized Demands
> The **Response** JSON structured like this:

```json
{
  "messages": [
    "DEMANDS HAVE BEEN FETCHED SUCCESSFULLY!"
  ],
  "success": true,
  "result": [
    {
      "occupancy": 0,
      "walkin": 0,
      "walkOut": 1,
      "time": "2016-01-01T18:00:00.000+0000",
      "timeISO": "2016-01-01T10:00:00Z"
    },
    {
      "occupancy": 1,
      "walkin": 1,
      "walkOut": 2,
      "time": "2016-01-01T18:15:00.000+0000",
      "timeISO": "2016-01-01T10:15:00Z"
    }
  ]
}
```

This endpoint will fetch all the demands of the store within the period

### HTTP Request
**_GET_** `/api/v2/m/demands/{districtid}`

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.

### Query Parameters
Parameter   | Value Type | Description
----------- |:----------:| -----------
from        |  *String*  | (Included) ISO RFC3336 Date with zone offset. E.g.: 2006-01-01T00:00:00Z.
to          |  *String*  | (Excluded) ISO RFC3336 Date with zone offset. E.g.: 2006-01-02T00:00:00Z.



# Setting
## Fetch Store Setting
> The **Response** JSON structured like this:

```json
{
  "messages": [
    "STORE SETTING HAS BEEN FETCHED SUCCESSFULLY FOR STORE#3"
  ],
  "success": true,
  "result": {
    "id": 1,
    "storeId": 3,
    "weeklyOvertimePayRate": 1.5,
    "dailyOvertimePayRate": 1.5,
    "weeklyHourLimit": 40,
    "dailyHourLimit": 8,
    "paidBreak": "30/3",
    "unpaidBreak": "15/5",
    "notifySAOpenShift": "MAIL",
    "notifySAShiftReminder": "MAIL",
    "notifySASignUp": "MAIL",
    "notifySASchedulesChanges": "MAIL"
  }
}
```

This endpoint will fetch the setting of the Store

### HTTP Request
**_GET_** `/api/v2/m/setting/{districtid}/store`

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.

## Update Store Setting
> The **Response** JSON structured like this:

```json

```

### HTTP Request
**_POST_** `/api/v2/m/setting/{districtid}/store`

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.

### Request Body
Field       		            | optional? | Description
------------------------------- | --------- | ---------------
id                              |           | The ID of the Store Setting
storeId                         |           | The ID of The Store
weeklyOvertimePayRate           |           | The Weekly Overtime Pay rate
dailyOvertimePayRate            |           | The Daily Overtime Pay rate
weeklyHourLimit                 |           | The Weekly working hours limit for a Employee
dailyHourLimit                  |           | The daily working hours limit for a Employee
paidBreak                       |           | Breaks limit of Paid Type
unpaidBreak                     |           | Breaks limit of UnPaid Type
notifySAOpenShift               |           | Whether alerts Associate when a Open Shift become available
notifySAShiftReminder           |           | Whether remind store associates 2 hours in advance when their shift will start                           
notifySASignUp                  |           | Whether remind associates daily to sign up until they finally do
notifySASchedulesChanges        |           | Whether remind associates when his/her schedules have been changed

## Fetch Manager Setting of a Store
> The **Response** JSON structured like this:

```json
{
  "messages": [
    "MANAGER SETTING OF STORE#3 HAS BEEN FETCHED SUCCESSFULLY FOR USER#34"
  ],
  "success": true,
  "result": {
    "id": 1,
    "uid": 34,
    "storeId": 3,
    "laborThreshold": 2,
    "star": 6,
    "startWeekDay": "TUESDAY",
    "notifyNewRequest": "MAIL",
    "notifyIdleAssociate": "MAIL",
    "notifyWeeklySummary": "MAIL",
    "notifyPasswordChanged": "NONE"
  }
}
```

### HTTP Request
**_GET_** `/api/v2/m/setting/{districtid}/manager`

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.


## Update Manager Setting

### HTTP Request
**_POST_** `/api/v2/m/setting/{districtid}/store`

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.

### Request Body
Field       		            | optional? | Description
------------------------------- | --------- | ---------------
id                              |           | The ID of the Manager Setting 
uid                             |           | The User ID of the Manager
storeId                         |           | The Store ID of the Manager Setting
laborThreshold                  |           | labor Threshold
star                            |           | STAR
startWeekDay                    |           | The start of Day of Week
notifyNewRequest                |           | Whether alerts when a New Request coming
notifyIdleAssociate             |           | 
notifyWeeklySummary             |           | Whether send a weekly summary
notifyPasswordChanged           |           | Whether Notify when user password has been changed

# Tableau Reports

## Fetch the Tableau URL of the store
> The **Response** JSON structured like this:

```json
{
  "messages": [
    "MANAGER SETTING OF STORE#3 HAS BEEN FETCHED SUCCESSFULLY FOR USER#34"
  ],
  "success": true,
  "result": ".../.../views/..."
}
```

This endpoint will fetch the url of the tableau view of the store

### HTTP Request
**_GET_** `/api/v2/m/tableau/{districtid}/url`

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.

### Query Parameters
Parameter   | Value Type | Description
----------- |:----------:| -----------
view        |  *String*  | the Tableau view name 


## Fetch Tableau Views of the store
> The **Response** JSON structured like this:

```json
{
  "messages": [
    "MANAGER SETTING OF STORE#3 HAS BEEN FETCHED SUCCESSFULLY FOR USER#34"
  ],
  "success": true,
  "result": "...."
}
```

This endpoint will fetch tableau views of the store

### HTTP Request
**_GET_** `/api/v2/m/tableau/{districtid}/view`

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.



# Security Token Authorization & Authentication

## Authorize an Egress Token
> The **Response** JSON structured like this:

```json
{
  "messages": [
    "MANAGER SETTING OF STORE#3 HAS BEEN FETCHED SUCCESSFULLY FOR USER#34"
  ],
  "success": true,
  "result": "651290be-3f17-4655-b5ac-2feaa38f0435"
}
```

This endpoint is request a EGRESS token. It will authorize a UUID EGRESS Token 

### HTTP Request
**_GET_** `/api/v2/m/token/{districtid}/egress`

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.

# Marketing Events

## Fetch all the Marketing events of a store
> The **Response** JSON structured like this:

```json
{
  "messages": [
    "MARKETING EVENTS HAVE BEEN FETCHED SUCCESSFULLY FOR STORE#3"
  ],
  "success": true,
  "result": [
    {
      "eid": "8fc5275e-ae99-431b-b9ed-2d0d393b792c",
      "storeId": 3,
      "start": 1453795200000,
      "end": 1453880700000,
      "event": "110 growth",
      "percentage": 200
    },
    {
      "eid": "171a002b-2c9d-45fd-bd82-865230e57a09",
      "storeId": 3,
      "start": 1454400000000,
      "end": 1455003900000,
      "event": "2",
      "percentage": 2
    }
  ]
}
```

### HTTP Request
**_GET_** `/api/v2/m/events/{districtid}`

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.   

### Query Parameters
Parameter   | Value Type | Description
----------- |:----------:| -----------
from        |  *String*  | (Included) ISO RFC3336 Date with zone offset. E.g.: 2006-01-01T00:00:00Z.
to          |  *String*  | (Excluded) ISO RFC3336 Date with zone offset. E.g.: 2006-01-02T00:00:00Z.

## Update a Marketing Event
> The **Response** JSON structured like this:

### HTTP Request
**_POST_** `/api/v2/m/events/{districtid}`

> The **Request Body** Json structured like this:

```json
{
  "eid": "171a002b-2c9d-45fd-bd82-865230e57a09",
  "storeId": 3,
  "start": 1454400000000,
  "end": 1455003900000,
  "event": "2",
  "percentage": 2
}
```

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.   

### Request Body
Field       		            | optional? | Description
------------------------------- | --------- | ---------------
eid                             | required  | the UUID of the event
storeId                         |           | the store ID of the event
start                           |           | the start time of the event in millis
end                             |           | the end time of the event in millis
percentage                      |           | the increase rate in percentage
event                           |           | the name of the event

## Remove a Marketing event
> The **Response** JSON structured like this:


### HTTP Request
**_DELETE_** `/api/v2/m/events/{districtid}/{eid}`

### URL Parameters
Parameter   | Description
 ---------- | -----------
districtid  | The ID of district, a *Long* value.   
eid         | The eid of the Marketing event
