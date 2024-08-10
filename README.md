Replace this code in the 5th cell if the default code does not work in the first Notebook.

```
#@title Separate Vocal and Instrument/Noise using Demucs
import subprocess

AUDIO_INPUT = f"/workspace/sph-voice-clone/youtubeaudio/{AUDIO_NAME}.wav"

if dataset == "Drive":
    command = f"demucs --two-stems=vocals {AUDIO_INPUT}"
elif dataset == "Youtube":
    command = f"demucs --two-stems=vocals {AUDIO_INPUT}"

# Split the command into a list and add the audio file path as the last argument
command_list = command.split()
command_list.append(AUDIO_INPUT)

result = subprocess.run(command_list, stdout=subprocess.PIPE, stderr=subprocess.PIPE)
print(result.stdout.decode())
print(result.stderr.decode())
```
