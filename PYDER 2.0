import pyttsx3
import speech_recognition as sr
import webbrowser
import datetime
import wikipedia
import pyjokes
import subprocess,os
print("Welcome to ifeanyi's virtual assistant app: you need a mic to use this application\nprogram will close or will not work if mic not found\n\nTo view commands, say commands:")

# this method is for taking the commands
# and recognizing the command from the
# speech_Recognition module we will use
# the recongizer method for recognizing
def takeCommand():

	r = sr.Recognizer()

	# from the speech_Recognition module
	# we will use the Microphone module
	# for listening the command
	with sr.Microphone() as source:
		print('Listening')
		
		# seconds of non-speaking audio before
		# a phrase is considered complete
		r.pause_threshold = 0.7
		audio = r.listen(source)
		
		# Now we will be using the try and catch
		# method so that if sound is recognized
		# it is good else we will have exception
		# handling
		try:
			print("Recognizing")
			
			# for Listening the command in indian
			# english we can also use 'hi-In'
			# for hindi recognizing
			Query = r.recognize_google(audio, language='en-in')
			print("the command is printed=", Query)
			
		except Exception as e:
			print(e)
			print("Say that again sir")
			return "None"
		
		return Query

def speak(audio):
	
	engine = pyttsx3.init()
	# getter method(gets the current value
	# of engine property)
	voices = engine.getProperty('voices')
	
	# setter method .[0]=male voice and
	# [1]=female voice in set Property.
	engine.setProperty('voice', voices[1].id)
	
	# Method for the speaking of the assistant
	engine.say(audio)
	
	# Blocks while processing all the currently
	# queued commands
	engine.runAndWait()

	
def tellDay():
	
	# This function is for telling the
	# day of the week
	day = datetime.datetime.today().weekday() + 1
	
	#this line tells us about the number
	# that will help us in telling the day
	Day_dict = {1: 'Monday', 2: 'Tuesday',
				3: 'Wednesday', 4: 'Thursday',
				5: 'Friday', 6: 'Saturday',
				7: 'Sunday'}
	
	if day in Day_dict.keys():
		day_of_the_week = Day_dict[day]
		print(day_of_the_week)
		speak("The day is " + day_of_the_week)


def tellTime():

        import time

        t = time.localtime()
        current_time = time.strftime("%H:%M:%S", t)
        speak("the time:")
        print(current_time)
	

def Hello():
	
	# This function is for when the assistant
	# is called it will say hello and then
	# take query

	speak("hello if arnee, how may I help you")


def Take_query():

	# calling the Hello function for
	# making it more interactive
	Hello()
	
	# This loop is infinite as it will take
	# our queries continuously until and unless
	# we do not say bye to exit or terminate
	# the program
	while(True):
		
		# taking the query and making it into
		# lower case so that most of the times
		# query matches and we get the perfect
		# output
		query = takeCommand().lower()
		if "open games" in query:
			speak("Opening Games ")
			
			# in the open method we just to give the link
			# of the website and it automatically open
			# it in your default browser
			webbrowser.open("https://www.coolmathgames.com/")
			continue
		
                        

		elif "translate" in query:
			speak("loading translator ")
			webbrowser.open("https://translate.google.com/")
			continue

		elif "search" in query:
			speak("loading google search ")
			import pywhatkit as kt
			target = query
			kt.search(target)
			continue


		elif "commands" in query:
			speak("opening commands ")
			webbrowser.open("https://github.com/CoderIfeanyi/PYDER-2.0/blob/main/Commands")
			continue

		elif "camera" in query:
			speak("opening camera ")
			import subprocess, os
			subprocess.run('start microsoft.windows.camera:', shell=True)


		elif "play classic fm" in query:
			speak("opening classic fm in you browser")
			webbrowser.open("https://www.globalplayer.com/live/classicfm/uk/")
			continue

		elif "play premier praise" in query:
			speak("opening premier praise in you browser")
			webbrowser.open("https://www.premierpraise.com/radio-windowed")
			continue

		

		elif "music" in query:
			speak("playing music ")
			webbrowser.open("https://www.youtube.com/watch?v=l_9y2czDCaY")
			continue

		elif "joke" in query:
			speak("Ok,  Let me think ")
			joke=pyjokes.get_joke(language='en', category= 'neutral')
			speak(joke)
			speak("hahaha ")
			



		elif "created you" in query:
			speak("Coder Ifarnee created me, I will take you to his website and github account ")
			webbrowser.open("https://github.com/CoderIfeanyi")
			webbrowser.open("https://coderifeanyi.github.io/Ifeanyi-Website/")
			continue

		elif "homework" in query:
			speak("opening homework sites ")
			webbrowser.open("https://www.satchelone.com/")
			webbrowser.open("https://vle.mathswatch.co.uk/vle/")
			continue

               
		elif "day" in query:
			tellDay()
			continue
		
		elif "time" in query:
			tellTime()
			continue
		
		# this will exit and terminate the program
		elif "close program" in query:
			speak("goodBye. Check Out CoderIfarnee on Github for more projects")
			exit()
		
		elif "who is" in query:
			
			# if any one wants to have a information
			# from wikipedia
			speak("Checking the wikipedia ")
			query = query.replace("wikipedia", "")
			
			# it will give the summary of 4 lines from
			# wikipedia we can increase and decrease
			# it also.
			result = wikipedia.summary(query, sentences=4)
			speak("According to wikipedia")
			speak(result)
		
		elif "tell me your name" in query:
			speak("I am PYDER, Coded by Ifarnee and Your desktop Assistant")

if __name__ == '__main__':
	
	# main method for executing
	# the functions
	Take_query()
