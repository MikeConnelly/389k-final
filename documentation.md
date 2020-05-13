
# PROJECT NAME

---

Name: Michael Connelly

Date: 5/12/20

Project Topic: Coding Challenges

URL: https://coding-challenges-389k.herokuapp.com/

---

### Final Project Documentation:

### 1. Sockets

When a user creates a new post, other users on the home page will see it appear at the top of their post list without refreshing (labeled: New Post)

### 2. Post endpoints

POST endpoint route 1: `/api/create`

```javascript
var options = { 
    method: 'POST',
    url: 'https://coding-challenges-389k.herokuapp.com/api/create',
    headers: { 
        'content-type': 'application/x-www-form-urlencoded' 
    },
    form: { 
      title: 'fibonacci',
      description: 'output the fibonacci sequence',
      tags: ['beginner', 'recursion'],
      difficulty: 3
    } 
};
```

POST endpoint route 2: `/api/comment/:postID`

```javascript
var options = { 
    method: 'POST',
    url: 'https://coding-challenges-389k.herokuapp.com/api/comment/0',
    headers: { 
        'content-type': 'application/x-www-form-urlencoded' 
    },
    body: { 
      text: 'example comment'
    }
};
```

### 3. Delete endpoints

DELETE endpoint route 1. `/api/post/:id`

DELETE endpoint route 2. `/api/comment/:postID/:commentNum`

### 4. Module created

/utils/getTags.js is used to get all unique tags from an array of posts.
It is used frequently on the backend to update what tags appear in the navbar.

### 5. Packages used

Moment.js is used to get and format the current time.
Marked.js is used to render markdown text as html.

### 6. View data

Navigation
1. random -> `  /random  `
2. easiest -> `  /easiest  `
3. hardest -> `  /hardest  `
4. shortest description -> `  /shortest  `
5. longest description -> `  /longest  `
5. sort by tag -> `  /tag/:tag  `
6. create -> `   /create   `
7. about page -> `  /about   `
8. view post -> `   /post/:id   ` and `  /post/title/:title   `


### Updated Midterm Project Documentation:

### 1. Data Format and Storage

Challenge data point fields:
- `Field 1`:     title         `Type: String`
- `Field 2`:     description   `Type: String`
- `Field 3`:     preview       `Type: String`
- `Field 4`:     date          `Type: String`
- `Field 5`:     tags          `Type: [String]`
- `Field 6`:     difficulty    `Type: Number`
- `Field 7`:     id            `Type: Number`

Challenge schema: 
```javascript
{
   title: String,
   description: String,
   preview: String,
   date: String,
   tags: [String],
   difficulty: Number,
   id: Number
}
```

Comment data point fields:
- `Field 1`:     text                 `Type: String`
- `Field 2`:     time                 `Type: String`
- `Field 3`:     postID               `Type: Number`
- `Field 4`:     commentNumber        `Type: Number`


Comment schema: 
```javascript
{
   title: String,
   text: String,
   postID: Number,
   commentNumber: Number
}
```

### 2. Add New Data

HTML form route: `/create`

POST endpoint route: `/api/create`

Example Node.js POST request to endpoint: 
```javascript
var request = require("request");

var options = { 
    method: 'POST',
    url: 'http://localhost:3000/api/create',
    headers: { 
        'content-type': 'application/x-www-form-urlencoded' 
    },
    form: { 
      title: 'fibonacci',
      description: 'output the fibonacci sequence',
      tags: ['beginner', 'recursion'],
      difficulty: 3
    } 
};

request(options, function (error, response, body) {
  if (error) throw new Error(error);

  console.log(body);
});
```

### 3. View Data

GET endpoint route: `/api/data`

### 4. Search Data

Search Field: `title`

### 5. Navigation Pages

Navigation Filters
1. random -> `  /random  `
2. easiest -> `  /easiest  `
3. hardest -> `  /hardest  `
4. shortest description -> `  /shortest  `
5. longest description -> `  /longest  `
5. sort by tag -> `  /tag/:tag  `

