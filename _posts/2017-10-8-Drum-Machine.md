---
layout: post
title: "Drum Machine: Playing Audio Samples with Arduino"
categories: pcomp
---

![alt text](/images/pcomp/drumMachine.jpg)
I made a sample based instrument using Arduino Uno and the [PCM library](http://highlowtech.org/?p=1963){:target="_blank"}.

I began by following the instructions on [this tutorial](http://highlowtech.org/?p=1963){:target="_blank"} and setting up the example. After this worked, I tried creating my own samples. I downloaded samples as wav files and followed the tutorial's instructions on using iTunes to convert them to 8 KHz, 8-bit mono sound mp3 files.

Sample sources: [99 Drum Samples](http://99sounds.org/drum-samples/){:target="_blank"}, [Travis Scott Ad-lib Pack](https://www.youtube.com/watch?v=o4raFeWQia4){:target="_blank"}

Converted mp3 files:
<audio src="/images/pcomp/mp3/kick-electro01.mp3" controls preload></audio>

<audio src="/images/pcomp/mp3/crash-acoustic.mp3" controls preload></audio>

<audio src="/images/pcomp/mp3/clap-tape.mp3" controls preload></audio>

<audio src="/images/pcomp/mp3/Ya%20Ya.mp3" controls preload></audio>

I used the EncodeAudio program as per the tutorial to generate a list of numbers per sample which I then stored in arrays.
```c++
const unsigned char claptape[]
const unsigned char crashacoustic[]
const unsigned char kickelectro[]
const unsigned char yaya[]
``` 

I then added switches and wrote code to read digital input. If a button is pressed, a sample will play. 
```c++
void loop()
{
  if (digitalRead(2) == HIGH){
    startPlayback(claptape, sizeof(claptape));
  }
  if (digitalRead(3) == HIGH){
    startPlayback(crashacoustic, sizeof(crashacoustic));
  }
  if (digitalRead(4) == HIGH){
    startPlayback(kickelectro, sizeof(kickelectro));
  }
  if (digitalRead(5) == HIGH){
    startPlayback(yaya, sizeof(yaya));
  }
}
```

Picture of circuit:
![alt text](/images/pcomp/drumMachineCircuit.jpg)

The sound output from the speakers was really quiet so I added a transistor (2N2222 NPN).
![alt text](/images/pcomp/drumMachineCircuit2.jpg)

Final circuit diagram:
![alt text](/images/pcomp/drumMachinecircuitdiagram.jpg)

<video src="https://github.com/jirrian/jirrian.github.io/blob/master/images/pcomp/drumMachineDemo.mp4?raw=true" width="640" height="400" controls preload></video>
