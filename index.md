<body style="overflow-x:scroll">

<h1>Welcome to the EreshCalcs2 Wiki!</h1>

<a href="https://andell4301.github.io/EreshCalcs2/basics">Basics</a> | <a href="https://andell4301.github.io/EreshCalcs2/syntax">Syntax</a> | <a href="https://andell4301.github.io/EreshCalcs2/arguments">Arguments</a> | <a href="https://andell4301.github.io/EreshCalcs2/assumptions">Assumptions</a> | <a href="https://andell4301.github.io/EreshCalcs2/reading">Reading</a> | <a href="https://andell4301.github.io/EreshCalcs2/FAQ">FAQ</a>

<h2>What is this?</h2>
This wiki is to help document how to use the new, revamped calculation command with Ereshbot. 
Currently, this command is <code>/calc2</code>.
<h2>I already know how to use the original EreshBot calc command. Should I still read this?</h2>
That depends. If you don't care about the new features, then probably not. Everything that you could do with the old 
command can be done in the exact same way with the new command, except for the fact that the servant name now has to 
be one word (i.e. from "Arjuna Alter" to "ArjunaAlter") and that everything goes in the same box now.
<br><br>
For example:
<br>
<b>Old Command</b>:<br>
<code>/calc servant:</code> Arjuna Alter <code>string:</code> ce2400 n80 a30 p50 m20 saber hp1000
<br><b>New Command</b>:<br>
<code>/calc2 string:</code> ArjunaAlter ce2400 n80 a30 p50 m20 saber hp1000

With that said, the new command is much, much more powerful. If you'd like to take advantage of all the new 
features and capabilities it now offers, you should definitely continue on reading.
<h2>What are the main differences between the old and new versions? Why was the command rewritten?</h2>
The major difference between the two is that the old version was written to calculate one card on one enemy at a time,
whereas the new version can calculate multiple cards on multiple enemies at once.
<br>

This means that with the new version of calcs, you could simulate a whole command chain, a noble phantasm 
that hits a wave of enemies all with different debuffs, or even an entire three turn looping comp all from within 
a single command.

That is not to say, however, that multi-calcs are the only new tricks up the revamped command's proverbial sleeve.
The new version of the command comes with a host of new arguments to use, critical star calculation support, 
and generally far more granular control over exactly what it is you want to calculate.