# The gorgeous es6 destructuring and how it works

es6 is here and it's staying, have you ever seen something like this?

```js
var { name, lastName, age } = user
```

I am sure that if you are a react developer you have, and perhaps you've used it but, do you know how it works?

## Where it comes from?

Let's imagine we are building a developers catalog using our favorite programing language. Sooooo we  want to print, scratch that, we want to log a developer name, lastName, and age, and all of this info is in a JSON...

```js
var user = {
  name: 'Carlos', 
  lastName: 'Gonzalez',
  age: 23,
  skills: ['javascript', 'python', 'scrum', 'react', 'node', 'express']
}
```

let's log it...

```js
console.log(user.name, user.lastName, user.age)
```

That's it right? now let's asume we want to use this several times in different parts of the code...

```js
console.log(user.name, user.lastName, user.age)
// several lines later...

console.log(user.lastName, user.name, user.age)
```

That doesn't make a lot of sense right? writing over and over use.something, besides, dot operations have cpu cost (is not much but should matters)
Besides that is not very readable, so lets use just name, lastName, age variables...

```js
var name = user.name
var lastName = user.lastName
var age = user.age

//then ...

console.log(name, lastName, age)

```

Much better, yes?

When we work a lot with data, displaying it, making operations with it this kind of "manual assigments" of variables help a lot with the job.

## es6 comes into action...

What if we could just do this...
```js
var { name, lastName, age } = user
```

Not a single dot operation, and we did in one line what it toked three.

We can also do this with arrays, lets take skills array...

```js
var { skill1, skill2, skill3 } = user.skills
```

Whaaaat does that works? yes, so you can destructur objects and arrays, but where all this come from?

let's create some skills for a second developer...

```js
var skills = ['javascript', 'python', 'scrum']

// now let's destructur them...

var { skill1, skill2, skill3 } = skills

// Lets create de developer...

var secondDeveloper = { name: 'Dennis', lastName: 'Ritchie'}
// destructur it
var { name, lastName } secondDeveloper
```

Notice something? We just need to realize destructuring is "just" the inversion of variable asigment, that is why the assigment goes right to left stead of left to right...

So, we just understand why destructuring looks like that, now let's understand something else...

Let's asume we are getting and the developers data from different sources... So we have three different variables.

```js
var name = 'Carlos'
var lastName = 'Gonzalez'
var twitter = 'cyberpolin'
```

Obiusly we want to add create a JSON with it, let's do it.

```js
var developer = {
  name: name,
  lastName: lastName,
  twitter: twitter
}
```

let's try this...

```js
var developer = { name: name, lastName: lastName, twitter: twitter }
```

well if we name the variables the same way we call the object attributes, doesn't make sense to write them twice right?

```js
var developer = { name, lastName, twitter }
```
Nice right?

what about if we flip it?

```js
var { name, lastName, twitter } = developer
```
the last one is a destructuring  syntax.

So far looks great right, I hope this clears where the notation came from, now lets do some destructuring cool stuff.
So far looks great right, I hope this clears where the notation came from, now lets do some destructuring cool stuff.