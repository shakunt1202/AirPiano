## Air Piano

---

### Technical Description of the project:
Air Piano is a project made at the confluence of computer vision and human-computer interaction. To make Air Piano, I have used the Python language and a specialised library called OpenCV. It is an open-source computer vision and machine learning software library.

Another important library that helps us complete this project is the PyAutoGUI library. PyAutoGUI lets your Python scripts control the mouse and keyboard to automate interactions with other applications. PyAutoGUI has several features: Moving the mouse and clicking or typing in the windows of other applications, take screenshots, etc.

---

### Now let’s understand the flow of the project:
The first step is to capture the video stream input of the user.
After we read the input frame by frame, we now need to convert the BGR scale to the HSV scale so that we can work with colours better.
Why do we convert to HSV colour space? The simple answer is that, unlike RGB, HSV separates luma, or the image intensity, from chroma or the colour information. In computer vision, you often want to separate colour components from intensity for various reasons, such as robustness to lighting changes, or removing shadows.

- The hand is detected using the black colour mask we created using the HSV scale. For this purpose, I chose to wear a pair of black gloves because detecting the skin colour was comparatively tougher and would have deprived the project of generalisation.
- After the hand is detected, we find the contours i.e. the boundary of our hand. We then draw a convex hull, to find the surrounding convex polygon. From this polygon, we extract the fingertips using the convexity defects function.
What is Convex Hull? The convex hull, the minimum n-sided convex polygon that completely circumscribes an object.

What are Convexity Defects? Any deviation of the contour from its convex hull is known as the convexity defect.


- There is also a filter applied to get just the fingertips using the distance between the points, i.e. the fingertip and the joint, while you may also choose to use the angle between the fingers to achieve the same.
- Before coming to the use of the PyAutoGUI function, let us draw the piano keys on our frame which will be our “Air Paino Keys”.
- The last part includes the use of the PyAutoGUI library which allows you to do the keyboard operations depending on the coordinates of your hand movements (fingertips to be precise). Now when this program is run, it will track the positions of the fingertips in the frame and automatically press the mentioned keys on the keyboard.

---

### How to run the project:
- Clone the repository 
```
gti clone https://github.com/IcHiGo-KuRoSaKiI/AirPiano.git
```
- Install the required libraries
```
pip install -r requirements.txt
```
- Run the code using the command
```
python flappy_bird.py
```

