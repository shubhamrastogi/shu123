---
layout: "post"
title: "Generate Invite Link"
date: 2018-03-11
---

                                           

Description
---
Returns *inviteId* and *test links* for candidates

URL
---

```
Method Type: POST
https://BASE-URL/harvest/api/v1/generateInviteLink/{testId}
```
Sample Input Data
---
Data is sent through Body
```
{
	"candidateEmail" : ["someEmail", "SomeEmail"]   //  JSON List of Emails
}
```
Sample Response Data
---
Returns an array of Object, where each object represent a candidate .
```
[
    {
        "inviteId": 111,  //  Invite Id
        "inviteURL": "http://localhost:8080/#/rapidTest/318/userDetails?candidate=5e21f1a852cbaf55bda9b3c212663d7&sessionId=111&email=5@a.com",
        "candidateEmailId": "5@a.com"  //  Test Link
    },
    {
        "inviteId": 112,
        "inviteURL": "http://localhost:8080/#/rapidTest/318/userDetails?candidate=c5b9c21fc4e86e81bd16aff4c43f8c&sessionId=112&email=6@a.com",
        "candidateEmailId": "6@a.com"
    }
]
```

Possible Exceptions
---
```
Status Code: 600
{"errorMessage": "apiKey can't be null"}
or 
{"errorMessage": "apikey not mapped to a user"}
```
```
Status Code: 601
{"errorMessage": "Authorization failed"}
```
```
Status Code: 602
{"errorMessage": "Test should be invite only"}
or
{"errorMessage": "Invalid EMail {xxx}, No invitation send"}
or
{"errorMessage": "Cannot invite candidate on expired test"}
or
{"errorMessage": "No candidate Email found"}
or
{"errorMessage": "testId can't be null"}
```
```
Status Code: 603
{"errorMessage": "A max of 500 candidate can be invite at once"}
or
{"errorMessage": "Not enough credit"}
```


```
Status Code: 500
{"errorMessage": "Internal Server Error, please share the exception id with the CG team::Exception id is xxxxx"}
```

