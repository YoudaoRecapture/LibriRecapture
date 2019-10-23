#  LibriRecapture

LibriRecapture is a real-world open audio corpus that focuses on recapture speech recognition.  We have  noticed that many people are using their mobile devices to recapture the sound from TV, radio, etc, and then use their translation application to help them understand language they are not familiar with. This kind of behavior can introduce  distortions from replay and recapture devices,  reverberations, and background noises, which can degrade the performance of the ASR systems.  Motivated by this, we use LibriSpeech as our replay audio source  and recapture audio using mobile microphones. **891 hours** of audio were successfully replayed and **1892 hours** were successfully recaptured.

# Collection of the data

![](https://tva1.sinaimg.cn/large/006y8mN6ly1g87b2jsppfj30my0h8djx.jpg)



-  We choose the LibriSpeech corpus which is derived from read audio books as our starting point.  

- For simplicity, we combine the short replay audio into a long replay audio (around 12 hours so that we could play it during night automatically) and trim the recapture audio according to the combine sequence. However, there are time shifts when playback audio (around 200ms every hour, it depends on the replay device).  These time shifts cause errors when trim the recapture audio if we simply trim the audio according the original audio length. To make sure right segmentation of the trimmed audio, we insert a pure tone  between the small piece of the audio as the boundary, which serves as a flag whether the segmentation of the audio is correct. We also add a special synchronization tone  every one hour. The special synchronization tone is 3-second long tone with 10-second silence before and 47-second silence tone after. Every one hour we do synchronization and adjust the timestamps when we trim the recapture audio.

- The audio is played and captured mainly in several small size rooms, the size of the small rooms is around $6m\times 4m\times3m$, while around one-tenth of the recordings are recorded in medium size rooms which are around  $10m\times 9m\times 4m$.  We use laptops, portable loudspeakers, TVs as our replay devices, and the recapture devices are mainly smartphones  because most of the recaptured speech recognition requests  are using smartphones.  The recapture devices cover both high-end and low-end smart phones.

- We put the recapture devices at  distances of 20cm, 40cm, 80cm from the replay devices.   The audio  captured by Androids is sampled at 16000HZ, while the audio captured by Apple series is  sampled at 22050HZ. All of the audio is  16bits wide WAV format and later encode into FLAC format.

  ![](https://tva1.sinaimg.cn/large/006y8mN6ly1g87bbrokwuj30ge0j4wfj.jpg)







# The Recapture Audio Analysis

Te playback-recapture process introduces a  lots of distortions includes background noise, reverberations, loss during the propagation as well as the possible front-end processing for audio from the smartphone





# 

