## Basic Input Syntax
The fundamental syntax for a calculation command is as follows:

<span style="color: #0083af;font-weight:bold"> /calc2 </span>
<span style="color: #00a82f;font-weight:bold"> string: </span>
<span style="color: #b70000;font-weight:bold"> servant </span>
<span style="color: #c97c00;font-weight:bold"> arguments </span>
<br>
As you may have seen in the [basics](basics.md) page, once you have selected the 
<span style="color: #0083AFFF;font-weight:bold"> /calc2</span> command, 
the <span style="color: #00A82FFF;font-weight:bold"> string:</span> box will automatically appear as well. 
All you will be responsible for typing after you have selected the command are the 
<span style="color: #B70000FF;font-weight:bold"> servant</span>
and the command <span style="color: #C97C00FF;font-weight:bold"> arguments</span>.

<hr>
<h5 style="color:#B70000FF">The Servant Argument</h5>
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
<h5 style="color:#C97C00FF">The Other Arguments</h5>
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
<h5>Basic Input Summary</h5>

With all of that in mind, let's try to put it together. Say you wanted to calculate for 
<img width="20" alt="Ereshkigal" src="https://static.atlasacademy.io/JP/Faces/f_3032000.png">
[Ereshkigal](https://apps.atlasacademy.io/db/JP/servant/196)
with a 20% attack buff and 50% buster buff. How do you think you might do that?

You'd do: 
<span style="color: #0083AFFF;font-weight:bold"> /calc2 </span>
<span style="color: #00A82FFF;font-weight:bold"> string: </span>
<span style="color: #B70000FF;font-weight:bold"> Ereshkigal </span>
<span style="color: #C97C00FF;font-weight:bold"> a20 bm50 </span>

## Multi-Calc Input Syntax
::: warning
This section assumes that you
:::

The servant argument aside, EreshBot calculation arguments can essentially be broken down into three distinct types.
The first type are those that are used to specify the structure of the calculation. This includes args like `enemy` or 
`card`. The second type are those used to specify a card or card chain. This includes args like `buster` or `arts`.
Finally, the third type are those that are used to specify the specifics of your calculation, such as `level`, `fou`,
`atk` or `def`.

This section will focus on how to use the first two types of arguments.

The full list of structure arguments is as follows:
 <table>
  <tr>
    <th>Argument</th>
    <th>Effect</th>
    <th>Example</th>
  </tr>
  <tr>
    <td>card#</td>
    <td>Defines and/or switches to a card.</td>
    <td>card1</td>
  </tr>
  <tr>
    <td>enemy#</td>
    <td>Defines and/or switches to an enemy.</td>
    <td>enemy1</td>
  </tr>
  <tr>
    <td>e#</td>
    <td>Used for targeting enemies with cards.</td>
    <td>e1</td>
  </tr>
  <tr>
    <td>wave#</td>
    <td>Switches to a wave.</td>
    <td>wave1</td>
  </tr>
  <tr>
    <td>nwave#</td>
    <td>Defines and/or switches to a wave. Also automatically fills the wave.</td>
    <td>nwave1</td>
  </tr>
  <tr>
    <td>rng#</td>
    <td>Applies a specified rng to the entire calculation.</td>
    <td>rng1.0</td>
  </tr>
</table> 
The full list of card chain arguments are as follows:
 <table>
  <tr>
    <th>Argument</th>
    <th>Effect</th>
    <th>Example</th>
  </tr>
  <tr>
    <td>b, buster</td>
    <td>Defines a buster card.</td>
    <td>buster</td>
  </tr>
  <tr>
    <td>a, arts</td>
    <td>Defines an arts card.</td>
    <td>arts</td>
  </tr>
  <tr>
    <td>q, quick</td>
    <td>Defines a quick card.</td>
    <td>quick</td>
  </tr>
  <tr>
    <td>e, extra</td>
    <td>Defines an extra card.</td>
    <td>extra</td>
  </tr>
  <tr>
    <td>n, np, noble</td>
    <td>Defines a noble phantasm card.</td>
    <td>noble</td>
  </tr>
  <tr>
    <td>x</td>
    <td>Defines an empty card.</td>
    <td>x</td>
  </tr>
</table>
* Note: Some arguments, such as `np` and `n`, have other functions when supplied with a number (ex `np5`). Make sure
that you do **not** supply a number to use them as a card chain argument.

The most important thing to remember when dealing with multi calcs is that 
<span style="color: #B70000FF;font-weight:bold;border-bottom: 2px solid">
the order of your arguments matters
</span>.

With that in mind, let's go through 
