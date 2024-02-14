![ga_cog_large_red_rgb](https://cloud.githubusercontent.com/assets/40461/8183776/469f976e-1432-11e5-8199-6ac91363302b.png)

# Project 2 - GalactiScope - ReadMe Worksheet

## Description

GalactiScope is a web app designed for the purposes of consuming the NASA Apod app in a reactive and visually pleasing way for clients to be able to view the best of NASA pictures and get context behind those pictures.

The Sign of requirements were a wireframe and show of the API intended for consumption with a written plan of how it would be consumed i.e what endpoints we would be using and how the data would be called to the front-end. Planning was completed relatively quickly before the project started. 

Below is a list of the deliverables for the project taken from the brief:



* *Consume a public API** – this could be anything but it must make sense for your project.
* * **Have several components**
* * **The app can have a router** - with several "pages", this is up to you and if it makes sense for your project.
* * **Include wireframes** - that you designed before building the app.
* * **Be deployed online** and accessible to the public (hosted on your public github, not GA github!)

 
### Deployment Link & Repository

Project was deployed using netlify, link here: [https://galacticscope.netlify.app/](https://galacticscope.netlify.app/)

### Getting Started/Code Installation

To run the app locally:



* Clone the repo from GitHub
* Install dependencies with `npm install`
* Start the dev server with `npm start`

Or click on the deployment link above.

### Timeframe And Working Team(Pair)

For this project I was paired up with [Adrienne Szabo](https://github.com/aszab1). The timeframe set out for this project was 2 days including planning, the first half of the first day was dedicated to planning and the project started shortly after sign off.

### Technologies used



* React.js
* React Bootstrap
* SASS
* NPM

## Planning:

We began planning by researching publicly available API’s and looking for something that would suit both our interests enough to be able to make a compelling project. This is how we found the [APOD](https://apod.nasa.gov/apod/astropix.html) (astronomy picture of the day) API. The website is maintained by NASA and features a different astronomy picture each day along with relevant details of that picture (description of the picture, who it was taken by, etc). The API supports HTTP requests and returns information based on specific endpoints called, which suited our needs. Endpoints below: 



<img width="599" alt="Screenshot 2024-02-13 at 12 01 49" src="https://github.com/NyashaDZT/apod-api-project-2/assets/124045473/637ef6a6-0097-4414-a76c-2207991366d2">


We wanted to create a web page where users would be able to see Astronomical picture of that given day on the homepage. We also wanted to create a separate page where users could browse through randomly generated pictures within the APOD API, which if they clicked on would then take them to a page on the site very similar to our landing page where they would be able to get the information of that specific picture, using the same design as the homepage.

## Build/Code Process

The project was paircoded, we utilised VSCodes extension “Collaborate with Liveshare” to paircode, almost all parts of the code were completed in tandem, a process where we would identify the component we would want to work on, create a boilerplate for that component and then discuss a method to achieve the functionality we were looking for. 

The first component we worked on was the Navbar, we thought this would be a pretty good starting point, as it would give us a way of navigating through the site whilst developing without having to type in the endpoints into the address bar each time. This also meant we could create our endpoints at the very start of the project and map the React Router app. Below is a screenshot of the Navbar component, as you can see this was mostly created using React Bootstrap: 


<img width="601" alt="Screenshot 2024-02-13 at 12 50 57" src="https://github.com/NyashaDZT/apod-api-project-2/assets/124045473/f6e7fb09-7542-4a04-b93a-f41bf48a4d57">

The feature we created was our landing page, another very simple component in terms of functionality and because we needed our single picture view which would be created later on in the project to have the same presentation of the photos, we ended up being able to reuse the code which was included in the single component page. 

The homepage data was accessed through Loader data by sending a request to the endpoint “apod?&lt;API-KEY>” which returns information for the current date. 

Below is a picture of the getPicofDay function which is used to call our loader data. By using the useLoaderData hook, we were able to make sure that the webpage would load only once the data required was available, once we had the response required we could then destructure the object received to display the picture’s url, the date it was taken on and other information we need to create a cohesive display page.


<img width="602" alt="Screenshot 2024-02-13 at 12 54 14" src="https://github.com/NyashaDZT/apod-api-project-2/assets/124045473/ab2dca42-7be5-4150-9305-a44476bb4dff">


Our fetch function for pictures of the day. 
 
 
<img width="596" alt="Screenshot 2024-02-13 at 12 55 18" src="https://github.com/NyashaDZT/apod-api-project-2/assets/124045473/8d343149-0ba7-4d65-9662-baa277acce92">


How the home component looked on display. 


A library page was also implemented into the project. The way we achieved this was by making an API call using the “count” parameter, we created a function in our loaders which would make a call to the API and make a call for 20 pictures. These twenty pictures were selected in random order, as the endpoint “count” only returns a random assortment. These 20 pictures would then display on the web page in 5 rows of 4 and using some basic CSS, we had the pictures expand if the user was hovering over them to enlarge the picture for the user, each picture was a link which would take the user to a single picture view component which behaved in the very same manner as our landing page function. A screenshot of our library/index page is below: 
 

<img width="604" alt="Screenshot 2024-02-13 at 12 57 49" src="https://github.com/NyashaDZT/apod-api-project-2/assets/124045473/d50cbe12-79be-4056-b35e-ef183a9ff2b2">




## Challenges/Bugs

The biggest challenge faced during development was the “previous” and “next” buttons on the web page, the next page worked for making a new API call and using state  we were able to change the pictures being displayed on the picture display by calling in 20 new images. However the previous button still does not work even at this point, we tried a few solutions to make it work but due to the limited time-scale we decided we would not have had the appropriate time to fix it. We diagnosed the problem as our web page being unable to fetch complete a re-fetch for the specific images that we would have had on the previous page, because we were not storing the data of these specific images anywhere within our state. At this point all pressing the previous button does is what the next button does, which is fetching random images from the API.

## Wins

Overall, it was great working collaboratively to build this app within a short timeframe. Despite the time constraints, our effective collaboration stemmed from clear communication and a well-defined division of tasks. Embracing an agile development approach, we regularly conducted brief stand-up meetings to discuss progress, share ideas, and address any roadblocks. Our synergy was further enhanced by utilising version control systems, such as Git, which facilitated seamless code integration and allowed us to work on different features simultaneously. Additionally, leveraging pair programming techniques, we were able to troubleshoot issues in real-time and learn from each other's insights. While there are still some bugs to fix, the successful deployment of the Minimum Viable Product (MVP) stands as a testament to our teamwork, adaptability, and shared commitment to the project's success.

## Future Improvements



* Fix the previous button.
* Implement more responsive design.
* Error handling.
* Fix the way the project handles video data, this can be achieved by calling and making sure that the data received corresponds to a picture or by manually adding a video player so that videos can play.
