# A Beginners Guide to Streamlit

The trend of Data Science and Analytics is increasing day by day. From the data science pipleine, one of the most important steps is model deployment. We have a lot of options in python for deploying our model. Some popular framworks as Flask and Django. But the issue with using these framework is that we should have some knowledge of HTML, CSS, and Javascript. To reduce this intricateness, streamlit was developed. Now using streamlit you can deploy any machine learning model and any python project with ease and without worrying about the frontend. Streamlit is very user-friendly.

In this repository, we will learn some instructions to important functions of streamlit, creata a python project, and deploy the project on a local web serve. 

To install streamlit
```
pip install streamlit
```
Once streamlit is installed successfully, run the given python code and if you do not get an error, then streamlit is successfully installed and you can now work with streamlit

**How to run Streamlit file?**
 Open command prompt  or Anaconda shell and type
 ```
streamlit run filename.py
```
You will get a local URL which you can open in teh web browser

**Understanding the Streamlit basic functions**

1. Title:
 ```
# import module
import streamlit as st

# Title
st.title("Hello World!")
```

![Output]()

2. Header and Subheader:
```
# Header
st.header("This is a header")

#Subheader
st.subheader("THis is a subheader")
```

![Output]()

3. Text:
```
# Text
st.text("This is Text")
```

![Output]()

4. Markdown:
```
# Markdown
st.markdown("### This is a markdown")
```

![Output]()

5. Success, Info, Warning, Error, Exception:
```
# success
st.success("Success")

# info
st.info("Information")

# Warning
st.error("Error")

# Exception
exp = ZeroDivisionError("Trying to divide by error")
st.exception(exp)
```
![Output]()

6. Write
Using write function, we can also display code in coding format. This is not possible using st.text(").
```
# Write text
st.write("Text with write")

# Writing python inbuilt function range()
st.write(range10))
```

![Output]()

7. Display Images:
```
# Display Images

# Import Image from pillow to open images
from PIL import Image
img =  Image.opne("stremalit.png")

# display image using streamlit
# width is used to set the width of an image
st.image(img, width=200)
```
![Output3]()

8. Checkbox:
A checkbox returns a **boolean value**. When the box is checked, it returns a **True** value else returns **False** value.

```
# checkbox
# check if the checkbox ic checked
# title of the checkbox is 'Show/Hide'
if
st.checkbox("Show/Hide"):
# display the text if the checkbox returns True value
   st.text("Showing the widget")
```

![Output3]()

9. Radio Button:
```
# radio button
# first argument is the title of the radio button
# second argument is the options for the raido button
status = st.radio("Select Gender: ", ('Male', 'Female'))

# conditional statement to print
# Male if male is selected else print female
# show the result using the success function
if (status == 'Male'):
    st.success("Male")
else:
    st.success("Female")
```
![Output]()

10. Selection Box:
You can select any one option fromt eh select box.
```
# Selection box
# first argument takes the title of the selection box
# second argument takes options
hobby = st.selectbox("Hobbies: ",['Dancing', 'Reading', 'Sports'])

# print the selected hobby
st.write("Your hobby is:", hobby)
```
![Output]()

11. Multi-Selectbox:
```
# multi select box
# first argument takes the box title
# second argument takes the optiosn to show
hobbies = st.multiselect("Hobbies: ", ['Dancing', 'Reading', 'Sports'])

# write the selected options
st.write("You selected", len(hobbies), 'hobbies')
```
![Output]()

12. Button
st.button() returns a **boolean value**. It returns a **True** value when clicke else returns **False**.
```
Create a simple button that does nothing
st.button("Click me for no reason")

# Create a button, that when clicked, shows a text
if(st.button("About")):
     st.text("Welcome!")
```
![Output]()

13. Text input:
```
# Text input:

# save teh input text in the variable 'name'
# first argument shows the tiltel of the text input box
# second argument displays a default text inside teh text input area
name = st.text_input("Enter Your name", "Type Here...")

# display the name when teh submit button is clicked
# .title() is used to get the input text string
if(st.button('Submit')):
     result = name.title()
     st.success(result)
```
![Output]()

14. Slider
```
# Slider
# first argumkent takes the title of the lsider
# second argument takes the starting of the slider
# last argument takes the end number
level = st.slider("Select the level", 1, 5)

# print the level
# format() is used to print value of a variable at a specific position
st.text('Selected: {}'.format(level))
```
![Output]()

**Mini Project**:
Let us collect everything that we learn above and create a BMI Calculator web app.
The formula of BMI Index when weight is in kgs and heights is in meters is:

*bmi = weight/height**2*
```
# import the streamlit library
import streamlit as st

# give a title to our app
st.title('Welcome to BMI Calculator')

# TAKE WEIGHT INPUT in kgs
weight = st.number_input("Enter your weight (in kgs)")

# TAKE HEIGHT INPUT
# raido button to choose height format
status = st.radio('Select your height format: ', ('cms', 'meters', 'feet'))

# compare status value
if(status == 'cms'):
# take height input in centimeters
     height = st.number_input('Centimeters')
     try:
         bmi = weight / ((height/100)**2)
     except:
         st.text("Enter some value of height")
elif(status == 'meter'):
# take height input in meters
      height = st.number_input('Meters')
      try:
          bmi = weight / (height **2)
      except:
          st.text("Enter some value of height")
else:
# take height input in feet
      height = st.number_input('Feet')
# 1 meter = 3.28
      try:
          bmi = weight / (((height/3.28))**2)
      except:
          st.text("Enter some value of height")
# check if the button is pressed or not
if(st.button('Calculate BMI')):
# print the BMI index
       st.text("Your BMI Index is {}.".format(bmi))
# give the interpretaion of BMI index
       if(bmi < 16):
            st.error("You are Extremely Underweight")
       elif(bmi >= 16 and bmi < 18.5):
            st.warning("You are Underweight")
       elif(bmi >= 18.5 and bmi < 25):
            st.success("Healthy")
       elif(bmi >= 25 and bmi < 30):
            st.warning("Overweight")
       elif(bmi >= 30):
            st.error("Extremely Overweight")
```
![Output]()

## Conclusion 
This way streamlit can be used to deploy projects without having any knkowledge of HTML, CSS, or JavaScript.

   

 
