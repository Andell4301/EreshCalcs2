# Welcome to the EreshCalcs2 Wiki!

## What is this?
This wiki is to help document how to use the new, revamped calculation command with Ereshbot. 
Currently, this command is `/calc2`.
Please note that at the time of writing, this command is still not available for public use.
## I already know how to use the original EreshBot calc command. Should I still read this?
That depends. If you don't care about the new features, then probably not. Everything that you could do with the old 
command can be done in the exact same way with the new command, except for the fact that the servant name now has to 
be one word (i.e. from "Arjuna Alter" to "ArjunaAlter") and that everything goes in the same box now.
For example:

**Old Command**:<br>
`/calc servant:` Arjuna Alter `string:` ce2400 n80 a30 p50 m20 saber hp1000
<br>**New Command**:<br>
`/calc2 string:` ArjunaAlter ce2400 n80 a30 p50 m20 saber hp1000

With that said, the new command is much, much more powerful. If you'd like to take advantage of all the new 
features and capabilities it now offers, you should definitely continue on reading.
## What are the main differences between the old and new versions? Why was the command rewritten?
The major difference between the two is that the old version was written to calculate one card on one enemy at a time,
whereas the new version can calculate multiple cards on multiple enemies at once.
<br>

This means that with the new version of calcs, you could simulate a whole command chain, a noble phantasm 
that hits a wave of enemies all with different debuffs, or even an entire three turn looping comp all from within 
a single command.

That is not to say, however, that multi-calcs are the only new tricks up the revamped command's proverbial sleeve.
The new version of the command comes with a host of new arguments to use, critical star calculation support, 
and generally far more granular control over exactly what it is you want to calculate.