## How To Calc Chen Gong and Arash
A common question I see is how to calculate damage for [Chen Gong](https://apps.atlasacademy.io/db/JP/servant/258)
and [Arash](https://apps.atlasacademy.io/db/JP/servant/16). Indeed, this is very difficult to do, and oftentimes I 
advise that it is easier to simply test in-game or use a shortcut to approximate the results. Nevertheless, as I've 
seen the question crop up increasingly more frequently lately (perhaps due to the approaching release of Castoria), this
guide will explain *why* they are difficult to calc and how to calc them.

## Where Is The Difficulty?
The difficulty with calcing Chen Gong and Arash stems from their unique Overcharge mechanic on their Noble 
Phantasms. Let's take a look at Chen Gong's NP, for example.
![](images/gong-arash/gong-oc.png)
As you can see, Chen Gong's NP deals additional damage based on the level of Overcharge he has. At OC1, there
is no additional damage.

Now <span style="color: #FF0000;font-weight:bold;"> a common misconception</span> is that the overcharge effect on Gong/Arash directly 
increases the multiplier of Effect 1. So for example, if you use Chen Gong's NP at Lv5 + OC2, then according to this
misconception, you'd get an accurate result by simply calcing `/calc string: gong npv1725` where 1725 is the 1500% of 
NP5 + the 225% of OC2. This misconception probably stems from the fact that Wizard, the OG calc bot, claims that the npv 
arg can be used to account for Arash.

__In reality, however, it is not so simple.__


## How Chen Gong and Arash's OC Effects Actually Work
Whats actually happening with Chen Gong and Arash is that their Overcharge function is an **entirely 
separate damage function**.
Let's take a look at a sample case to help explain.