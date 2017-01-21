	
# 2 - Test plannning and execution <br />

| 1 - login failed                                                                                                                                                                                      | Expected                                                  | Actual |Comments|
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|--------|--------|
| 1.1 - empty username                                                                                                                                                                                  | "This field is required" message                          | OK     |        |
| 1.2 - empty password                                                                                                                                                                                  | "This field is required" message                          | OK     |        |
| 1.3 - empty password and username                                                                                                                                                                     | "This field is required" message                          | OK     |        |
| 1.4 - inexistent user                                                                                                                                                                                 | "Warning! Invalid Credentials. Please try again." Message | OK     |        |
| 1.5 - wrong password                                                                                                                                                                                  | "Warning! Invalid Credentials. Please try again." Message | OK     |        |
| 1.6 - sql injection (or 1=1, or 1=1--, or 1=1#,1234 ' AND 1=0 UNION ALL SELECT 'admin', '81dc9bdb52d04dc20036dbd8313ed055,1234 ' AND 1=0 UNION ALL SELECT 'admin', '81dc9bdb52d04dc20036dbd8313ed055) | "This field is required" message                          | OK     |        |


<br />
 <br />
### 2 - login successful <br />
| 2.1 - happy path                          | Expected                                               | Actual | Comments              |
|-------------------------------------------|--------------------------------------------------------|--------|-----------------------|
| Pick a translation task                   | Translation task is opened                             | OK     |                       |
| Perform annotation - create 1 minor issue | Annotation is created                                  | OK     |                       |
| Take a break                              | Application redirected to Batch selection page         | OK     |                       |
| Go to the same task translation           | Translation task is opened with the annotation created | OK     |                       |
| Perform annotation - create 1 minor issue | Annotation is created                                  | OK     |                       |
| Check QT21 Score                          | QT21 shall be updated                                  | NOK    | Score is not updated. |
 <br />

| 2.2 - check if QT21 is correctly calculated with 2 different issues types | Expected                                               | Actual | Comments              |
|---------------------------------------------------------------------------|--------------------------------------------------------|--------|-----------------------|
| Go to Batch Selection page                                                | Batch Selection Page is opened                         | OK     |                       |

| Pick a translation task                                                   | Translation task is opened                             | OK     |                       |
| Perform annotation - create 1 major issue                                 | Annotation is created                                  | OK     |                       |
| Take a break                                                              | Application redirected to Batch selection page         | OK     |                       |
| Go to the same task translation                                           | Translation task is opened with the annotation created | OK     |                       |
| Perform annotation - create 1 minor issue                                 | Annotation is created                                  | OK     |                       |
| Check QT21 Score                                                          | QT21 shall be updated                                  | NOK    | Score is not updated. |
 
 
 <br />
 
| 2.3 - check if QT21 is correctly calculated with 3 different issues types | Expected                                               | Actual | Comments              |
|---------------------------------------------------------------------------|--------------------------------------------------------|--------|-----------------------|
| Go to Batch Selection page                                                | Batch Selection Page is opened                         | OK     |                       |
| Pick a translation task                                                   | Translation task is opened                             | OK     |                       |
| Perform annotation - create 1 minor issue                                 | Annotation is created                                  | OK     |                       |
| Take a break                                                              | Application redirected to Batch selection page         | OK     |                       |
| Go to the same task translation                                           | Translation task is opened with the annotation created | OK     |                       |
| Perform annotation - create 1 critical issue                              | Annotation is created                                  | OK     |                       |
| Take a break                                                              | Application redirected to Batch selection page         | OK     |                       |
| Go to the same task translation                                           | Translation task is opened with the annotation created | OK     |                       |
| Perform annotation - create 1 major issue                                 | Annotation is created                                  | OK     |                       |
| Check QT21 Score                                                          | QT21 shall be updated                                  | NOK    | Score is not updated. |


<br />
 
 
| 2.4 - check if QT21 is correctly calculated with 3 different issues types without breaks | Expected                   | Actual | Comments              |
|------------------------------------------------------------------------------------------|--------------------------------|--------|-----------------------|
| Go to Batch Selection page                                                               | Batch Selection Page is opened | OK     |                        |
| Pick a translation task                                                                  | Translation task is opened     | OK     |                        |
| Perform annotation - create 1 critical issue                                             | Annotation is created          | OK     |                        |
| Perform annotation - create 1 major issue                                                | Annotation is created          | OK     |                        |
| Perform annotation - create 1 minor issue                                                | Annotation is created          | OK     |                        |
| Check QT21 Score                                                                         | QT21 shall be updated          | NOK    | Score is not updated.|


<br />
 
 

| 2.5 check if QT21 is correctly calculated with 3 different issues types with severall issues in each break session time out | Expected                                               | Actual |Comments               |
|-----------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------|--------|-----------------------|
| Go to Batch Selection page                                                                                                  | Batch Selection Page is opened                               | OK     |                       |
| Pick a translation task                                                                                                     | Translation task is opened                             | OK     |                       |
| Perform annotation - create 1 minor issue                                                                                   | Annotation is created                                  | OK     |                       |
| Perform annotation - create 1 minor issue                                                                                   | Annotation is created                                  | OK     |                       |
| Take a break                                                                                                                | Application redirected to Batch selection page         | OK     |                       |
| Go to the same task translation                                                                                             | Translation task is opened with the annotation created | OK     |                       |
| Perform annotation - create 1 major issue                                                                                   | Annotation is created                                  | OK     |                       |
| Perform annotation - create 1 critical issue                                                                                | Annotation is created                                  | OK     |                       |
| Let the login session expire and  create annotation                                                                         | User is redirected to the welcome page                 | OK     |                       |
| Login                                                                                                                       |                                                        | OK     |                       |
| Chose Batch                                                                                                                 |                                                        |        |                       |
| Go to the same task translation                                                                                             | Translation task is opened with the annotation created | OK     |                       |
| Take a break                                                                                                                | Application redirected to Batch selection page         | OK     |                       |
| Go to the same task translation                                                                                             | Translation task is opened with the annotation created | OK     |                       |
| Perform annotation - create 1 minor issue                                                                                   | Annotation is created                                  | OK     |                       |
| Check QT21 Score                                                                                                            | QT21 shall be updated                                  | NOK    | Score is not updated. |


 <br />

| 2.6 Add annotation without assigning severity                 | Expected                               | Actual |Comments   |
|---------------------------------------------------------------|----------------------------------------|--------|-----------|
| Go to Batch Selection page                                    | Batch Selection Page is opened         | OK     |           |
| Create annotation withou assigning type of error and severity | You have to select the severity first. | OK     |           |
| Assign severity   | You have to select the severity first.                                             | OK     |           |

 <br />
 
| 2.7 Add annotation without assigning severity | Expected                               | Actual |Comments   |
|-----------------------------------------------|----------------------------------------|--------|-----------|
| Go to Batch Selection page                    | Batch Selection Page is opened         | OK     |           |
| Create annotation withou assigning severity   | You have to select the severity first. | OK     |           |



#2.3 Status Report
![Status](https://drive.google.com/uc?export=download&id=0B0LtWpv5HjEDZWRiZzFPWDBtcE0)
