---
title: Road Running Timing
layout: page
permalink: /projects/raceTimingPortfolio/
---
### Behind the Scenes of Timing a Road Race ###
<body>
I've been an avid runner on and off over the years. Personally, the act of physically running is my least favorite part. The best aspect of running is the community that comes along with it. Running is an individual sport that requires nothing more than a decent pair of shoes making it accessible to just about anyone uniting folks from many walks of life. This makes the atmosphere of local road races one of a kind - events that promote exercise, invite a healthy competitive spirit, drive engagement with a diverse group of people, and usually are all in pursuit of raising money for local charities.
</body>

During my PhD I responded to a local running store's call for part-time race timers (I've always been fascinated with the invisible folks behind the scenes, which explains my long stint as a Camera operator and switchboard operator at my local church throughout high school). Although I'd never really thought much about the technology that allows you to scan that QR code after a race and instantly get a milli-second-level precision finishing time.

I've worked for the store for over a year now timing all kinds of races from 20-person 5ks to larger multi-race events of 1200+ runners.

<figure>
  <img src="/assets/images/SR-TimingArticle/IMG_5743.jpeg"
       alt="The Strictly Running timing team at the 52nd annual Governor's Cup 5k + Half-Marathon on April 11th, 2025">
  <figcaption>
    The Strictly Running timing team at the 52nd annual Governor's Cup 5k + Half-Marathon on April 11th, 2025.
  </figcaption>
</figure>

So here I thought I'd write a short column describing the simple yet magic technology behind race timing.

### Chip-Timing ###

There are actually quite a few articles out there describing the various methods to timing a road race, but in the great year of 2026, many of those methods are quite antiquated and comparably unreliable to the gold standard, which is now chip-timing.

In simple terms, chip-timing is an automated timing system where participants cross over devices that read the number of the chip and record the exact time that chip crossed the sensor.

In more technical terms, chip-timing consists of an ultra high frequency (UHF) RFID (Radio-frequency Identification) timing chip (technically called a transponder) ~usually~ attached to the runners bib, a race controller (technically called an RFID reader or decoder), and one or more RFID antennas (technically called a transmitter).

SCHEMATIC OF THE TIMING SYSTEM

The chip-timing system you'll often see at events around Columbia is called a passive system, meaning constant power is supplied to the RFID antennas which emit a continouous radio signal. In this case the system is active and the timing chips are passive, as opposed to an active system where the chips themselves are supplied power. The heart of the system is the reader, which is the device that supplies power to the antennas and interprets the signal reflected back to the antennas from the timing chip. When the antennas emit a signal to the timing chip, the timing chip is turned on by the energy of the radio wave and sends a unique signal back to the antenna and eventually the reader. The reader translates and interprets that signal as your bib number. You can read about the physics of RFID technology in more detail here: https://www.atlasrfidstore.com/rfid-insider/rf-physics/

PHOTO OF CHIP AND BIB

At Strictly Running we use the ChronoTrack Timing system. On the back of your bib is a long, vertically placed, strip of plastic which embeds the actual RFID transponder. In ChronoTrack lingo, this is called a B-tag or "bib tag", with each b-tag given a unique chip that is programmed to the specific number of the bib. Only Chronotrack knows (1) the specific radio frequency needed to excite the tag, and (2) how to decode the signal reflected back from the tag's antenna to the reader's antenna. This is where the race controller comes in, which is basically a highly-specific reader for ChronoTrack race bibs.

PICTURE OF CHRONOTRACK TIMING SYSTEM

This all obviously happens incredibly fast. When you cross over the timing mat and antenna, the time is recorded and the signal is sent back to the race controller which translated into your bib number. The now-digitized information is then sent to the computer where specialized software containing a database of race registrants associates the number with the registrants name and age. From there, the data is organized before being copied to the SR website!