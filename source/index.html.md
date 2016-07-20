---
title: API Reference

language_tabs:
  - shell
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

# Schedules

## Get Schedules of Store
> The above command returns JSON structured like this:

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

> The Response JSON structured like this:

```json
{  
   "messages":[  
      "SCHEDULES HAVE BEEN UPDATED SUCCESSFULLY!"
   ],
   "success":true,
   "result":
}
```

This endpoint retrieves a specific kitten.

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

