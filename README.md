import speech_recognition as sr

# get path to "gabi.wav" in the same folder as this script
from os import path
AUDIO_FILE = path.join(path.dirname(path.realpath(__file__)), "gabi.wav")

r = sr.Recognizer()

with sr.AudioFile(AUDIO_FILE) as source:
    audio = r.record(source)  # this line is responseble to read the entire audio file

document = r.recognize_google(audio)
