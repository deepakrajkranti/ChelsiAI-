[![Header](https://i.postimg.cc/1XrrC9N4/Screenshot-from-2022-12-16-17-25-25.png "Header")](yashkumarvaibhav.github.io/mysite)  
  
  
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)![TensorFlow](https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=for-the-badge&logo=TensorFlow&logoColor=white)![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white)  
  
# Hello, folks! <img src="https://raw.githubusercontent.com/MartinHeinz/MartinHeinz/master/wave.gif" width="30px">  
  
This project is crated only for those who are having interest in building Virtual Assistant. Generally it takes a lots of time to write code from scratch to build Virtual Assistant. So, we have built a Library called "ChelsiAI", which gives you easy functionality to build your own Virtual Assistant.  
  
  
## **1. What is Chelsi AI?**  
  
Chelsi AI is a Python Module which is able to perform task like Chatbot, Assistant etc. It provides base functionality for any assistant application. This ChelsiAI is built using Tensorflow, Pytorch, Transformers and other opensource libraries and frameworks. Well, you can contribute on this project to make it more powerful.  
     
  
  
## 2. Prerequisite  
      
- To use it only Python (> 3.6) is required.  
      
- To contribute in project: Python is the only prerequisite for basic scripting, Machine Learning and Deep Learning knowledge will help this model to do task like AI-ML. Read How to contribute section of this page.  
      



## 3. Methodology 
  
  
### 3.1. Installation-

* Install the latest version-  

   ```bash
   pip install ChelsiAI
   ```  

#### Optional Steps (Common Installation Issues)-

* [Optional Step] If Pyaudio is not working or not installed you might need to install it seperately-
	
	In the case of Mac OSX do:
	
	```python
	brew install portaudio
	pip install pyaudio
	```
	In the case of Windows or Linux do:
	
	- Download pyaudio from: lfd.uci.edu/~gohlke/pythonlibs/#pyaudio
	
	- ```pip install PyAudio-0.2.11-cp310-cp310-win_amd64.whl```

* [Optional Step] If pycountry is not working or not installed then Install "python3-pycountry" Package on Ubuntu/Linux-
	
	```
	sudo apt-get update -y
	sudo apt-get install -y python3-pycountry
	```

* [Optional Step] You might need to Install [Microsoft Visual C++ Redistributable for Visual Studio 2022](https://visualstudio.microsoft.com/downloads/#microsoft-visual-c-redistributable-for-visual-studio-2022)

### 4. Description-
 
   You need only this piece of code-  

```
import ChelsiAI  
	 
# create your own function  
# It must contain parameter 'feature_command' which is the command you want to execute  
# Return is optional  
# If you want to provide return value it should only return text (str)  
# Your return value will be displayed or call out by the choice of OutputMethods of ChelsiAI  
  
def custom_function(feature_command="custom command"):  
    # write your code here to do something with the command  
	# perform some tasks # return is optional  
	return feature_command + ' Executed'  
  
obj = ChelsiAI.ChelsiAI(input_method=ChelsiAI.InputsMethods.voice_input_google_api,
                        output_method=ChelsiAI.OutputMethods.voice_output,
                        backend_tts_api='pyttsx3',
                        api_key="c6fd2013918f9bc9a12c5394a819af49",
                        detect_wake_word=False,
                        wake_word_detection_method=ChelsiAI.InputsMethods.voice_input_google_api,
                        bot_name="Chelsi",
                        display_intent=True,
                        google_speech_recognition_input_lang='en',
                        google_speech_recognition_key=None,
                        google_speech_recognition_duration_listening=5)  
 
obj.register_feature(feature_obj=custom_function, feature_command='custom feature')  
  
obj.start()
```  
### 5. Supported Input/Output Methods (Which option do I need to choose?)-
For text input-'

text_input Just ask input from command line

For voice input-

voice_input_google_api It use google free API. After using few minutes GoogleAPI might restrict you to use it. It's a limitation from GoogleAPI. But it's fast, very accurate and consume very less memory.

or

voice_input_deepspeech_streaming ChelsiAI's own Machine Learning model to process voice input and convert into text for further processing. Little slow as compared to GoogleAPI, consume more memory, less accurate. But it's free to use and no restriction.

For text output-

text_output Just print output in command line

For voice output-

voice_output It use 'gtts' or 'pyttsx3' backend to produce voice output. You can set backend_tts_api.
 
 
   
## License  
  
[MIT](https://choosealicense.com/licenses/mit/)
