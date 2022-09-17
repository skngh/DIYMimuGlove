# DIY Mi.Mu Gloves using the BBC Micro:

##### Disclaimer --- This build involves soldering and the use of the Glover software to get the best use out of it.

## Summary

The Mi.Mu Gloves are a fantastic performance device. They're an easy way to control audio using your body as an instrument. That being said, they come at quite a high cost. A [single glove](https://shop.mimugloves.com) cost over $1,500, so it sadly won't become a home studio regular any time soon. Luckily, there are still things we can do.

## The BBC Micro:bit

After Mi.Mu sold their Glover software separately from the gloves, I checked it out and noticed the ability to connect it to something called the "Micro:bit." After digging a bit more, I discovered that the first prototypes of the gloves were actually made with the Micr:bit, which is a simple "pocket-sized computer" used for educational purposes in early schooling. On top of that, Mi.Mu used to sell a product called the [MINI.MU](https://www.adafruit.com/product/4141), which is essentially what we'll be making. Seems like an odd thing to use for a musical glove, but it actually includes an accelerometer and compass, which we can use to send the same data that the gloves do.

## The Build

First, you'll need to pick up a BBC Micro:bit. You should be able to find one on Ebay or other similar sites; both the V1 or V2 will work.

Next we'll be working with attaching the Micro:bit to a glove of your choice. Depending on what type of glove you have, the method in which you attach the Micro:bit may differ. I personally used a normal cotton glove, and found that sewing on velcro patches such as [these](https://www.amazon.com/gp/product/B00006IC2T/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1) worked perfectly. For the battery pack, I sewed a velcro patch on the back part of the glove, and used super glue to attach the other velcro end to the battery pack. The battery pack is one annoying feature of the gloves, but I find you quickly forget it's there. 

There is a bit of soldering that needs to be done in order to have buttons to control. Like the Mi.Mu Gloves, we can send out specific messages based on which buttons we press. If you want to control reverb and delay both with the pitch input of the glove, you could map reverb to be sent when button 1 is pressed, and delay to be sent with button 2. Without the buttons, you could only map one value to your vertical movement, and that value would be constantly sent. As for the soldering, I used a small perf board as shown below that I soldered the buttons onto, so I could put it on the underside of the glove where my fingers could reach. The top right leg of the button is connected to the matching port on the Micro:bit, and then a wire connects ground to each bottom right leg of the button (the lefts and rights are if viewed from the wire side of the perfboard). The perfboard is connected to the glove with the same double sided tape/velcro method.

If soldering really isn't your thing, you can always pick up some [crocodile clips](https://www.amazon.com/WGGE-WG-026-Pieces-Colors-Alligator/dp/B06XX25HFX/ref=sr_1_6?crid=WT0D2Q62IHG3&keywords=crocodile+clips&qid=1663390982&sprefix=crocodile+clips%2Caps%2C78&sr=8-6) instead, which will allow you to connect the buttons but will be quite annoying to work with.

Next, all you need to do is open up the Glover software, choose the Micro:bit, the version you're using, and you're off to making some music!

![Front of Glove](/front.jpg?raw=true "Front of Glove")

![Back of Glove](/back.jpg?raw=true "Back of Glove")



## Demo

Here's a simple demo I made for a song I wrote. It's using Glover's "Note Matrix" and "Chord Machine" features to randomly sweep through notes I inputted, and to trigger chords using drum hit data. I have a distortion VST being controller with the pitch of the glove when I hold down button 1, and reverb being controller with the yaw + button 2. I've included the patch I used up above for those who want to check it out themselves.

#### Click here for Demo

[![Demo Video](http://img.youtube.com/vi/5-CkCcIOAzc/0.jpg)](http://www.youtube.com/watch?v=5-CkCcIOAzc "DIY Mi.Mu Glove Using a Micro:bit Demo")

## Additional Notes

Some people may be disappointed with the usage of the Glover software since, while substantially cheaper than the Mi.Mu gloves, it is still not the cheapest software out there. While I do believe it is absolutely worth it, I understand the want for a cheaper alternative, and luckily there are absolutely ways to send OSC or MIDI without the Glover software. They will be lacking the amazing GUI of Glover, but still should get the job done. I have not personally tried these methods, but here are some sources to look into:

- [Extensions for the MakeCode Editor to send out MIDI](https://support.microbit.org/support/solutions/articles/19000053392-how-do-i-play-a-midi-instrument-on-the-micro-bit)

- [Pairs with Sonic PI to send out OSC (not wireless)](https://github.com/RBilsland/pxt-sonicpiosc)

- [Build guide to making a MIDI guitar](https://www.youtube.com/watch?v=hG7CxlRxRq0)

- [How to send MIDI into a DAW](https://www.youtube.com/watch?v=Gfp9Ve_YUhg)

- [Another way to send MIDI into a DAW (not wireless)](https://www.youtube.com/watch?v=DcgRHOqSFm8)
