## Full Argument List

### Structure Arguments
Utilized for setting up the structure of the calculation. How many enemies, which card 
hits who, etc.

<details>
  <summary><b>Card</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>card</td>
    <td>✔️</td>
    <td>❌</td>
    <td>N/A</td>
    <td>N/A</td>
</tr>
</table>
All arguments following the card argument will apply only to the specified card until a new card, enemy, or wave
arg is specified. 
The card argument does not define new cards. If you use <code>card6</code> when there are only 5 cards, 
<code>card6</code> and all arguments that would apply to <code>card6</code> will be treated as invalid.
<br><br>
Utilizing <code>card0</code> will return you to the global scope.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal card1 a30 m30 n50</code>
<br>
This would calculate Ereshkigal's Noble Phantasm, and that card would have 30% ATK Up, 30% Card Up, 
and 50% NP Damage Up.
<br><br>
<code>/calc2 string: Ereshkigal bnqe card1 a30 m30 n50 card2 a20 d30 m70</code>
<br>
This would calculate a Buster➝NP➝Quick➝Extra chain from Ereshkigal. The Buster card would have 
30% ATK Up, 30% Card Up, and 50% NP Damage Up. The Quick card would have 20% ATK Up, 30% Card Up, and 70% NP Damage Up.
</details>
<details>
  <summary><b>Enemy</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>enemy</td>
    <td>✔️</td>
    <td>❌</td>
    <td>N/A</td>
    <td>N/A</td>
</tr>
</table>
All arguments following the enemy argument will apply only to the specified enemy until a new card, enemy, or wave
is specified. 
The enemy argument also defines new enemies. If you use <code>enemy3</code> when there are only 2 enemies, 
a new enemy in position 3 will be created.
<br><br>
Utilizing <code>enemy0</code> will return you to the global scope.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal enemy1 saber hp1000</code>
<br>
This would calculate Ereshkigal's Noble Phantasm against one saber enemy with 1000 HP.
<br><br>
<code>/calc2 string: Ereshkigal enemy1 saber hp1000 enemy2 berserker hp5000</code>
<br>
This would calculate Ereshkigal's Noble Phantasm against one saber enemy with 1000 HP and one 
berserker enemy with 5000 HP. Note that as Ereshkigal's Noble Phantasm is AoE, it would hit both by default.
<br><br>
<code>/calc2 string: Ereshkigal enemy1 m40 d-30 enemy2 m60 d-20</code>
<br>
This would calculate Ereshkigal's Noble Phantasm against two enemies. When hitting the first enemy, 
the Noble Phantasm will have 40% Card Up and 30% Defense Down. When hitting the second enemy, 
the Noble Phantasm will have 60% Card Up and 20% Defense Down.
<br><br>
<code>/calc2 string: Ereshkigal buster enemy1 m40 d-30 enemy2 m60 d-20</code>
<br>
This would calculate a Buster card from Ereshkigal. Two enemies are specified, but since normal 
cards can only hit one enemy, it would only hit <code>enemy1</code>. The Buster card would have
40% Card Up and 30% Defense Down.
</details>
<details>
  <summary><b>E</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>e</td>
    <td>✔️</td>
    <td>❌</td>
    <td>N/A</td>
    <td>N/A</td>
</tr>
</table>
Used for targeting enemies with a card. If provided after a card, the card will only hit
the specified enemy. For AoE Noble Phantasms, multiple <code>e</code> args can be specified.
<br><br>
The <code>e</code> argument can only be used if provided after first explicitly switching to a card.
<br><br>
If an invalid enemy is provided, the argument will be ignored. Ex. if there are only 2 enemies, 
<code>e3</code> will be ignored.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal nwave1 card1 e1</code>
<br>
This would calculate Ereshkigal's Noble Phantasm against a wave defined with 3 enemies, but 
the Noble Phantasm would only actually hit <code>enemy1</code>.
<br><br>
<code>/calc2 string: Ereshkigal bqa nwave1 card1 e1 card2 e2 card3 e3</code>
<br>
This would calculate a Buster➝Quick➝Arts chain from Ereshkigal against a wave defined with 3 enemies.
The Buster card would hit <code>enemy1</code>, the Quick card would hit <code>enemy2</code>, and 
the Arts card would hit <code>enemy3</code>.
<br><br>
<code>/calc2 string: Ereshkigal npbb enemy1 enemy2 card2 e2 card3 e2</code>
<br>
This would calculate an NP➝Buster➝Buster chain from Ereshkigal against two enemies.
The Noble Phantasm will hit both enemies, but the Buster cards will only hit <code>enemy2</code>.
<br><br>
<code>/calc2 string: Ereshkigal nwave1 card1 e1 e2</code>
<br>
This would calculate Ereshkigal's Noble Phantasm against a wave defined with 3 enemies, but the 
Noble Phantasm would only hit <code>enemy1</code> and <code>enemy2</code>.
</details>
<details>
  <summary><b>Wave</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>wave</td>
    <td>✔️</td>
    <td>❌</td>
    <td>N/A</td>
    <td>N/A</td>
</tr>
</table>
All arguments following the wa argument will apply only to the specified wave until a new card, enemy, or wave 
arg is specified. 
<br>
The wave argument does not define new waves. If you use <code>wave2</code> when there is only one wave, 
<code>wave2</code> and all arguments that would apply to <code>wave2</code> will be treated as invalid.
<br><br>
Waves are automatically generated based on the number of enemies and the value of <code>wavesize</code> (3 by default).
In the calc <code>/calc2 string: Ereshkigal enemy1 enemy2 enemy3 enemy4</code>, <code>wave1</code> and 
<code>wave2</code> would be valid, with <code>wave1</code> containing enemies 1-3 and <code>wave2</code> 
containing enemy 4.
<br><br>
Utilizing <code>wave0</code> will return you to the general scope.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal enemy1 enemy2 wave1 m30</code>

</details>
<details>
  <summary><b>NewWave</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>newwave, nwave</td>
    <td>✔️</td>
    <td>❌</td>
    <td>N/A</td>
    <td>N/A</td>
</tr>
</table>
The newwave argument is used to define and switch to entire waves at once. It is equivalent to specifying
<code>enemy#</code> for each enemy that would be in a given wave, followed by <code>wave#</code> for the 
corresponding wave.
<br><br>
For example, say that you use <code>nwave3</code>, and your <code>wavesize</code> is the default 
of 3. If each wave is 3 enemies, that would mean a third wave would contain enemies 7, 8, and 9.
In this scenario, <code>nwave3</code> would be equivalent to <code>enemy7 enemy8 enemy9 wave3</code>.
<br><br>
In the scenario that you specify an already existing wave, <code>nwave</code> will fill out 
the remaining enemies in that wave until it has the same number of enemies as 
<code>wavesize</code>.
<br><br>
Utilizing <code>nwave0</code> will return you to the general scope.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal nwave1 m30</code>

</details>