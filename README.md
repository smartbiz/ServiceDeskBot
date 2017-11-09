# README #
## Source structure

```
├── app
│   ├── handlers
│   │   └── fileanissue.js
│   └── models
│       ├── columne.model.js
│       ├── label.model.js
│       ├── milestone.model.js
│       └── project.model.js
├── assets
│   ├── json
│   │   └── github_organization.json
│   └── it-helpdesk-structure.xlsx
├── config
│   ├── .env
│   ├── constants.js
│   ├── index.js
│   └── mongodb.js
├── package.json
├── README.md
```
## Setup

- Start MongoDB
```
$ sudo service mongod start
```
- Run node server to create github structure from json
```
$ node createGitHubStructure.js
```
- After structure already has created, stop node server

- Run node server
```
$ node index.js
```
## Service Desk Bot Flow

### 1. Create issue on Workplace

- Pattern to create a issue on workplace

```
@Bot_name Title_of_Issue#Assignee#Priority#Type_of_Issue
```
- Priority such as: High, Low, Medium
- Type of issue such as: Access/Login, Desktop/Laptop/Hardware, Internet/Intranet ...

Example: @ServiceDeskBot Can't Login Desktop#smartbiz#High#Access/Login

![](/assets/images/create-issue-workplace.png)

- Workplace will post a message if create a issue is success

![](/assets/images/create-issue-success.png)


### 2. Handle issue on github
- Click on issue's link on workplace to see detail on github as below

![](/assets/images/issue-github.png)

- Issues are organized as dashboard below

![](/assets/images/dashboard-github.png)

- After close a issue, this issue will auto move to Close column on dashboard

![](/assets/images/close-issue.png)
![](/assets/images/dashboard-move.png)

### 3. Workplace notify the issue is close
- Workplace will notify as below

![](/assets/images/workplace-notify.png)