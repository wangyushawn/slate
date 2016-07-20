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

## Cache
> The **Cache** JSON structred like this:

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
date        | The from date time of availability. __ISO RFC3336__ Date with zone offset.
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
type        |               |				| The type of the **Slot**, **_AVAILABILITY_**, **_SCHEDULE_**, **_DAYOFF_**.
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



