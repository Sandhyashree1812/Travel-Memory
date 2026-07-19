# Travel-Memory

==================================================

Explanation:
===========

Travel Memory is a web application which we are building to see how the front and backend are connecting.

   The frontend :
   ============

  1. Frontend (React) , this is the part the user sees and runs on :http://localhost:3000
  2. sends requests to the backend, and the backend stores data in MongoDB.

   Backend (Node.js) :
   =================

  1. The backend receives requests from React, connects to MongoDB, saves data, returns data
  2. Runs on : http://localhost:3001

  MongoDB :
  ========

  MongoDB stores the travel memories.

  Each travel memory is one document like:

   {
     "tripName": "Incredible India",
     "totalCost": 800000
   }

======================================================================== 

Lets Start
========== 


Steps:
========= 

Cloning:
========
1. First we Clone the Project.
(Instead of creating every file manually, you download the existing project from GitHub, we cloned the project from github link: https://github.com/UnpredictablePrashant/TravelMemory.git)

  Steps to clone:
  1. copy the code link from github
  2. Go to VS code terminal to the folder where we want to clone and type the clone command :

     C:\Users\sandy\Git Travelmemory\TravelMemory>git clone https://github.com/UnpredictablePrashant/TravelMemory.git
   
2. After cloning the project, it should look something like this:
   
 <img width="260" height="343" alt="image" src="https://github.com/user-attachments/assets/a833d6a2-e500-4992-91d4-cf176d7ed864" />


TravelMemory/

│
├── backend/

│
├── frontend/

│
└── README.md

=============================== 
The backend folder looks like this :

<img width="230" height="184" alt="image" src="https://github.com/user-attachments/assets/df4cd4ef-2fcb-4427-aef8-7ccc2976893e" />

Note : 
=======

What each folder/file does :

| File/Folder    | Purpose                                                                      |
| -------------- | ---------------------------------------------------------------------------- |
| controllers    | Contains the logic for handling requests (e.g., saving or retrieving trips). |
| models         | Defines the structure of data stored in MongoDB using Mongoose schemas.      |
| routes         | Maps API URLs (such as `/api/trips`) to controller functions.                |
| index.js       | Starts the Express server and registers routes.                              |
| conn.js        | Connects the application to MongoDB.                                         |
| package.json   | Lists the backend dependencies and scripts.                                  |

===================================================

Creating database in Mongodb:
============================= 

Steps:
======

3. In MongoDB Atlas, create a Project

   <img width="751" height="215" alt="image" src="https://github.com/user-attachments/assets/41e50151-60b4-48e3-a5fb-f68c79065a14" />

4. Create cluster and database 
   
   <img width="901" height="333" alt="image" src="https://github.com/user-attachments/assets/12726390-44c3-465f-8146-7d5b896fd6ff" />

   
   <img width="251" height="112" alt="image" src="https://github.com/user-attachments/assets/21e64efd-77fd-47d4-b0e7-ecea42a36d84" />


   <img width="367" height="131" alt="image" src="https://github.com/user-attachments/assets/5591216a-e24c-4dab-8979-e37df8cd6f53" />


 5. Open your cluster, click connect, then click drivers:
    
     <img width="572" height="376" alt="image" src="https://github.com/user-attachments/assets/00d9ef69-f01e-4c5a-9e99-47b8aa0b1027" />

  <img width="571" height="392" alt="image" src="https://github.com/user-attachments/assets/dd262493-556e-4a58-b325-f0655fce98c5" />

6. copy the string and save it for further use. We would replace the user name and password and data base name to add to the .env file in backend later on in the below copied string:
   
  String copied : 
  mongodb+srv://Sandhyashree:<db_password>@travelmemorycluster.sntukb6.mongodb.net/?appName=Travelmemorycluster

7. Also Allow your IP address in Network Access:

   Steps:
   ======
   
   1. Click the Database and Network Access from the left side bar:

   <img width="181" height="431" alt="image" src="https://github.com/user-attachments/assets/4654ba9d-cb89-4443-8c28-fc7da34cf008" />

   2. Under the Network access, click IP Address List and chnage the IP Address :

  <img width="193" height="171" alt="image" src="https://github.com/user-attachments/assets/715234b2-af5e-400d-b721-73995d6136af" /> 

   3.  Add Access List Entry as : 0.0.0.0/0 
       Comment : you can give any name

  <img width="428" height="343" alt="image" src="https://github.com/user-attachments/assets/03fe71aa-1fa0-42a9-96d6-553809015742" />

=================== 

Creating .env files:
====================

Note : 
=======
We don't store passwords or connection strings in the code because:
1.they contain sensitive information,
2.they can differ between development and production.
3.Instead, we use a .env file that is typically not committed to GitHub (it's usually listed in .gitignore).

==============================


8. create .env fies in both the backend and frontend.

 Steps:
 =====
 1. In .env file of backend add the below code:
  MONGO_URI=mongodb+srv://Sandhyashree:<db_password>@travelmemorycluster.sntukb6.mongodb.net/?appName=TravelmemoryclusterappName=Travelmemorycluster
 PORT=3001

===================

  Note:
  =====

 2. Replace in the above string with the below details:

   <username> with your MongoDB Atlas username.
   <password> with your MongoDB Atlas password.
   <cluster> and <appName> with the values from your Atlas connection string.
   
====================================

<img width="811" height="108" alt="image" src="https://github.com/user-attachments/assets/15d40ec0-e665-42c0-80fd-c59909112a4c" />


========================================  

 3. In frontend .env file add the below code:
    REACT_APP_BACKEND_URL=http://localhost:3001

<img width="576" height="59" alt="image" src="https://github.com/user-attachments/assets/65182e9e-e541-4c03-a9a5-95461cd79b9e" />


   Save both the files: press Cntl+S
 
 ================================================

 
 9. In VS code :
    Go into the backend folder, type the below commands:
    
     1.   PS C:\Users\sandy\Git Travelmemory\TravelMemory> cd backend
     2.  PS C:\Users\sandy\Git Travelmemory\TravelMemory\backend> npm install
        if npm install gives error, type the below command         
     3.  PS C:\Users\sandy\Git Travelmemory\TravelMemory\backend> npm.cmd install


<img width="403" height="42" alt="image" src="https://github.com/user-attachments/assets/573eb415-fe5a-4408-b7a6-5cf69a917c3c" />

         
  ====================================       
   
   note: npm install reads package.json and downloads all required packages.

   After installation, you'll see:

   backend
    │
    ├── node_modules
    ├── package-lock.json


9. Then Start the Backend

   In the backend terminal type the command:

   PS C:\Users\sandy\Git Travelmemory\TravelMemory\backend>node index.js
   
  <img width="452" height="39" alt="image" src="https://github.com/user-attachments/assets/d69c0e2c-6e39-4d09-ad46-bd93e7f29fb2" />

 11. This confirms:
    1. the Express server is running,
    2. the application successfully connected to MongoDB.

  ========================================= 

  frontend explanation :

  The frontend is built using React.

  Its job is to:

  Display travel memories.
  Show images and trip details.
  Let users add, edit, or delete trips.
  Send requests to the backend.

  It looks like below:

  React Frontend (localhost:3000)
            │
            │ HTTP Requests
            ▼
  Node.js Backend (localhost:3001)
            │
            ▼
   MongoDB Atlas 

   ============================= 

   11. front end folder looks like below:

       <img width="203" height="272" alt="image" src="https://github.com/user-attachments/assets/0c1b199a-254f-45e0-9afe-8f108bb68390" />

  What each folder does is :

       | Folder/File     | Purpose                                            |
| --------------- | -------------------------------------------------- |
| `public/`       | Contains static files like `index.html` and icons. |
| `src/`          | Contains the React application code.               |
| `package.json`  | Lists all React dependencies.                      |
| `node_modules/` | Created after running `npm install`.               |


============== 

12. Expand src.

You may see something like:

<img width="218" height="317" alt="image" src="https://github.com/user-attachments/assets/3b419098-2184-47b3-9af6-ba9d28fd7a18" /> 

src/
│
├── components/
├── App.js
├── index.js
├── App.css
└── ...


| File          | Purpose                                               |
| ------------- | ----------------------------------------------------- |
| `index.js`    | Entry point of the React application.                 |
| `App.js`      | Main component that renders the application.          |
| `components/` | Reusable UI pieces like cards, forms, and navigation. |
| `App.css`     | Styles for the application.                           |

============= 


This is something like below:


index.js
    │
    ▼
App.js
    │
    ├── Navbar
    ├── Home
    ├── Travel Card
    ├── Add Trip Form
    └── Footer


=================== 

13. install Frontend Packages

    React application needs to know where the backend is running.

    Instead of hardcoding the URL in multiple places, you store it in an environment variable.

    Whenever the frontend makes an API call, it can use: process.env.REACT_APP_BACKEND_URL
    which resolves to: http://localhost:3001

15. Open a new terminal (keep the backend terminal running).

    1.  Go to the frontend folder:

   PS C:\Users\sandy\Git Travelmemory\TravelMemory> cd frontend
   PS C:\Users\sandy\Git Travelmemory\TravelMemory\frontend> npm.cmd install
   PS C:\Users\sandy\Git Travelmemory\TravelMemory\frontend> npm.cmd start

<img width="446" height="45" alt="image" src="https://github.com/user-attachments/assets/c9f797da-b05a-49d8-8c3b-1828a7915627" />


<img width="437" height="21" alt="image" src="https://github.com/user-attachments/assets/640091af-7c07-4abb-a2ee-c629a75a0ac9" />


<img width="649" height="449" alt="image" src="https://github.com/user-attachments/assets/bf126c9d-2c7a-490e-b8c9-f0353e325727" />

<img width="273" height="42" alt="image" src="https://github.com/user-attachments/assets/cb9f6aba-12e8-41a9-9dd3-026aebc5b029" /> 


<img width="916" height="425" alt="Screenshot 2026-07-18 210619" src="https://github.com/user-attachments/assets/196d9190-62c6-46ce-a132-dcc8cb29e5b6" />


<img width="818" height="429" alt="Screenshot 2026-07-18 211425" src="https://github.com/user-attachments/assets/cefb0192-d342-42b0-b31f-0e4b4f719ab1" /> 


<img width="937" height="433" alt="Screenshot 2026-07-18 210635" src="https://github.com/user-attachments/assets/7f52b947-4ab7-4059-bed9-adb8127af09d" />



<img width="915" height="423" alt="Screenshot 2026-07-18 211919" src="https://github.com/user-attachments/assets/da07a67d-9e3a-49dc-810e-85f557bc5dbb" />












     


