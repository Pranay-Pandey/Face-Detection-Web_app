# Face Detection Web App

## About the Project
Face Detection App is a web app that allows a user to get group photos that include them without having to keep or sort through all of the photos, saving them time and
storage space. When a photo is uploaded, the app identifies the faces in it and arranges them according to the users who have been identified. Each identified user gets
a separate album with all their photos allowing them to get the photos they need seamlessly.
Upload group photos, arrange them by faces using ML and share them with ease. 🤳🤖

## Installation 
### Cloning the Repo on your local machine
<ol>
  <li>Run the following command to clone the repo: <code>git clone https://github.com/Pranay-Pandey/Face-Detection-Web_app.git</code></li>
  <li>Navigate to the project directory: <code>cd Face-Detection-Web_app</code></li>
  <li>Create a virtual environment named .env: <code>python3 -m venv .env</code></li>
  <li>Activate the virtual environment: <code>source .env/bin/activate</code></li>
  <li>Download the required dependencies: <code>pip install -r requirements.txt</code></li>
  <li>Run the setup script: <code>bash setup.sh</code></li>
  <li>Go to <a href="http://127.0.0.1:8000/">http://127.0.0.1:8000/</a></li>
  <li>You're ready to go! <span style="font-size:1.5em;">🤘</span></li>
</ol>


![3](https://user-images.githubusercontent.com/72318258/150670158-1e18c160-9a04-4412-999a-051e228887cc.png)
Here I have uploaded 6 images of Harry Potter cast.


![4](https://user-images.githubusercontent.com/72318258/150670161-1a04b223-aa9a-4b64-a66d-822e5384fddf.png)
After pressing "Process" we get these 3 albums of faces present in the photos we uploaded.


![5](https://user-images.githubusercontent.com/72318258/150670162-4a8ae9d4-34a3-4c25-8e64-8442c0cd36ba.png)
This is the album for Ron Weasley, also known as Rupert Grint. Of the original six images, he appears in four, and these images can now be downloaded individually or as a group in a zip file.

## How does it work?


When a user uploads a group photo, the [Face Recognition](https://github.com/ageitgey/face_recognition) library is used to detect all the faces present in the image. The detected faces are then transformed into 128-dimensional vectors, representing each image by a single vector. To group these vectors into clusters of similar images, the [DBSCAN](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.DBSCAN.html) algorithm is applied, which is an unsupervised clustering method that doesn't require knowledge of the number of clusters beforehand. By clustering images that are similar to each other, the algorithm aims to create clusters that belong to a single person, resulting in individual albums for each person in the group photo. From these albums, users can download individual images or the entire album.




