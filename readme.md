# Eos OSC Lighting Controls Examples
### What is this?
This repository is a collection of (for now only) Max 8 patches that provide quick examples for controlling the various lighting fixtures in the iStage environment. Each patch shows the methods for controlling fixtures in different common groups. Feel free to incorporate these patches into your iStage installations for quicker adaptation to the new lighting control system (EOS Nomad).

---

## Where can I get more information about the OSC addresses available?
 **If you are in the iStage**
 Head over to the lighting computer (Leftmost computer) and open a web browser. Type in "http://127.0.0.1:4242" to access the web based reference material.
 
 **If you aren't in the iStage**
 Uploading a file with the more comprehensive list of available OSC addresses is on my todo list. For now just poke around in the included patches to get the gist of the more crucial addresses.
 
 ---
 
 ## I've used the old system, what's different?
 For the most part, everything OSC-wise got much simpler!
 
 **For Example**
 If you wanted to set the red channel of all of the Source 4 lamps over the main stage you would have needed to send this message:
 `/s4/master/list7 <your value> 0. 0. 0. 0. 0. 0.`
 
 Now, just send:
`/lustr/red <your value>`

If you still want to control all 7 LED emitters in the lamps, it's still possible using:
`/lustr/7color 0 0 0 0 0 0 0  // replace the 0s with the actual values that you want to send`

If you instead wanted to only control the first lamp in the Source 4 group rather than the whole series, you only need to send somethinng like:
`/lustr1/red <your value>`

---

## Where can I learn more about OSC?
The [official OSC website](http://opensoundcontrol.org/) is a good place to start!

There are OSC implementations in almost any language you can think of, but here are a some common ones:
- [Max](https://overprocessedthinking.com/osc-and-max-7/) or just checkout the patches in this repository for some quick examples.
- [Touch Designer](https://matthewragan.com/2013/10/10/sending-and-receiving-osc-values-with-touchdesigner/)
- [Swift](https://github.com/ExistentialAudio/SwiftOSC)
- [Node.js](https://www.npmjs.com/package/osc)
- [C++](https://github.com/kaoskorobase/oscpp)
- [C#](https://github.com/ValdemarOrn/SharpOSC)

---

## Listing of fixtures, their names, and some key addresses

NOTE: All parameters to OSC addresses listed here are normalized floating-point values between 0 & 1.

- **lustr** group
    - Member Fixtures: lustr1, lustr2, lustr3, lustr4, lustr5, lustr6, lustr7, lustr8, lustr9, lustr10, lustr11, lustr12
    - Key Addresses: 
        - /7color : controls the 7 LED emitters
        - /intens : controls lamp brightness
        - /hs : set color by way of hue and saturation
- **mega** group
    - Member Fixtures: side-light-L1, side-light-L2, side-light-L3, side-light-L4, side-light-R1, side-light-R2, side-light-R3, side-light-R4
    - Key Addresses:
        - /rgbw : controls the color via the Red, Green, Blue, and White LEDs
        - /intens: sets the brightness of the light
- **lamps** group
    - Member Fixtures: lamp1, lamp2, lamp3, lamp4, lamp5, lamp6, lamp7, lamp8
    - Key Address:
        - /intens : sets the lamp brightness
- **i-cue**
    - Members: i-cue and i-cue-lamp
    - i-cue addresses:
        - /pan : controls the pan of the mirror
        - /tilt : controls the tilt of the mirror
        - /pantilt : controls mirror pan & tilt together
    - i-cue-lamp address:
        - /intens : brightness of the lamp attached to the I-Cue
- Fixtures not a part of any group
    - All fixtures in this area only have the /intens address.
    - scoopR, scoopL
    - boothR, boothL, entryway
    - carpet-spotR, carpet-spotL
    - carpet-ir1, carpet-ir2, carpet-ir3, carpet-ir4
    

