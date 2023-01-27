# Face Detection Web App

## About the Project
Face Detection App is a web app that allows a user to get group photos that include them without having to keep or sort through all of the photos, saving them time and
storage space. When a photo is uploaded, the app identifies the faces in it and arranges them according to the users who have been identified. Each identified user gets
a separate album with all their photos allowing them to get the photos they need seamlessly.
Upload group photos, arrange them by faces using ML and share them with ease. 🤳🤖

## Installation
    1. ### Setting up git:
    - [Download and install the latest version of Git.](https://git-scm.com/downloads)
    - (Optional) [Set your username in Git.](https://help.github.com/articles/setting-your-username-in-git)
    - (Optional) [Set your commit email address in Git.](https://help.github.com/articles/setting-your-commit-email-address-in-git)
    2. ### Cloning the Repo in your local machine
    - Run ``git clone git@github.com:Pranay-Pandey``
    - ``cd Face-Detection-App``
    - Make a virtual environment named .env ``python3 -m venv .env``
    - Activate ``.env`` by ``source .env/bin/activate``
    - Download the requirements ``pip install -r requirements.txt``
    - Run script ``bash setup.sh``
    - Go to  http://127.0.0.1:8000/
    - You are good to go! 🤘


![3](https://user-images.githubusercontent.com/72318258/150670158-1e18c160-9a04-4412-999a-051e228887cc.png)
Here I have uploaded 6 images of Harry Potter cast.


![4](https://user-images.githubusercontent.com/72318258/150670161-1a04b223-aa9a-4b64-a66d-822e5384fddf.png)
After pressing "Process" we get these 3 albums of faces present in the photos we uploaded.


![5](https://user-images.githubusercontent.com/72318258/150670162-4a8ae9d4-34a3-4c25-8e64-8442c0cd36ba.png)
This is the album for Ron Weasley, also known as Rupert Grint. Of the original six images, he appears in four, and these images can now be downloaded individually or as a group in a zip file.

## How does it work?


When a user uploads a group photo, the [Face Recognition](https://github.com/ageitgey/face_recognition) library is used to detect all the faces present in the image. The detected faces are then transformed into 128-dimensional vectors, representing each image by a single vector. To group these vectors into clusters of similar images, the [DBSCAN](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.DBSCAN.html) algorithm is applied, which is an unsupervised clustering method that doesn't require knowledge of the number of clusters beforehand. By clustering images that are similar to each other, the algorithm aims to create clusters that belong to a single person, resulting in individual albums for each person in the group photo. From these albums, users can download individual images or the entire album.




