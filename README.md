### Cash card rest api

### Original tutorial:
https://spring.academy

Notes:
- ?
- ?

<br>

Prep and run it locally:


```
cd ~/Downloads
```
- 
- create project from spring.io
```
mkdir -p cashcard && \
curl -o 'cashcard.tar' 'https://start.spring.io/starter.tgz?'\
'type=gradle-project&'\
'language=java&'\
'dependencies=web&'\
'name=CashCard&'\
'groupId=example&'\
'artifactId=cashcard&'\
'description=CashCard+service+for+Family+Cash+Cards&'\
'packaging=jar&'\
'packageName=example.cashcard&'\
'javaVersion=17' && \
tar -xvf 'cashcard.tar' -C 'cashcard'
```

- copy the project from the `dir` to the active branch/dir
```
cp -r . ~/IdeaProjects/spring-azure-playground
```

<br>

- example API contract:
```
Request
  URI: /cashcards/{id}
  HTTP Verb: GET
  Body: None

Response:
  HTTP Status:
    200 OK if the user is authorized and the Cash Card was successfully retrieved
    401 UNAUTHORIZED if the user is unauthenticated or unauthorized
    404 NOT FOUND if the user is authenticated and authorized but the Cash Card cannot be found
  Response Body Type: JSON
  Example Response Body:
    {
      "id": 99,
      "amount": 123.45
    }
```







<br>

---