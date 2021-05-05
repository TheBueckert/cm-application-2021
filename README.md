# cm-application-2021
This repository is to contain all components of the code challenge in my application to the Critical Mass Intern program. This application is in May 2021. Let's jump in.

#Work/Project Examples

###CPSC 471 Project
One of the most recent projects I will mention is a group project at University of Calgary… or at least it was intended to be.
It was a team project for the class CPSC 471 *Database Management Systems*. The goal was to build a full-fledged CRUD web application with an SQL database,
 an API and a responsive web application. I was in charge of building the web app for my team.


Unfortunately, my teammates did not share my aspirations to get a good grade… or complete anything… at all.
 The warning signs surfaced early on, and I relayed them to the Professor throughout the semester.
 Unfortunately, it wasn’t until the eleventh hour, staring down the F on our transcripts when the situation hit its dramatic culmination.
 The Professor and head TA having borne witness to the situation granted my doomsday request of splitting from the group and completing everything on my own.
 With 3 days left before final submission I set out to complete the API, database, and make everything functional entirely on my own.
 It was ***grueling***. I can’t overstate that, but I learned an incredible amount. 

I weighed options for the database and settled on PostgreSQL.
 Postrges has an excellent management hub, modern features like explicit rules and foreign keys, and is very cooperative with other platforms.
 I referenced the relational model I had designed earlier and completed the database using Pgadmin4 and command line SQL queries.


I have a good grasp on JS so I decided on Node.js and Express.js for the API.
 There is an expansive NPM package called *node-postgres* for instantiating a client and interfacing with Postgres databases.
 Node-postgres was a life saver because of its error handling, rollback on failed queries and mix of JS and SQL syntax for writing queries within the API.
 I hosted several POST and GET request handlers on appropriate endpoints for serving data.
 I sent a result code back to any clients on a successful/failed query, with the database being rolled back to it’s previous state before any failed query.
    
    app.post('/customerupdate', cors(), async (req, res) => {
    try {
        await client.query("BEGIN");
        await client.query(`update customer set address= ($1) where email=($2)`, [`${req.body.data.address}`, `${req.body.data.email}`])
        await client.query("COMMIT").then(res.send("1"));
    } catch (e) {
        console.log(e)
        await client.query("ROLLBACK").then(res.send("0"))
    }
    });


I built the web application earlier in the semester so all that was left was making it functional.
 The layout was simple using a navbar, hamburger menus, flexboxes organizing relevant data etc.
 For functionality, I used async/await on Fetch calls to the API, and filled the headers with any required information.
 On failure, a brief error message is displayed to users, and on success the updated data is stored and displayed.
	
	
	businessLoginButton.addEventListener('click', ()=>{
    const id = document.querySelector('#business-id-login').value
    getSpecificItem('business',id).then(data => {
        if (data.length === 0) {
            display(businessLoginFail);
            setTimeout(() => dontDisplay(businessLoginFail), 5000);
        } else {
            localStorage.setItem("business", JSON.stringify(data));
            window.location = '../BusinessApp/BusinessView.html';
        }
    })
	})


Not everything in the original design could be implemented in time. Was it the best thing ever? No way. It was a one-man operation after all.
 The process was draining and frustrating, but I did it. I successfully built a full stack CRUD application in 3 days.
 The TA and Professor liked the result and gave me a final grade of 29.2/30.
 The real gain from this project was the new knowledge.
 I can analyze applications on a much deeper level, and it excites me thinking about what I could build with these new skills!

Image

###Go-to-logic
####[Link to Go To Logic](https://gotologic.ca/)

I was recently contacted by a small Quebec based development company.
 They were seeking a freelance Web Developer to jump into their React projects and fix bugs.
 They really liked me and pulled me on to their team!
 Their apps are massive… custom webpack configurations, Node package after package, custom runtime environments…
 It can all be a bit daunting, but it is super cool! Since then I have successfully fixed a few minor bugs like UI glitches or sorting data, and my PRs have been pulled into master!
 The updated apps will soon go into production, and I think it is awesome that a huge application used by multimillion dollar companies will have a few lines in there written by me!
 Even though it’s very minor stuff I’m still very proud.  
<br>
<br>

#Inspiration

###Kotlin Project
####[Link to build on github](https://github.com/TheBueckert/CodingProject)

This point is a mixture of a project example and inspiration.
 It’s not directly related to web development, so here it lies under the inspiration header, but I see it as important in my growth.
 I was introduced to a friend of a friend who likes to teach and develop mobile applications in his free time.
 Like the excellent guy he is he wanted me to hear the good word of Kotlin.
 Under his guidance, I built a test app, to pull and display movie data from the iTunes API and store it using Realm DB.
 The catch is that the app was written entirely in Kotlin! 

Well let me tell you friend, Kotlin is *amazing*!
 The syntax is remarkably legible and the static typing reminds me of when I made cloud functions in TypeScript for Ivy!
 The real beauty of this project is what Kotlin inspired in me. New and upcoming technologies are so efficient and powerful.
 I have always been wowed by new technologies, but Kotlin sparked my curiosity for exploring this world as a software developer.
 Now, I look on with awe at libraries like GraphQL or Next.js and the world of possibilities they open!
 Capitalizing on new technologies to make something massive is something that inspires me deeply.
 Maybe I could make something cool like Slippi...

###Slippi
####[Link to Project Slippi](https://slippi.gg/)

I am a massive, diehard fan of *Super Smash Brothers Melee* for the Nintendo GameCube.
 I could rant about it all day, but I am not alone.
 I belong to a community of passionate and dedicated fans to this game like no other.
 Melee raises a special kind of talent, and I must talk about a person known as *Fizzi36*.
 In June 2020, Fizzi released an update to his ongoing project called Slippi.
 This update included something called Rollback Netplay.
 Essentially, rollback estimates character positions based off your last known input for lagless smashing online.
 Rollback is the supreme netcode technique in fighting games.
 Now rollback netcode has been beautifully implemented in a game that came out in 2001, much to the envy of the rest of the Fighting Game Community.
 Original melee doesn’t even have online play!

Fizzi frequently hosts coding sessions on Twitch.tv.
 I like to pop in there to watch and ask him some questions.
 Interestingly he states that Project Slippi is "about 45% Javascript, 25% Assembly, 20% C, and a smorgasbord of other languages".
 Fizzi and Slippi to me are shining examples of accomplishing something astounding through perseverance and a well-rounded knowledge base.
 If I develop my skills too, and dedicate myself, I know I can achieve amazing things too.
 I wish to gain the skills to build something revolutionary like Fizzi has.
 Also, if you have a GameCube Controller and USB adapter, I encourage you to check it out! Feel free to ask me if you want any tips!

###CSS Animations
####[Link to a cool example](https://www.reddit.com/r/webdev/comments/mboqa2/the_tilt_to_make_room_for_a_menu_is_a_nice_effect/)

In my free time I also peruse web development blogs and Reddits.
 I recently noticed a cool CSS animation, that captures another aspect of development that I like.
 CSS is actually a pretty good tool for developing simple animations and effects.
 Posts like the one above exemplify how flexible our current technologies can be with a little creativity.
 I also think sitting down and working out a cool animation sounds like a fun activity, even when the result is not the most efficient or stable thing ever.
 Regardless, I like when creativity and knowledge combine to create something unique, and I appreciate when it is demonstrated in a way that shows us not to discount our current technologies.

<br>
<br>

#Focus

A major goal for me would be ***learning as much as possible*** in this internship.
 I seek the internship because I am the type of person who learns by doing.
 Some specific things I would like to focus on are React, and other Web Development libraries.
 I would like to get my hands dirty building with them and see how libraries interact with each other in big applications.
 But overall, as cliché as it sounds, I think learning is a good basket for many of my eggs to go into.
 
Another aspect I would like to focus on is learning ***process***.
 I will toss best practices, and efficiency in here as well.
 When I think about building a large application I run into roadblocks like where to go next, or how to build things on top of each other with scalability in mind.
 I know a few process’ at differing development phases like mobile-first, TDD, Agile etc.
 But I want first hand experience seeing a large problem broken down, and a plan of action being created by an experienced team.
 I think helping fit pieces together, following and developing a plan with a team at CM would be excellent for learning process.
 
The last thing I would take advantage of during the internship is the ***environment to apply myself fully***.
 I like to dedicate myself to work and apply my all.
 As a less experienced developer, its easy to second guess myself or face hesitancies in development.
 But with a team, I like to do the best I can to help *us* do the best we can.
 The internship would be a position for me to really go the extra mile, read the docs, be sure of my work and level up for a bigger cause.
 When my mistakes are no longer just my own and others will suffer, it gives me a steady reason to build upon and grow as much as possible.
 

