const mongoose = require('mongoose')


const alienSchema = new mongoose.Schema({

    name: {
        type: String,
        required: true
    },
    tech: {
        type: String,
        required: true
    },
    sub: {
        type: Boolean,
        required: true,
        default: false
    }

})

module.exports = mongoose.model('Alien',alienSchema)






const express = require('express')
const mongoose = require('mongoose')
const url = 'mongodb://localhost/AlienDBex'

const app = express()

mongoose.connect(url, {useNewUrlParser:true})
const con = mongoose.connection

con.on('open', () => {
    console.log('connected...')
})

app.use(express.json())

const alienRouter = require('./routes/aliens')
app.use('/aliens',alienRouter)

app.listen(9000, () => {
    console.log('Server started')
})




const express = require('express')
const mongoose = require('mongoose')
const url = 'mongodb://localhost/AlienDBex'

const app = express()

mongoose.connect(url, {useNewUrlParser:true})
const con = mongoose.connection

con.on('open', () => {
    console.log('connected...')
})

app.use(express.json())

const alienRouter = require('./routes/aliens')
app.use('/aliens',alienRouter)

app.listen(9000, () => {
    console.log('Server started')
})






{
  "name": "crudjs",
  "version": "1.0.0",
  "description": "",
  "main": "app.js",
  "scripts": {
    "start": "nodemon app.js"
  },
  "author": "navin@telusko",
  "license": "ISC",
  "dependencies": {
    "express": "^4.17.1",
    "mongodb": "^3.5.7",
    "mongoose": "^5.9.13"
  },
  "devDependencies": {
    "nodemon": "^2.0.3"
  }
}
