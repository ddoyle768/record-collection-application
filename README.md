# record-collection-application

This was a collaborative final-capstone project for Tech Elevator (https://www.techelevator.com/)
Partners Included:
- Conor Parnell (https://www.linkedin.com/in/conorparnell/)
- Dominic Petruccelli (https://www.linkedin.com/in/dpetruccelli/)
- Myrka Gonzalez (https://www.linkedin.com/in/myrkagonzalez123/)

This project utilizes Java, Spring, postgreSQL, Vue.js (HTML, CSS, JavaScript), as well as two external APIs (MusicBrainz API: https://musicbrainz.org/doc/MusicBrainz_API and Cover Art Archive API: https://musicbrainz.org/doc/Cover_Art_Archive/API)

This is a record collection website (Project Leader decided on the name "Vinyl Revival") where a user can track the vinyl they have within their libraries. Tech Elevator provided the starter code for a user logging in, logging out, and registering. These processes included checking if an username was already taken upon registration, generating unique user-tokens for access to the site, confirming passwords matched during registration, and hashing the password before storing it in a database. These methods were modified to include a "Premium User" check and generation in the database.

An important distinction to be made is that a user's "Library" is the entirety of all the records they have entered. A "collection" can be thought of as a specific grouping or "playlist" of records.

All information such as user information, record information, collection makeup, etc. has all been stored in our created database for the program. No compromising user information is ever stored within the database.

An anonymous user is able to browse the collection's page. Here my partners and I created "staff picks" collections. Each collection on the webpage is viewed within a "Carousel" animation (credit for the tutorial on creating the Carousel can be found at the bottom on the Carousel component in Vue), cycling through album art either forwards or backwards by using the "Next" and "Back" buttons, respectively. Each collections entry in the database is dynamically generated on the webpage as well as each individual record within the collections. As collections are updated, deleted, etc. and as records are added or removed from collections, they will automatically update accordingly.

The remaining pages of the website are restricted to registered users. Any anonymous user's attempted access to these other pages will redirect them to the login page. Users are able to use the Login and Register pages to create an account with the website. Once logged in, a logged in user can select the "logout" navigation button to logout and become an anonymous user.

Once logged in, a user may enter their profile page. Here they can use the two external API's to search both an album name and an artist together to search for their desired record to add to their library. Given the amount of albums being retrieved and the age of the API, the search could potentially take up to ~30 secs to complete. When searching the API's, only items tagged as "records", "vinyl", "12 inch", etc. will be searched for, given the nature of the website. Assuming they would want to match the record they physically own, multiple entries may be generated per search. A user can then choose which specific record out of the search results to add to their library by clicking the "add" button beneath the entries. The page will then reload, and the selected record will now appear it he user's library. When hovering over the record in teh library, a flipping animation occurs to view the back of the record. Should a record not contain any artwork from the APIs, a default image appears instead.
