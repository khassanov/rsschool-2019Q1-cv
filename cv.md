# Junior Web Developer

# Personal information:   
# Nurlan Khassanov

![CV photo](/photo.jpeg/150x100 "My photo")  

# Contacts

## adress:  ### 29/1 Kunaeva, 010000 Astana (Kazakhstan)
## phone:  ### +7 777 039 56 95 
## e-mail: ### hasanov85@gmail.com
## Linkedin: ### https://www.linkedin.com/in/nurlan-khassanov-aba9b1123/
## Github    ### https://github.com/khassanov


# Summary 

My objective is to learn create and maintain optimally functional websites and applications as tools in achieving the companyâ€™s mission and vision. This being said, I look forward to becoming a useful part of the company.

# Education

### KARAGANDA STATE TECHNICAL UNIVERSITY, Karaganda (Kazakhstan)

### 5В070400 «Computing engineering and software» 

# English

| Listening | Reading | Speaking  | Writing |
|-----------|---------|-----------|---------|
|    A2     |    A2   |     A2    |    A2   |

# Skills 
* HTML5 & CSS3
* Bootstrap
* BEM methodology
* JavaScript ES5/6
* MongoDB/Mongoose
* NodeJS 
* Express 
* AngularJS
* Python 3.7
* Django 2.1
* Linux (Ubuntu Server/CentOS 7)
* Virtualization (Proxmox, VMware, Hyper-v)
* Github
* MySQL 

# Projects 

* Test task from Devir LLP : https://github.com/khassanov/DEVIRCRUD

* Test task from SoftCloud LLP: https://github.com/khassanov/SoftCloud

* App for accounting office hardware: https://github.com/khassanov/inventory

* App to parse exchange rates and show  result in linux mint system notifications: https://github.com/khassanov/linux_python_parser

```javascript   
var express = require('express'); // connect express
var logger = require('morgan'); // connect logging module morgan
var mongoose = require('mongoose'); //connect moongose
var path = require('path');
var bodyParser = require('body-parser');
var session = require('express-session');
var MongoStore = require('connect-mongo')(session);
var coockieParser = require('cookie-parser');
var app = express();
mongoose.connect('mongodb://127.0.0.1:27017/invdb', {
    useNewUrlParser: true,
    useCreateIndex: true,
});

app.use(logger('dev'));
app.use(bodyParser.json({
    limit: '100mb'
}));
app.use(bodyParser.urlencoded({
    limit: '100mb',
    extended: true
}));
app.use(coockieParser());
app.use(express.static(path.join(__dirname, 'public'), {
    maxAge: 1
})); //path to static file
app.use(session({
    secret: 'D9?yI|qN7lwT',
    resave: true,
    saveUninitialized: true,
    key: 'crudsessionid',
    store: new MongoStore({
        mongooseConnection: mongoose.connection
    })
}));
app.use(require('./server/routes'));
app.listen(process.env.PORT || 8080, function () {
    console.log('Server is a listening on port ', process.env.PORT || 8080);
});
```


