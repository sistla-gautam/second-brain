```python
!pip install gtts

  

from gtts import gTTS #Import Google Text to Speech

from IPython.display import Audio #Import Audio method from IPython's Display Class

tts = gTTS('hello joyjit') #Provide the string to convert to speech

tts.save('1.wav') #save the string converted to speech as a .wav file

sound_file = '1.wav'

Audio(sound_file, autoplay=False)
```