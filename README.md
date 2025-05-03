# SWE363-TEAM19
Project title and description.  
Title: **SAMRA**  

interactive storytelling platform dedicated to preserving and sharing SaudiArabia’s rich
cultural heritage through user-generated stories. The platform will serve as a digital archivewhere content creators can
write and manage their stories, upload images, and participate in storytelling events that highlight Saudifolklore,
history, and traditions. Regular users can browse, search, and filter stories based on themes, genres, and geographic
regions, making it easy to explore narratives from different parts ofthe Kingdom.Astory moderation system will ensure
high-quality content by allowing administrators to reviewand approve submissions before they are published.Users
will also be able to share stories via unique links, enabling them to distribute content across various platforms.Areward
system will incentivize engagement, encouraging both creators and readers to contribute actively.Additionally, an
interactive map featurewill allowusers to discover stories tied to specific Saudiregions,reinforcing the country’s diverse
cultural history. By combining storytelling, community participation, and interactive features,this platform aims to
preserve SaudiArabia’s oral andwritten traditions, ensuring they remain accessible and appreciated for generations to
come.  


Setup and installation instructions.  
`important Notes:`  bulit it for both moblie and desktop, start file is just for us to commit and upload our work, this is a SAMPLE data it inclues two proflies only but it shows how they work 
1. Download zip flie  
2. upload it to visual studio code  
3. start running at the **homepage**  
4. naviage to pages and login information   
   `login credentials`
   both are case sensitive
      **creator:**  
      email: creator@samra.com  
      passward: pass123  
      code: 1234  
      
      **Admin:**  
      email: admin@samra.com  
      passward: pass123  
      code: 1234

5. you can go the website via link https://samra-7dc09ed5b123.herokuapp.com/homepage.html
6. or add http://127.0.0.1:5000/ to any fetch method
7. run serve.js in the termial 

Usage instructions and examples.  
`login credentials`  
**creator:** 

fatimabazroun@gmail.com
Fatima@123

code:1234

**Admin:**  
sara@samra.com
SaraAdmin@123
code: 1234  

code always 1234
example: guest user can just go through the stories and view the pages   
creator or users who have an account, they can log in and also join events, comment, like and follow creators unlike guest   
admin: can edit, delete comments, edit map and also do what the users can do   


==============================
✅ Back-End Setup Instructions
==============================

1. Install dependencies
-----------------------
npm install

2. (Optional) Create a .env file for configs
--------------------------------------------
PORT=5000
MONGO_URI=your_mongodb_connection_string

3. Update mongoose connection in server.js
------------------------------------------
mongoose.connect(process.env.MONGO_URI, {
  useNewUrlParser: true,
  useUnifiedTopology: true
})

4. Start the server
-------------------
node server.js

Default server runs on:
http://localhost:5000
but for deployent it was removed 


==========================
📚 API Documentation 
==========================

▶ POST /signup
--------------
Creates a new creator user.

Request:
{
  "fullName": "Fatima",
  "email": "fatima@example.com",
  "password": "Fatima@123"
}

Response:
{
  "message": "✅ Account created successfully!"
}


▶ POST /login
-------------
Login as creator or admin.

Request:
{
  "email": "fatima@example.com",
  "password": "Fatima@123"
}

Response:
{
  "message": "✅ Login successful! Enter verification code.",
  "fullName": "Fatima",
  "role": "creator",
  "verificationCode": "1234"
}
▶ POST /stories
---------------
Create a new story.

Request:
{
  "title": "My Story",
  "content": "Once upon a time...",
  "author": { "name": "Fatima" },
  "genre": "Fiction",
  "region": "Riyadh"
}

Response:
{
  "_id": "...",
  "title": "My Story",
  ...
}
▶ GET /stories
--------------
Fetch all stories.

Response:
[
  { "_id": "...", "title": "Story 1", ... },
  { "_id": "...", "title": "Story 2", ... }
]

▶ POST /api/comments
--------------------
Add a comment to a story.

Request:
{
  "storyId": "STORY_OBJECT_ID",
  "userName": "Fatima",
  "content": "Loved this!"
}
▶ POST /api/likes/toggle
------------------------
Like or unlike a story.

Request:
{
  "storyId": "STORY_OBJECT_ID",
  "userId": "USER_OBJECT_ID"
}

Response:
{
  "newCount": 5
}
▶ POST /api/follow/toggle
--------------------------
Follow/unfollow a creator.

Request:
{
  "followerId": "USER_ID",
  "authorId": "CREATOR_ID"
}

Response:
{
  "isFollowing": true,
  "followerCount": 12
}
▶ GET /api/creators/:id
------------------------
Fetch a creator's profile + stories + recent activity.

▶ PUT /api/creators/:id
------------------------
Update a creator's profile (bio, interests, etc.)

▶ GET /api/creators/:id/follow-status
-------------------------------------
Check if a user is following a creator.



Team member names and roles.    

`Fatima Bazroun:` homepage: the header ,footer , the cards at the bottom multiple page navigation  , join functions and accessibility for guest users and creators different view of it which was implement across the whole website while also linking to the pages .  login page for both admin and creator the functions of them checking credential and while adding verification code. map pages: integrating the api making it customizable for the app and linking it to the libraries. dhahran-library, popular-stories, riyadh-library adding filter, search and reset button in each page, join button and multiple pages navigation. Creative the profile for the creator and linked it accordingly.  Helped with debugging stories, like, comment to limit access. Fixing the issue with disconnecting join and clicking the story, helped with debugging testing as well, creating readme file, the repository and figma designs. removed whats hardcoded for the login, create an account, forget passward and anything that login related from check if admin has accuess to login as creator and creator as admin not allows, dubugged and deployed the app 



`Sadeem Alotaibi:`
Implemented and updated story pages with like, comment, view, follow/unfollow, and share features. Handled user access control and localStorage functionality in main.js.

`Fatimah Alshabaan:`
Built a responsive story content page featuring a header with image and metadata, interactive view/like counters, comment section, and author follow button. Implemented clean styling with a card-based layout, proper typography hierarchy, and mobile-responsive design using flexbox and media queries. Added share functionality and connected interactive elements to main.js for localStorage integration.

`Renad Alqahtani:`
In this project, I created a creator dashboard (`creator-dashboard.html`) I specifically implemented and styled the Followers, Favorites, and Messages sections, making them interactive and user-friendly. Also three detailed follower profile pages (`HanaOmar.html`, `NouraAlqahtani.html`, and `MohammedAlhajri.html`) for a heritage-focused web platform called "Samra." The dashboard allows creators to manage messages, followers, and favorites, with interactive sections and styled tables. Each follower profile showcases unique personal information, including their role, region, specialty, biography, interests, and recent activity, all aligned with the platform’s mission to preserve Saudi oral traditions. The design is consistent across pages, using shared headers, footers, and layout styles to ensure a cohesive user experience.

Sarah Alsaleem:
Story writing page. Modify the map to suit the supervisor's functions. Edit comments to match moderator functions,helped with debugging testing,Corrected the problem with admin login.

`Reman Alqahtani:`I developed the Posts section in the creator dashboard, allowing creators to manage and view their published content in an organized and interactive layout. I also implemented the Admin section for event approval, where administrators can review, approve, or reject submitted events before they go live on the platform.
