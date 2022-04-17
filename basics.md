## How To Actually *Use* The Calculation Command
Like EreshBot's other commands, the calculation command is a slash command.
To utilize slash commands, you'll want to first input the character `/` into your chat box.
When you do this, any and all slash commands available to you from all of the bots in your server
(not just EreshBot!) will appear as a list. You'll know that a command is an EreshBot command if it has the 
<img width="20" alt="EreshBot Avatar" src="https://cdn.discordapp.com/avatars/912209452596363325/1ae321df6d8233616edf7b7504bf1dec.png"> 
icon by its name and says `Eresh (Slash)` on the right side. 
<br>
<img width="859" alt="Slash Command Input" src="https://user-images.githubusercontent.com/56235026/163707477-683a498c-5d50-400a-a298-573538b2cf9a.png">
<br>
<br>
After entering `/` into the chat box and pulling up the list of slash commands, you'll want to type out `calc2` 
to search for the command in question. Once you find the EreshBot command named `calc2`, you'll want to hit your enter
key to select it.
<br>
<img src="https://user-images.githubusercontent.com/56235026/163707996-c863c0c2-561f-4b4d-ae19-ecaa81d8fa26.gif" alt="Searching For Slash Commands">
<br>
<br>
Once you've hit the enter key and selected the `calc2` command, a box labeled `string` will appear. This will be where 
you will enter what we call your
<span style="color: #209e5f"> calculation string</span>. This is the text that you use to tell EreshBot what it is you
want to calculate.
<br>
<img width="346" alt="Screenshot 2022-04-17 051507" src="https://user-images.githubusercontent.com/56235026/163708289-ef16a5c9-d8df-4d6b-8aba-e5953631bef1.png">

## Basic Input Syntax
The fundamental syntax for a calculation command is as follows:

<span style="color: #1ac8ff"> /calc2 </span>
<span style="color: #3eef6f"> string: </span>
<span style="color: #e30000"> servant </span>
<span style="color: #f4a120"> arguments </span>
<br>
As you've seen above, once you have selected the 
<span style="color: #1ac8ff"> /calc2</span> command, 
the <span style="color: #3eef6f"> string:</span> box will automatically appear as well. 
All you will be responsible for typing after you have selected the command are the 
<span style="color: #e30000"> servant</span>
and the command <span style="color: #f4a120"> arguments</span>.

The <span style="color: #e30000"> servant</span> is technically an argument itself, but it is distinct in that it is
required. The servant refers to the specific servant who you will be calculating for. You will not be able to run the 
command without providing a servant.

As you will see shortly, arguments are separated by spaces. Since the servant name is technically an argument itself, 
it is no exception. Only the first argument is considered to be the servant, so this means that the servant name
<u>**cannot contain spaces**</u>. If you need to specify a servant whose name contains a space, such as 
`Arjuna Alter`, you can simply enter it as `ArjunaAlter`.

After the servant, the rest of the <span style="color: #f4a120"> arguments</span> that you provide, if any, will make 
up the details of your specific calculation. The documentation goes into more detail about what types of arguments there 
are in the [arguments](./arguments) page, but for the time being, know that:
<br>
A `20% attack buff`, such as 
<img width="20" alt="Merlin" src="https://static.atlasacademy.io/JP/Faces/f_5008000.png">
[Merlin's](https://apps.atlasacademy.io/db/JP/servant/150)
<img width="20" alt="Dreamlike Charisma" src="https://static.atlasacademy.io/JP/SkillIcons/skill_00300.png">
[Dreamlike Charisma](https://apps.atlasacademy.io/db/JP/skill/321550), would be represented as `a20`.
<br>

A `50% buster buff`, such as 
<img width="20" alt="Merlin" src="https://static.atlasacademy.io/JP/Faces/f_5008000.png">
[Merlin's](https://apps.atlasacademy.io/db/JP/servant/150)
<img width="20" alt="Hero Creation" src="https://static.atlasacademy.io/JP/SkillIcons/skill_00306.png">
[Hero Creation](https://apps.atlasacademy.io/db/JP/skill/323650), would be represented as `bm50`.

The way to separate multiple arguments is through spaces. So if you wanted to provide both 20% attack and 
50% buster buffs, you would enter `a20 bm50`.

With all of that in mind, let's try to put it together. Say you wanted to calculate for 
<img width="20" alt="Ereshkigal" src="https://static.atlasacademy.io/JP/Faces/f_3032000.png">
[Ereshkigal](https://apps.atlasacademy.io/db/JP/servant/196)
with a 20% attack buff and 50% buster buff. How do you think you might do that?

You'd do: 
<span style="color: #1ac8ff"> /calc2 </span>
<span style="color: #3eef6f"> string: </span>
<span style="color: #e30000"> Ereshkigal </span>
<span style="color: #f4a120"> a20 bm50 </span>
<br>

