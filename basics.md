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

<span style="color: #0083af;font-weight:bold"> /calc2 </span>
<span style="color: #00a82f;font-weight:bold"> string: </span>
<span style="color: #b70000;font-weight:bold"> servant </span>
<span style="color: #c97c00;font-weight:bold"> arguments </span>
<br>
As you've seen above, once you have selected the 
<span style="color: #0083AFFF;font-weight:bold"> /calc2</span> command, 
the <span style="color: #00A82FFF;font-weight:bold"> string:</span> box will automatically appear as well. 
All you will be responsible for typing after you have selected the command are the 
<span style="color: #B70000FF;font-weight:bold"> servant</span>
and the command <span style="color: #C97C00FF;font-weight:bold"> arguments</span>.

<hr>
<h4 style="color:#B70000FF">The Servant Argument</h4>
The servant is technically an argument itself, 
but it is distinct in that it is required. The servant refers to the specific servant who you will be calculating for. 
You will not be able to run the command without providing a servant.

As you will see shortly, arguments are separated by spaces. Since the servant name is technically an argument itself, 
it is no exception. Only the first argument is considered to be the servant, so this means that 
<span style="color: #B70000FF;font-weight:bold;border-bottom: 2px solid">
the servant name cannot contain spaces
</span>.
If you need to specify a servant whose name contains a space, such as 
`Arjuna Alter`, you can simply enter it as `ArjunaAlter`.

Please note that the servant name is fuzzy-matched. This basically means that if you give EreshBot a servant it 
doesn't know, it will try to guess who you mean. "Arashkigal" would match to "Ereshkigal" and so on. Aliases can also
be used, such as "Eresh" for "Ereshkigal." Finally, both servant collection numbers (ex. 196) and IDs (ex. 303200) can 
be used.

<hr>
<h4 style="color:#C97C00FF">The Servant Argument</h4>
After the servant, the rest of the arguments
that you provide, if any, will make up the details of your specific calculation. The documentation goes into more 
detail about what types of arguments there are in the [arguments](./arguments) page, but for the time being, know that:
<br>
<br>
A `20% attack buff` would be represented as `a20`.
<br>
A `50% buster buff` would be represented as `bm50`.

The way to separate multiple arguments is through spaces. So if you wanted to provide both 20% attack and 
50% buster buffs, you would enter `a20 bm50`.

<hr>
<h4>Basic Input Summary</h4>

With all of that in mind, let's try to put it together. Say you wanted to calculate for 
<img width="20" alt="Ereshkigal" src="https://static.atlasacademy.io/JP/Faces/f_3032000.png">
[Ereshkigal](https://apps.atlasacademy.io/db/JP/servant/196)
with a 20% attack buff and 50% buster buff. How do you think you might do that?

You'd do: 
<span style="color: #0083AFFF;font-weight:bold"> /calc2 </span>
<span style="color: #00A82FFF;font-weight:bold"> string: </span>
<span style="color: #B70000FF;font-weight:bold"> Ereshkigal </span>
<span style="color: #C97C00FF;font-weight:bold"> a20 bm50 </span>
