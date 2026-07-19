# Travel-Memory

1. We clone the Travel Memory project :

Steps to clone:
1. copy the code link from github
2. 
After cloning the project, it should look something like this:

TravelMemory/
│
├── backend/
│
├── frontend/
│
└── README.md

The frontend sends requests to the backend, and the backend stores data in MongoDB.

Steps:

1. In VS code we will create the folders as below:
TravelMemory
    backend
    frontend
2. In MongoDB Atlas, create a Project

   <img width="751" height="215" alt="image" src="https://github.com/user-attachments/assets/41e50151-60b4-48e3-a5fb-f68c79065a14" />

3. Create cluster
   <img width="901" height="333" alt="image" src="https://github.com/user-attachments/assets/12726390-44c3-465f-8146-7d5b896fd6ff" />
   <img width="251" height="112" alt="image" src="https://github.com/user-attachments/assets/21e64efd-77fd-47d4-b0e7-ecea42a36d84" />


   <img width="367" height="131" alt="image" src="https://github.com/user-attachments/assets/5591216a-e24c-4dab-8979-e37df8cd6f53" />


 4. Open your cluster. click connect drivers
    <img width="572" height="376" alt="image" src="https://github.com/user-attachments/assets/00d9ef69-f01e-4c5a-9e99-47b8aa0b1027" />

  <img width="571" height="392" alt="image" src="https://github.com/user-attachments/assets/dd262493-556e-4a58-b325-f0655fce98c5" />

  copy the string, replace the user name and password and data base name :
mongodb+srv://Sandhyashree:<db_password>@travelmemorycluster.sntukb6.mongodb.net/?appName=Travelmemorycluster
  
5. create .env fies in both the backend and frontend.
6. In .env file of backend add the below code:
MONGO_URI=mongodb+srv://Sandhyashree:<db_password>@travelmemorycluster.sntukb6.mongodb.net/?appName=TravelmemoryclusterappName=Travelmemorycluster
PORT=3001
7. In frontend .env file add the below code:
   REACT_APP_BACKEND_URL=http://localhost:3001

   Save both the files: Cntl+S
 8.In VS code :
     


