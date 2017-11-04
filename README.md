
Machine Learning project to recognise people from an Image just like facebook.


## USED:

- Python 3.x
- Numpy
- Scipy
- [Scikit-learn](http://scikit-learn.org/stable/install.html)
- [dlib](http://dlib.net/)

- Extras:

    - OpenCV (required only in `webcam.py` for capturing frames from the webcam)

    - For using `./demo-python-files/projecting_faces.py` you will need to install [Openface](https://cmusatyalab.github.io/openface/setup/).

        To install Openface, follow the below instructions:
        ```bash
            $ git clone https://github.com/cmusatyalab/openface.git
            $ cd openface
            $ pip install -r requirements.txt
            $ sudo python setup.py install
        ```


## Procedure:

- Clone this repository `git clone :https://github.com/aadil-srivastava01/facial_recognition.git.

### Training:
- Make folder `training-images`.
- Add images of each person you want to recognise to a folder by their name in `training-images`.

    Example
    ```bash
    $ mkdir training-images
    $ cd training-images
    $ mkdir Name_Of_Person
    ```
    Then copy all the images of that person in `./training-images/Name_Of_Person` folder.


- Run on cmd `python create_encodings.py` to get the encodings of the images and the labels.
    This will create `encoded-images-data.csv` and `labels.pkl` files.


    Note: There has to be only one face per image otherwise encoding will be for the first face found in the image.

- Run on cmd `python train.py` to train and save the face recognition classifier.
    This will create `classifier.pkl` file.
    It will also create `classifier.pkl.bak` backup file if the classifier with that name already exists.



### Prediction:
- Make folder `test-images` which contains all the images you want to find people in.

 

- Run on cmd `python predict.py` to predict the faces in each image.

