# FREE THE BOOKS

<img width="1440" alt="screen shot 2017-03-06 at 13 06 43" src="https://cloud.githubusercontent.com/assets/22742327/23613820/ce3cf262-0278-11e7-9a3a-cdaf11ede059.png">

## Overview

FREE THE BOOKS is a website that enables a novel form of physical book sharing, presented as a mock activist movement to “free books from the tyranny of bookshelves”. Book freers write the website URL and a book ID and then leave the book in a public place (“in the wild”) for anyone to find. Book finders then can read the book (or not) and leave a message on the website before again leaving it in a public space. The website was created as a team project during my 12-week Web Development Immersive course at General Assembly in London. It was built using a MEAN stack.

See it here: [Free The Books](https://free-the-books.herokuapp.com/)

## How it works

Users of our website can:

- Join The Cause: register as a user by providing a name, email and password
- Free A Book: search for a book in the search feature below and register it, leaving a message. The user is provided with a unique code for the book, which they must then write on it along with a link to our movement, freethebooks.com, before releasing into the wild for someone else to find
- Find A Book: enter the unique code for the book and add your message to the book's story

## The build

Key aspects of the build were as follows:

- MEAN stack: MongoDB, Express.js, AngularJ, Node.js
- CSS framework: Skeleton
- Database: MongoDB
- Angular modules:
	- Simple HTTP requests: ngResource
	- Authentication: angular-jwt
	- Carousel functionality: slick
	- Typeahead functionality: ui.bootstrap
- External APIs:
	- Google Books
	- Google Maps

## Idea generation

As a team of 5, our first task was coming up with an idea. After some debate, we settled on food and books as our main common ground. We narrowed our ideas down to two main front-runners: a recipe / what's in my fridge app, or a book-sharing app. With help from our lead instructor, we decided to pursue the book app. Taking inspiration from [Books on the Underground](http://booksontheunderground.tumblr.com/), our book-sharing app evolved into a book-sharing movement, where users are encouraged to leave books for others to find, read and pass on again.

We decided to make the website a mock activist movement whose aim was to free books from the tyranny of bookshelves. We styled the app after Communist propaganda posters, and included a manifesto and guidelines drawing inspiration from the tenets of Fight Club.

## Planning / teamwork

Once we had decided on our idea, we created a Trello board. While our intentions were good, we did not keep this updated as much as we might have liked, instead often preferring in-person chats and white-board based plans.

We started by splitting into three teams to set up the foundation for our app. Klaudia and Sharon tackled wireframing; Chris researched the Google Books and Goodreads APIs, settling on Google Books; James and I set up the beginnings of the app, with basic RESTful routes and authentication.

After that, we tended to split by page / functionality. I worked on most parts of the app, but I was particularly involved in the 'Free a Book' functionality, the user profile page and the 'Freedom Feed' page.

Over half of our time was spent pair programming, and we did regular stand-ups throughout the week to keep each other updated on our progress - at least two per day. We pushed regularly to github, and were active on our team slack channel.

## Website & code overview

The three main areas of the website are as follows:

#### 1. Free a Book / Found a Book

On visiting the 'Free a Book' page, the user is presented with a simple search box. This search box is linked to the Google Books API, returning the top 10 matches for the user to choose between. We integrated typeahead functionality from ui-bootstrap, which returns the results as the user is typing. We limited this to two API requests per second in order to avoid going over Google Book's API limits.

Once the user has selected the correct book, they are redirected to the book's page, which presents them with the book's unique code and a form to leave their message and location. Upon submission, both are saved into our database (along with the latitude & longitude courtesy of Google Maps API), and the the form is replaced by a map showing the book's location and message.

Finding a book involves entering the unique code, and adding a message and location in a similar manner.

<img width="1440" alt="screen shot 2017-03-06 at 14 35 21" src="https://cloud.githubusercontent.com/assets/22742327/23614246/308f337a-027a-11e7-89ff-fa98295909f1.png">

#### 2. Freedom Feed

Our 'Freedom Feed' page includes a carousel feed of recent books freed using the angular-slick module. It also shows the full index of freed books, initially showing 10 books with a button to show 10 more.

<img width="1440" alt="screen shot 2017-03-06 at 14 31 44" src="https://cloud.githubusercontent.com/assets/22742327/23614081/aa228fd0-0279-11e7-88c5-1da98e376a31.png">

#### 3. User profile

The user's profile shows their basic information and books dropped - both in carousel and map format.

<img width="1440" alt="screen shot 2017-03-06 at 14 29 03" src="https://cloud.githubusercontent.com/assets/22742327/23613976/574cce7e-0279-11e7-95cd-768101642bb7.png">

## Key challenges/learnings

Our team project did not always go smoothly - there was plenty of healthy disagreement along the way. I'm thankful for this - I believe we navigated through our disagreements very well, and learned a huge amount about working in a team as a result.

My other main learning was around planning. I believe our work would have been more efficient if we had spent more time planning at the start of the project - in particular, drawing up the full user journey and associated features. 
