## Full Argument List

### Structure Arguments
Used for setting up the structure of the calculation. How many enemies, which card 
hits who, etc.
<br>
<details>
  <summary><b><img src="./images/icons/cards.png" alt="Card Icon" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> Card</b></summary>
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
  <summary><b><img src="./images/icons/enemies_light.png" alt="Enemy Icon" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> Enemy</b></summary>
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
  <summary><b><img src="./images/icons/enemies_light.png" alt="Enemy Icon" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> E</b></summary>
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
  <summary><b><img src="./images/icons/enemies_dark.png" alt="Wave Icon" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> Wave</b></summary>
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
<br>
This would calculate Ereshkigal's Noble Phantasm against two enemies. When hitting both 
enemies, the Noble Phantasm would have 30% Card Up.
<br><br>
<code>/calc2 string: Ereshkigal npnp nwave1 nwave2 wave1 m30 wave2 m60 card1 w1 card2 w2</code>
<br>
This would calculate two Noble Phantasms from Ereshkigal. The first Noble Phantasm would only hit <code>wave1</code>,
and would have 30% Card Up. The second Noble Phantasm would only hit <code>wave2</code>, and would have 60% Card Up.
</details>
<details>
  <summary><b><img src="./images/icons/enemies_dark.png" alt="Wave Icon" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> NewWave / NWave</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>newwave<br>nwave</td>
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
For example, say that you use <code>nwave3</code> with a <code>wavesize</code> of the default 
3. If each wave is 3 enemies, that would mean a third wave would contain enemies 7, 8, and 9.
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
<br>
This would calculate Ereshkigal's Noble Phantasm against a wave of 3 enemies. When hitting any of the enemies, 
the Noble Phantasm would have 30% Card Up.

</details>
<details>
  <summary><b><img src="./images/icons/enemies_dark.png" alt="Wave Icon" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> W</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>w</td>
    <td>✔️</td>
    <td>❌</td>
    <td>N/A</td>
    <td>N/A</td>
</tr>
</table>
Used for targeting waves with a card. If provided after a card, the card will only hit
the specified wave. For an AoE Noble Phantasm, this means that it will hit all enemies in the wave.
For a normal card, it will hit the first enemy in the wave.
<br><br>
The <code>w</code> argument can only be used if provided after first explicitly switching to a card.
<br><br>
If an invalid wave is provided, the argument will be ignored. Ex. if there are only 2 waves, 
<code>w3</code> will be ignored.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal nwave1 nwave2 card1 w2</code>
<br>
This would calculate Ereshkigal's Noble Phantasm against <code>wave2</code> of enemies. Two full waves 
are defined using <code>nwave</code>, and since the Phantasm is AoE, it will hit 
<code>enemy4</code>, <code>enemy5</code>, and <code>enemy6</code>.
<br><br>
<code>/calc2 string: Ereshkigal nwave1 nwave2 buster card1 w2</code>
<br>
This would calculate Ereshkigal's Buster card against <code>enemy4</code>. This is because two waves of 3 enemies 
are defined using <code>nwave</code>, and the buster card will only hit the first enemy of <code>wave2</code> when 
using <code>w2</code> as a target. The first enemy of <code>wave2</code> is <code>enemy4</code>.
<br><br>
</details>
<details>
<summary><b><img src="./images/icons/enemies_dark.png" alt="Wave Icon" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> WaveSize</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>wavesize</td>
    <td>✔️ (1-6)</td>
    <td>❌</td>
    <td>N/A</td>
    <td>N/A</td>
</tr>
</table>
Used to specify the number of enemies per wave, 1-6. In practice, unless you really know what you're doing and 
why you're doing it, this should <b>only</b> ever be used for battles with 6 enemy waves.
<br><br>
Note that this argument neither creates enemies nor waves. It is only used to indicate how many enemies should be 
allowed in a wave, and consequently how to split the enemies already provided.
<br><br>
By default, <code>/calc2 string: Ereshkigal enemy1 enemy4</code> would create two waves with one enemy each.
If you were to specify <code>wavesize4</code> however, it would create one wave with two enemies.
<br><br>
Please note that <code>wavesize</code> is global. You cannot specify a different <code>wavesize</code> 
for different waves. With that said, you don't need to. You can still make a three enemy wave even if 
<code>wavesize</code> is 6 by simply manually creating the enemies.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal wavesize6 nwave1</code>
<br>
This would set the number of enemies per wave to 6 and create one wave of 6 enemies.
<br><br>
<code>/calc2 string: Ereshkigal wavesize6 nwave1 enemy7 enemy8 enemy9</code>
<br>
This would create one wave of 6 enemies (<code>nwave1</code>) and a second wave of three enemies 
(<code>enemy7 enemy8 enemy9</code>).
<br><br>
<code>/calc2 string: Ereshkigal wavesize6 enemy1 enemy2 enemy3 nwave2</code>
<br>
This would create one wave of three enemies (<code>enemy1 enemy2 enemy3</code>) and a second wave
of 6 enemies (<code>nwave2</code>). Note that the wave of 6 enemies will begin with <code>enemy7</code> and end with 
<code>enemy12,</code> as <code>wavesize</code> is 6 so any enemies prior to 7 would be part of 
<code>wave1</code> and thus not a new wave.
</details>
<details>
  <summary><b>🎲 RNG / Rand / Random</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>rng<br>rand<br>random</td>
    <td>✔️</td>
    <td>️️✔️</td>
    <td>N/A</td>
    <td>Ignore</td>
</tr>
</table>
Used to provide a custom RNG value as opposed to the default range of 
<code>0.9</code>, <code>1.0</code>, and <code>1.099</code>. Note that only one custom RNG value 
can be provided. Subsequent values will be ignored.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal rng1.077</code>
<br>
This would calculate Ereshkigal's Noble Phantasm with an RNG value of <code>1.077</code>.
<br><br>
<code>/calc2 string: Ereshkigal bb rng1.077</code>
<br>
This would calculate two of Ereshkigal's Buster Cards, each with an RNG value of <code>1.077</code>.
</details>

### Card Arguments
Used to tell EreshBot which cards to calculate.
<br>
<details>
  <summary><b><img src="./images/cards/buster.png" alt="Buster Icon" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> Buster / B</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>buster<br>b</td>
    <td>❌</td>
    <td>❌</td>
    <td>N/A</td>
    <td>N/A</td>
</tr>
</table>
Used to tell EreshBot to calculate a Buster card.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calcs2 string: Ereshkigal buster</code>
<br>
This would calculate one Buster card from Ereshkigal.
<br><br>
<code>/calcs2 string: Ereshkigal buster buster</code>
<br>
This would calculate two Buster cards from Ereshkigal.
<br><br>
<code>/calcs2 string: Ereshkigal b</code>
<br>
This would calculate one Buster card from Ereshkigal.
<br><br>
<code>/calcs2 string: Ereshkigal bb</code>
<br>
This would calculate two Buster cards from Ereshkigal.
</details>
<details>
  <summary><b><img src="./images/cards/arts.png" alt="Arts Icon" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> Arts / A</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>arts<br>a</td>
    <td>❌</td>
    <td>❌</td>
    <td>N/A</td>
    <td>N/A</td>
</tr>
</table>
Used to tell EreshBot to calculate an Arts card.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calcs2 string: Ereshkigal arts</code>
<br>
This would calculate one Arts card from Ereshkigal.
<br><br>
<code>/calcs2 string: Ereshkigal arts arts</code>
<br>
This would calculate two Arts cards from Ereshkigal.
<br><br>
<code>/calcs2 string: Ereshkigal a</code>
<br>
This would calculate one Arts card from Ereshkigal.
<br><br>
<code>/calcs2 string: Ereshkigal aa</code>
<br>
This would calculate two Arts cards from Ereshkigal.
</details>
<details>
  <summary><b><img src="./images/cards/quick.png" alt="Quick Icon" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> Quick / Q</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>quick<br>q</td>
    <td>❌</td>
    <td>❌</td>
    <td>N/A</td>
    <td>N/A</td>
</tr>
</table>
Used to tell EreshBot to calculate a Quick card.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calcs2 string: Ereshkigal quick</code>
<br>
This would calculate one Quick card from Ereshkigal.
<br><br>    
<code>/calcs2 string: Ereshkigal quick quick</code>
<br>
This would calculate two Quick cards from Ereshkigal.
<br><br>
<code>/calcs2 string: Ereshkigal q</code>
<br>
This would calculate one Quick card from Ereshkigal.
<br><br>
<code>/calcs2 string: Ereshkigal qq</code>
<br>
This would calculate two Quick cards from Ereshkigal.
</details>
<details>
  <summary><b><img src="./images/cards/extra.png" alt="Extra Icon" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> Extra / E</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>extra<br>e</td>
    <td>❌</td>
    <td>❌</td>
    <td>N/A</td>
    <td>N/A</td>
</tr>
</table>
Used to tell EreshBot to calculate an Extra card.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calcs2 string: Ereshkigal extra</code>
<br>
This would calculate one Extra card from Ereshkigal.
<br><br>
<code>/calcs2 string: Ereshkigal extra extra</code>
<br>
This would calculate two Extra cards from Ereshkigal.
<br><br>
<code>/calcs2 string: Ereshkigal e</code>
<br>
This would calculate one Extra card from Ereshkigal.
<br><br>
<code>/calcs2 string: Ereshkigal ee</code>
<br>
This would calculate two Extra cards from Ereshkigal.
</details>
<details>
  <summary><b><img src="./images/cards/np.png" alt="NP Icon" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> Noble / NP / N</b>
</summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>noble<br>np<br>n</td>
    <td>❌</td>
    <td>❌</td>
    <td>N/A</td>
    <td>N/A</td>
</tr>
</table>
Used to tell EreshBot to calculate a Noble Phantasm card.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calcs2 string: Ereshkigal np</code>
<br>
This would calculate one Noble Phantasm card from Ereshkigal.
<br><br>
<code>/calcs2 string: Ereshkigal npnp</code>
<br>
This would calculate two Noble Phantasm cards from Ereshkigal.
<br><br>
<code>/calcs2 string: Ereshkigal n</code>
<br>
This would calculate one Noble Phantasm card from Ereshkigal.
<br><br>
<code>/calcs2 string: Ereshkigal nn</code>
<br>
This would calculate two Noble Phantasm cards from Ereshkigal.
</details>
<details>
  <summary><b><img src="./images/cards/card_bg_blank.png" alt="NP Icon" style="width: 16px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> X</b>
</summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>x</td>
    <td>❌</td>
    <td>❌</td>
    <td>N/A</td>
    <td>N/A</td>
</tr>
</table>
Used to tell EreshBot to calculate skip a card while including it within a chain.
Useful for cases such as <code>/calc2 string: Ereshkigal bxb</code> where you still want
the third card to be in position 3, even if you aren't calculating a second card.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calcs2 string: Ereshkigal bxb</code>
<br>
This would calculate one two Buster cards from Ereshkigal, with the first card in position 1 and the second card
in position 3.
</details>
<b>☆ Important Note:</b>
<br>
The <code>np</code>, <code>n</code>, and <code>e</code> arguments do different things depending on whether or not 
you include a number with them.
<details>
<summary>More Details</summary>
<code>np#</code>: Sets NP level.
<br>
<code>np</code>: Card argument for NP.
<hr style="width: 200px; margin: 5px">
<code>n#</code>: Sets NP damage.
<br>
<code>n</code>: Card argument for NP.
<hr style="width: 200px; margin: 5px">
<code>e#</code>: Sets target enemy for a card.
<br>
<code>e</code>: Card argument for Extra.
<br>
</details>

### Positional Arguments
Used to tell EreshBot what position a card should be in. Useful when you want to calculate 
a single card without providing a full chain. Position args do not affect cards already in chains.
<br>
<details>
  <summary><b>First</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>first</td>
    <td>❌</td>
    <td>❌</td>
    <td>E>C>W>G</td>
    <td>Replace</td>
</tr>
</table>
Used to indicate that a given card should be in position 1. Using this argument will automatically
apply the first card bonus for the card type.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calcs2 string: Ereshkigal buster first</code>
<br>
This would calculate one of Ereshkigal's Buster cards in position 1.
</details>
<details>
  <summary><b>Second</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>second</td>
    <td>❌</td>
    <td>❌</td>
    <td>E>C>W>G</td>
    <td>Replace</td>
</tr>
</table>
Used to indicate that a given card should be in position 2.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calcs2 string: Ereshkigal buster second</code>
<br>
This would calculate one of Ereshkigal's Buster cards in position 2.
</details>
<details>
  <summary><b>Third</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>third</td>
    <td>❌</td>
    <td>❌</td>
    <td>E>C>W>G</td>
    <td>Replace</td>
</tr>
</table>
Used to indicate that a given card should be in position 3.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calcs2 string: Ereshkigal buster third</code>
<br>
This would calculate one of Ereshkigal's Buster cards in position 3.
</details>


### Servant Attribute Arguments
Used to indicate the specifics of your servant, such as NP level, CE Attack, etc.
<br>
<details>
  <summary><b>Level / Lvl / Lv / L</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>level<br>lvl<br>lv<br>l</td>
    <td>❌</td>
    <td>❌</td>
    <td>N/A</td>
    <td>Replace</td>
</tr>
</table>
Used to indicate the level of your servant. Servant's base attack is automatically set based on level.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calcs2 string: Ereshkigal lv50</code>
<br>
This would calculate Ereshkigal's Noble Phantasm with an attack stat based on Ereshkigal's attack at level 50.
</details>