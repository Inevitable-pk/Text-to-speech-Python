import os
import pyttsx3

def speak(text):
    engine = pyttsx3.init()
    voices = engine.getProperty("voices")
    engine.setProperty("voice", voices[1].id)
    rate = engine.getProperty("rate")
    rate = engine.setProperty("rate", rate-50)
    engine.say(text)
    engine.runAndWait()

if __name__ == "__main__":
    print("Welcome to PySpeech 1.1.0")
    while True:
        text = input("Enter what you want me to speak: ")
        if text == "quit":
            speak("Bye bye, I am exiting.")
            break
        speak(text)
