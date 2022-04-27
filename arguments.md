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
<code>/calc2 string: Ereshkigal buster</code>
<br>
This would calculate one Buster card from Ereshkigal.
<br><br>
<code>/calc2 string: Ereshkigal buster buster</code>
<br>
This would calculate two Buster cards from Ereshkigal.
<br><br>
<code>/calc2 string: Ereshkigal b</code>
<br>
This would calculate one Buster card from Ereshkigal.
<br><br>
<code>/calc2 string: Ereshkigal bb</code>
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
<code>/calc2 string: Ereshkigal arts</code>
<br>
This would calculate one Arts card from Ereshkigal.
<br><br>
<code>/calc2 string: Ereshkigal arts arts</code>
<br>
This would calculate two Arts cards from Ereshkigal.
<br><br>
<code>/calc2 string: Ereshkigal a</code>
<br>
This would calculate one Arts card from Ereshkigal.
<br><br>
<code>/calc2 string: Ereshkigal aa</code>
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
<code>/calc2 string: Ereshkigal quick</code>
<br>
This would calculate one Quick card from Ereshkigal.
<br><br>    
<code>/calc2 string: Ereshkigal quick quick</code>
<br>
This would calculate two Quick cards from Ereshkigal.
<br><br>
<code>/calc2 string: Ereshkigal q</code>
<br>
This would calculate one Quick card from Ereshkigal.
<br><br>
<code>/calc2 string: Ereshkigal qq</code>
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
<code>/calc2 string: Ereshkigal extra</code>
<br>
This would calculate one Extra card from Ereshkigal.
<br><br>
<code>/calc2 string: Ereshkigal extra extra</code>
<br>
This would calculate two Extra cards from Ereshkigal.
<br><br>
<code>/calc2 string: Ereshkigal e</code>
<br>
This would calculate one Extra card from Ereshkigal.
<br><br>
<code>/calc2 string: Ereshkigal ee</code>
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
<code>/calc2 string: Ereshkigal np</code>
<br>
This would calculate one Noble Phantasm card from Ereshkigal.
<br><br>
<code>/calc2 string: Ereshkigal npnp</code>
<br>
This would calculate two Noble Phantasm cards from Ereshkigal.
<br><br>
<code>/calc2 string: Ereshkigal n</code>
<br>
This would calculate one Noble Phantasm card from Ereshkigal.
<br><br>
<code>/calc2 string: Ereshkigal nn</code>
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
<code>/calc2 string: Ereshkigal bxb</code>
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

### Servant Attribute Arguments
Used to indicate the specifics of your servant, such as NP level, CE Attack, etc.
<br>
<details>
  <summary><b><img src="./images/icons/level.png" alt="Level" style="width: 19px; height:auto; border:none; padding:0; margin:0"> Level / Lvl / Lv / L</b></summary>
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
    <td>✔️</td>
    <td>❌</td>
    <td>N/A</td>
    <td>Replace</td>
</tr>
</table>
Used to indicate the level of your servant. Servant's base attack is automatically set based on level.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal lv50</code>
<br>
This would calculate Ereshkigal's Noble Phantasm with an attack stat based on Ereshkigal's attack at level 50.
</details>
<details>
  <summary><b><img src="./images/cards/np.png" alt="NP Icon" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> NPLevel / NP</b>
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
    <td>nplevel<br>np</td>
    <td>✔️</td>
    <td>❌</td>
    <td>N/A</td>
    <td>Replace</td>
</tr>
</table>
Used to tell EreshBot what the NP level of your servant is.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal np3</code>
<br>
This would calculate a Noble Phantasm from Ereshkigal at NP level 3.
</details>
<details>
  <summary><b><img src="./images/cards/np.png" alt="NP Icon" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> Strengthen / STR / Lewd / Interlude / SetNP / SNP</b>
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
    <td>np</td>
    <td>✔️</td>
    <td>❌</td>
    <td>N/A</td>
    <td>Replace</td>
</tr>
</table>
Used to tell EreshBot what the strengthening status of your servant is.
<br>
This argument is also used to switch between Noble Phantasms for servants like Space Ishtar 
or Fairy Knight Lancelot.
<br>
Noble Phantasms are numbered starting from 0 in the same order they appear in <code>/np Servant</code>.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal str1</code>
<br>
This would calculate Ereshkigal's upgraded Noble Phantasm.
<br><br>
<code>/calc2 string: Bride str0</code>
<br>
This would calculate Nero Bride's un-upgraded Noble Phantasm.
<br><br>
<code>/calc2 string: Vlad str2</code>
<br>
This would calculate Vlad III's Noble Phantasm with its <i>second</i> strengthening.
<br><br>
<code>/calc2 string: Spishtar str1</code>
<br>
This would calculate Space Ishtar's Buster Noble Phantasm.
</details>
<details>
  <summary><b><img src="./images/icons/fou.png" alt="Fou" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> Fou / F</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>fou<br>f</td>
    <td>✔️</td>
    <td>❌</td>
    <td>E>C>W>G</td>
    <td>Replace</td>
</tr>
</table>
Used to indicate how much additional ATK stat your servant should have from ATK fous.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal fou2000</code>
<br>
This would calculate Ereshkigal's Noble Phantasm with 2,000 additional ATK from fous.
</details>
<details>
  <summary><b><img src="./images/icons/2000.png" alt="Paw" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> Paw / FouPaw / Print / Footprint</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>paw<br>foupaw<br>print<br>footprint</td>
    <td>✔️</td>
    <td>❌</td>
    <td>E>C>W>G</td>
    <td>Replace</td>
</tr>
</table>
Used to indicate how much additional ATK stat your servant should have from fou paws.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal buster paw250</code>
<br>
This would calculate Ereshkigal's Buster card with 250 additional ATK from fou paws.
</details>
<details>
  <summary><b><img src="./images/icons/ce.png" alt="CE" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> CE / C</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>ce<br>c</td>
    <td>✔️</td>
    <td>❌</td>
    <td>E>C>W>G</td>
    <td>Replace</td>
</tr>
</table>
Used to indicate how much additional ATK stat your servant should have from a craft essence.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal ce2000</code>
<br>
This would calculate Ereshkigal's Noble Phantasm with 2,000 additional ATK from a craft essence.
</details>
<details>
  <summary><b><img src="./images/icons/img_list_atk.png" alt="ATK" style="width: 23px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> TotalAttack / TA</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>totalattack<br>ta</td>
    <td>✔️</td>
    <td>❌</td>
    <td>E>C>W>G</td>
    <td>Replace</td>
</tr>
</table>
Used to specify the total attack stat of your servant. This will override all other sources of ATK.
<br>
In other words, if you specify total attack, then fou, ce, paw, and the servant's base attack will all be 
ignored and replaced by your specified total attack.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal ta11525</code>
<br>
This would calculate Ereshkigal's Noble Phantasm with 11,525 ATK stat.
</details>

### Card Attribute Arguments
Used to specify things like buster first bonus, whether a card critically hits, etc.
<br>
<details>
  <summary><b>1️⃣ First</b></summary>
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
Note that this argument will not affect cards in card chains.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal buster first</code>
<br>
This would calculate one of Ereshkigal's Buster cards in position 1.
</details>
<details>
  <summary><b>2️⃣ Second</b></summary>
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
Note that this argument will not affect cards in card chains.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal buster second</code>
<br>
This would calculate one of Ereshkigal's Buster cards in position 2.
</details>
<details>
  <summary><b>3️⃣ Third</b></summary>
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
Note that this argument will not affect cards in card chains.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal buster third</code>
<br>
This would calculate one of Ereshkigal's Buster cards in position 3.
</details>
<details>
  <summary><b><img src="./images/cards/buster.png" alt="Buster" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> BusterFirst / BF</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>busterfirst<br>bf</td>
    <td>❌</td>
    <td>❌</td>
    <td>E>C>W>G</td>
    <td>Replace</td>
</tr>
</table>
This argument can be used to force buster first card bonus even in cases where a buster card is not 
first and/or you are calculating a single non-buster card.
<br>
Note that when calculating a single buster card or using a card chain that begins with a buster card,
this bonus is automatically applied.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal quick bf</code>
<br>
This would calculate a quick card from Ereshkigal with buster first bonus.
<br><br>
<code>/calc2 string Ereshkigal xqbe bf</code>
<br>
This would calculate an X→Quick→Buster→Extra card chain from Ereshkigal with buster first bonus.
This could be useful if the x card is a different servant's buster card.
</details>
<details>
  <summary><b><img src="./images/cards/arts.png" alt="Arts" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> ArtsFirst / AF</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>artsfirst<br>af</td>
    <td>❌</td>
    <td>❌</td>
    <td>E>C>W>G</td>
    <td>Replace</td>
</tr>
</table>
This argument can be used to force arts first card bonus even in cases where an arts card is not 
first and/or you are calculating a single non-arts card.
<br>
Note that when calculating a single arts card or using a card chain that begins with an arts card,
this bonus is automatically applied.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal quick af</code>
<br>
This would calculate a quick card from Ereshkigal with arts first bonus.
<br><br>
<code>/calc2 string Ereshkigal xqbe af</code>
<br>
This would calculate an X→Quick→Buster→Extra card chain from Ereshkigal with arts first bonus.
This could be useful if the x card is a different servant's arts card.
</details>
<details>
  <summary><b><img src="./images/cards/quick.png" alt="Quick" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> QuickFirst / QF</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>quickfirst<br>qf</td>
    <td>❌</td>
    <td>❌</td>
    <td>E>C>W>G</td>
    <td>Replace</td>
</tr>
</table>
This argument can be used to force quick first card bonus even in cases where a quick card is not 
first and/or you are calculating a single non-quick card.
<br>
Note that when calculating a single quick card or using a card chain that begins with a quick card,
this bonus is automatically applied.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal arts qf</code>
<br>
This would calculate an arts card from Ereshkigal with quick first bonus.
<br><br>
<code>/calc2 string Ereshkigal xabe qf</code>
<br>
This would calculate an X→Arts→Buster→Extra card chain from Ereshkigal with quick first bonus.
This could be useful if the x card is a different servant's quick card.
</details>
<details>
  <summary><b><img src="./images/cards/buster.png" alt="Buster" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> BusterChain / BC</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>busterchain<br>bc</td>
    <td>❌</td>
    <td>❌</td>
    <td>E>C>W>G</td>
    <td>Replace</td>
</tr>
</table>
This argument can be used to force a buster chain bonus even when calculating a single card.
<br>
Note that when calculating a buster card chain using card arguments, this is automatically applied.
<br>
Additionally, using this argument will automatically apply buster first.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal buster bc</code>
<br>
This would calculate a single Buster card from Ereshkigal as a part of a buster chain.
</details>
<details>
  <summary><b><img src="./images/cards/arts.png" alt="Arts" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> ArtsChain / AC</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>artschain<br>ac</td>
    <td>❌</td>
    <td>❌</td>
    <td>E>C>W>G</td>
    <td>Replace</td>
</tr>
</table>
This argument can be used to force an arts chain bonus even when calculating a single card.
<br>
Note that when calculating an arts card chain using card arguments, this is automatically applied.
<br>
Additionally, using this chain argument will automatically apply arts first.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal arts ac</code>
<br>
This would calculate a single Arts card from Ereshkigal as a part of an arts chain.
</details>
<details>
  <summary><b><img src="./images/cards/quick.png" alt="Quick" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> QuickChain / QC</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>quickchain<br>qc</td>
    <td>❌</td>
    <td>❌</td>
    <td>E>C>W>G</td>
    <td>Replace</td>
</tr>
</table>
This argument can be used to force a quick chain bonus even when calculating a single card.
<br>
Note that when calculating a quick card chain using card arguments, this is automatically applied.
<br>
Additionally, using this argument will automatically apply quick first.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal quick qc</code>
<br>
This would calculate a single Quick card from Ereshkigal as a part of a quick chain.
</details>
<details>
  <summary><b><img src="./images/cards/extra.png" alt="Extra" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> ExtraCardModifier / ECM</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>extracardmodifier<br>ecm</td>
    <td>✔️</td>
    <td>✔️</td>
    <td>E>C>W>G</td>
    <td>Replace</td>
</tr>
</table>
This argument can be used to set a custom extra card modifier. Note that this argument only impacts extra cards.
<br>
When calculating using card chains, the extra card modifier is automatically applied with the appropriate amount.
<br><br>
Note: This value is 1 by default, 2 if the extra card is part of a brave chain, and 3.5 if the extra card is
part of a color brave chain (ex. bbbe). Note that in FGO, generally you cannot use an extra card in any other scenario 
than as a part of a brave chain, so in practice this value should <b>always</b> be 2.0 or 3.5.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal extra ecm2</code>
<br>
This would calculate an extra card from Ereshkigal with an extra card modifier of 2.
<br><br>
<code>/calc2 string Ereshkigal extra ecm3.5</code>
<br>
This would calculate an extra card from Ereshkigal with an extra card modifier of 3.5.
</details>
<details>
  <summary><b><img src="./images/cards/buster.png" alt="Buster" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> NoBusterFirst / NoBF / No-BF</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>nobusterfirst<br>nobf<br>no-bf</td>
    <td>❌</td>
    <td>❌</td>
    <td>E>C>W>G</td>
    <td>Replace</td>
</tr>
</table>
This argument can be used to force remove the buster first card bonus even when calculating a single 
buster card or a card chain beginning with a buster card.
<br>
As far as I am aware, this is impossible for the player, but when calculating an enemy's cards, this can be applied.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal buster nobf</code>
<br>
This would calculate a single buster card from Ereshkigal without buster first bonus.
<br><br>
<code>/calc2 string Ereshkigal bbb bf</code>
<br>
This would calculate an Buster→Buster→Buster→Extra card chain from Ereshkigal without buster first bonus.
</details>
<details>
  <summary><b><img src="./images/icons/crit_dmg_up.png" alt="Quick" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> Critical / Crit</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>critical<br>crit</td>
    <td>❌</td>
    <td>❌</td>
    <td>E>C>W>G</td>
    <td>Replace</td>
</tr>
</table>
This argument indicates that a card is a critical hit.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal quick critical</code>
<br>
This would calculate a single Quick card from Ereshkigal, and that card would be a critical hit.
</details>
<details>
  <summary><b><img src="./images/cards/np.png" alt="NP" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> NPOverride / NPValue / NPV / NPO</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>npoverride<br>npvalue<br>npv<br>npo</td>
    <td>✔️</td>
    <td>✔️</td>
    <td>E>C>W>G</td>
    <td>Replace</td>
</tr>
</table>
This argument can be used to set a custom np multiplier. This can be used to calculate very new NP before EreshBot 
updates.
<br><br>
This corresponds to <code>npDamageMultiplier</code> in the damage formula.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal npv550</code>
<br>
This would calculate Ereshkigal's noble phantasm with a custom multiplier of 550%.
</details>
<details>
  <summary><b><img src="./images/icons/cards.png" alt="Cards" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> CardDamageVal / CDV / CardValue / CardMultiplierOverride / CMV</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>
    cardmultiplieroverride<br>cmv<br>cardvalue<br>cdv<br>carddamageval
    </td>
    <td>✔️</td>
    <td>✔️</td>
    <td>E>C>W>G</td>
    <td>Replace</td>
</tr>
</table>
This argument can be used to set a custom card multiplier. This can be used to manually set the value that 
would typically be set by the <code>first</code>, <code>second</code>, and <code>third</code> arguments. 
<br><br>
This corresponds to <code>cardDamageValue</code> in the damage formula.
<br><br>
Note that unlike the positional arguments, this argument <i>can</i> be used even on cards in chains.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal buster cmv1.8</code>
<br>
This would calculate Ereshkigal's Buster card with a custom multiplier of 180%.
</details>
<details>
  <summary><b><img src="./images/icons/cards.png" alt="Cards" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> CardRefundValue / CRV</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>cardrefundvalue<br>crv</td>
    <td>✔️</td>
    <td>✔️</td>
    <td>E>C>W>G</td>
    <td>Replace</td>
</tr>
</table>
This can be used to set a custom NP value for a card. Doing so manually sets the card's np value 
that is normally set automatically based on a card's position or by using the position arguments.
<br><br>
This corresponds to <code>cardNpValue</code> in the NP Generation formula.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal hp2250 quick crv1.5</code>
<br>
This would calculate a quick card from Ereshkigal with a refund value of 150%.
</details>
<details>
  <summary><b><img src="./images/icons/cards.png" alt="Cards" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> CardStarValue / CSV</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>cardstarvalue<br>csv</td>
    <td>✔️</td>
    <td>✔️</td>
    <td>E>C>W>G</td>
    <td>Replace</td>
</tr>
</table>
This can be used to set a custom star value for a card. Doing so manually sets the card's star value 
that is normally set automatically based on a card's position or by using the position arguments.
<br><br>
This corresponds to <code>cardStarValue</code> in the Star Generation formula.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal hp2250 buster csv0.15</code>
<br>
This would calculate a buster card from Ereshkigal with a refund value of 15%.
</details>

### Enemy Attribute Arguments
<details>
  <summary><b><img src="./images/icons/img_list_hp.png" alt="HP" style="width: 23px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> EnemyHP / HP</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>enemyhp<br>hp</td>
    <td>✔️</td>
    <td>❌</td>
    <td>E>C>W>G</td>
    <td>Replace</td>
</tr>
</table>
Used to set the HP of an enemy. This is required to calculate NP and Star Generation.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal hp20000</code>
<br>
This would calculate Ereshkigal's Noble Phantasm against an enemy with 20,000 HP.
<br><br>
<code>/calc2 string: Ereshkigal enemy1 hp20000 enemy2 hp15000</code>
<br>
This would calculate Ereshkigal's Noble Phantasm against an enemy with 20,000 HP and an enemy with 15,000 HP.
</details>
<details>
  <summary><b><img src="./images/icons/All_Gold.png" alt="Class Icon" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> [Any Class Name] (No Spaces)</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>
    saber<br>archer<br>lancer<br>
    rider<br>caster<br>assassin<br>
    berserker<br>zerk<br>zerker<br>shielder<br>ruler<br>
    alterego<br>ego<br>avenger<br>mooncancer<br>moon<br>cancer<br>
    foreigner<br>pretender<br>demongodpillar<br>
    beasti<br>beast1<br>beastii<br>beast2<br>
    beastiiir<br>beast3r<br>beastiiil<br>beast3l<br>
    beastiv<br>beast4<br>beastunknown<br>cccfinaleemiyaalter<br>
    </td>
    <td>❌</td>
    <td>❌</td>
    <td>E>C>W>G</td>
    <td>Replace</td>
</tr>
</table>
This argument can be used to set the class of an enemy. This automatically sets class advantage, 
enemy server mod (NP Gen), and enemy server rate (Star Gen).
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal saber</code>
<br>
This would calculate Ereshkigal's Noble Phantasm against a saber class enemy.
</details>
<details>
  <summary><b><img src="./images/icons/All_Gold.png" alt="Class Icon" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> ClassAdvantageOverride / CAO</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>
    classadvantageoverride<br>cao<br>
    </td>
    <td>✔️</td>
    <td>✔️</td>
    <td>E>C>W>G</td>
    <td>Replace</td>
</tr>
</table>
This argument can be used to manually set the class advantage override versus an enemy as opposed to using
the enemy class argument.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal cao2.0</code>
<br>
This would calculate Ereshkigal's Noble Phantasm with a 2x class advantage.
</details>
<details>
  <summary><b>天 Human / Man / Sky / Heaven / Earth / Star / Beast </b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>
    human<br>man<br>sky<br>heaven<br>earth<br>star<br>beast
    </td>
    <td>❌</td>
    <td>❌</td>
    <td>E>C>W>G</td>
    <td>Replace</td>
</tr>
</table>
This argument can be used to set the attribute of an enemy.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal earth</code>
<br>
This would calculate Ereshkigal's Noble Phantasm against an Earth attribute enemy.
</details>
<details>
  <summary><b><img src="./images/icons/np_gain_up.png" alt="NP" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> EnemyServerMod / ESM / SM</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>
    enemyservermod<br>esm<br>sm<br>
    </td>
    <td>✔️</td>
    <td>✔️</td>
    <td>E>C>W>G</td>
    <td>Replace</td>
</tr>
</table>
This argument can be used to manually set the server mod of an enemy.
<br><br>
This corresponds to <code>enemyServerMod</code> in the NP Generation formula.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal arts hp2250 esm1.2</code>
<br>
This would calculate Ereshkigal's arts card against an enemy with a server mod of 120%
</details>
<details>
  <summary><b><img src="./images/icons/star_gen_up.png" alt="Stars" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> EnemyServerRate / ESR / SR / SRR / ServerRate</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>
    enemyserverrate<br>esr<br>sr<br>srr<br>serverrate
    </td>
    <td>✔️</td>
    <td>✔️</td>
    <td>E>C>W>G</td>
    <td>Replace</td>
</tr>
</table>
This argument can be used to manually set the server rate of an enemy.
<br><br>
This corresponds to <code>serverRate</code> in the Star Generation formula.
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal quick hp2250 esr1</code>
<br>
This would calculate Ereshkigal's quick card against an enemy with a server rate of 100%
</details>

### Damage Buff Arguments
<details>
  <summary><b>
    <img src="./images/icons/buster_up.png" alt="Buster Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    <img src="./images/icons/arts_up.png" alt="Arts Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    <img src="./images/icons/quick_up.png" alt="Quick Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    <img src="./images/icons/buster_down.png" alt="Buster Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    <img src="./images/icons/arts_down.png" alt="Arts Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    <img src="./images/icons/quick_down.png" alt="Quick Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    <img src="./images/icons/buster_resist_up.png" alt="Buster Resist Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    <img src="./images/icons/arts_resist_up.png" alt="Arts Resist Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    <img src="./images/icons/quick_resist_up.png" alt="Quick Resist Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    <img src="./images/icons/buster_resist_down.png" alt="Buster Resist Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    <img src="./images/icons/arts_resist_down.png" alt="Arts Resist Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    <img src="./images/icons/quick_resist_down.png" alt="Quick Resist Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    CardMod / CM / M</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>
    cardmod<br>cm<br>m
    </td>
    <td>✔️</td>
    <td>✔️</td>
    <td>E>C>W>G</td>
    <td>Sum</td>
</tr>
</table>
Used to set cardmod. This argument is universal and applies to Buster, Arts, and Quick cards. It does <b>NOT</b>
apply to Extra cards.
<br><br>
Positive Values:
<br>
<img src="./images/icons/buster_up.png" alt="Buster Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
<img src="./images/icons/arts_up.png" alt="Arts Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
<img src="./images/icons/quick_up.png" alt="Quick Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
Card Up (Ex. Buster Card Up) 
<br>
<img src="./images/icons/buster_resist_down.png" alt="Buster Resist Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
<img src="./images/icons/arts_resist_down.png" alt="Arts Resist Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
<img src="./images/icons/quick_resist_down.png" alt="Quick Resist Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
Card Resist Down (Ex. Buster Card Resist Down)
<br><br>
Negative Values:
<br>
<img src="./images/icons/buster_down.png" alt="Buster Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
<img src="./images/icons/arts_down.png" alt="Arts Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
<img src="./images/icons/quick_down.png" alt="Quick Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
Card Down (Ex. Buster Card Down)
<br>
<img src="./images/icons/buster_resist_up.png" alt="Buster Resist Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
<img src="./images/icons/arts_resist_up.png" alt="Arts Resist Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
<img src="./images/icons/quick_resist_up.png" alt="Quick Resist Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
Card Resist Up (Ex. Buster Card Resist Up)
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal m30</code>
<br>
This would calculate Ereshkigal's Noble Phantasm with 30% Card Damage Up.
<br><br>
<code>/calc2 string: Ereshkigal m-30</code>
<br>
This would calculate Ereshkigal's Noble Phantasm with 30% Card Damage Down.
</details>
<details>
  <summary><b>
    <img src="./images/icons/buster_up.png" alt="Buster Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    <img src="./images/icons/buster_down.png" alt="Buster Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    <img src="./images/icons/buster_resist_up.png" alt="Buster Resist Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    <img src="./images/icons/buster_resist_down.png" alt="Buster Resist Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    BCardMod / BCM / BM</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>
    bcardmod<br>bcm<br>bm
    </td>
    <td>✔️</td>
    <td>✔️</td>
    <td>E>C>W>G</td>
    <td>Sum</td>
</tr>
</table>
Used to set buster specific cardmod. This argument will only apply to Buster cards.
<br><br>
Positive Values:
<br>
<img src="./images/icons/buster_up.png" alt="Buster Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
Buster Card Up
<br>
<img src="./images/icons/buster_resist_down.png" alt="Buster Resist Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
Buster Resist Down
<br><br>
Negative Values:
<br>
<img src="./images/icons/buster_down.png" alt="Buster Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
Buster Card Down
<br>
<img src="./images/icons/buster_resist_up.png" alt="Buster Resist Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
Buster Card Resist Up
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal buster bm30</code>
<br>
This would calculate Ereshkigal's Buster card with 30% Buster Damage Up.
<br><br>
<code>/calc2 string: Ereshkigal buster bm-30</code>
<br>
This would calculate Ereshkigal's Buster card 30% Buster Damage Down.
</details>
<details>
  <summary><b>
    <img src="./images/icons/quick_up.png" alt="Quick Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    <img src="./images/icons/quick_down.png" alt="Quick Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    <img src="./images/icons/quick_resist_up.png" alt="Quick Resist Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    <img src="./images/icons/quick_resist_down.png" alt="Quick Resist Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    QCardMod / QCM / QM</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>
    qcardmod<br>qcm<br>qm
    </td>
    <td>✔️</td>
    <td>✔️</td>
    <td>E>C>W>G</td>
    <td>Sum</td>
</tr>
</table>
Used to set quick specific cardmod. This argument will only apply to Quick cards.
<br><br>
Positive Values:
<br>
<img src="./images/icons/quick_up.png" alt="Quick Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
Quick Card Up
<br>
<img src="./images/icons/quick_resist_down.png" alt="Quick Resist Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
Quick Resist Down
<br><br>
Negative Values:
<br>
<img src="./images/icons/quick_down.png" alt="Quick Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
Quick Card Down
<br>
<img src="./images/icons/quick_resist_up.png" alt="Quick Resist Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
Quick Card Resist Up
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal quick qm30</code>
<br>
This would calculate Ereshkigal's Quick card with 30% Quick Damage Up.
<br><br>
<code>/calc2 string: Ereshkigal quick qm-30</code>
<br>
This would calculate Ereshkigal's Quick card 30% Quick Damage Down.
</details>
<details>
  <summary><b>
    <img src="./images/icons/arts_up.png" alt="Arts Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    <img src="./images/icons/arts_down.png" alt="Arts Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    <img src="./images/icons/arts_resist_up.png" alt="Arts Resist Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    <img src="./images/icons/arts_resist_down.png" alt="Arts Resist Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    ACardMod / ACM / AM</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>
    acardmod<br>acm<br>am
    </td>
    <td>✔️</td>
    <td>✔️</td>
    <td>E>C>W>G</td>
    <td>Sum</td>
</tr>
</table>
Used to set arts specific cardmod. This argument will only apply to Arts cards.
<br><br>
Positive Values:
<br>
<img src="./images/icons/arts_up.png" alt="Arts Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
Arts Card Up
<br>
<img src="./images/icons/arts_resist_down.png" alt="Arts Resist Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
Arts Resist Down
<br><br>
Negative Values:
<br>
<img src="./images/icons/arts_down.png" alt="Arts Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
Arts Card Down
<br>
<img src="./images/icons/arts_resist_up.png" alt="Arts Resist Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
Arts Card Resist Up
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal arts am30</code>
<br>
This would calculate Ereshkigal's Arts card with 30% Arts Damage Up.
<br><br>
<code>/calc2 string: Ereshkigal arts am-30</code>
<br>
This would calculate Ereshkigal's Arts card 30% Arts Damage Down.
</details>
<details>
  <summary><b>
    <img src="./images/icons/extra_up.png" alt="Extra Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    <img src="./images/icons/extra_down.png" alt="Extra Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    <img src="./images/icons/extra_res_up.png" alt="Extra Resist Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    <img src="./images/icons/extra_res_down.png" alt="Extra Resist Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
    ECardMod / ECM / EM</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>
    ecardmod<br>ecm<br>em
    </td>
    <td>✔️</td>
    <td>✔️</td>
    <td>E>C>W>G</td>
    <td>Sum</td>
</tr>
</table>
Used to set extra specific cardmod. This argument will only apply to Extra cards.
<br><br>
Positive Values:
<br>
<img src="./images/icons/extra_up.png" alt="Extra Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
Extra Card Up
<br>
<img src="./images/icons/extra_res_down.png" alt="Extra Resist Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
Extra Resist Down
<br><br>
Negative Values:
<br>
<img src="./images/icons/extra_down.png" alt="Extra Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
Extra Card Down
<br>
<img src="./images/icons/extra_res_up.png" alt="Extra Resist Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
Extra Card Resist Up
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal extra em30</code>
<br>
This would calculate Ereshkigal's Extra card with 30% Extra Damage Up.
<br><br>
<code>/calc2 string: Ereshkigal extra em-30</code>
<br>
This would calculate Ereshkigal's Extra card 30% Extra Damage Down.
</details>
<details>
  <summary><b>
    <img src="./images/icons/atk_up.png" alt="Atk Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub">
    <img src="./images/icons/atk_down.png" alt="Atk Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub">
    AtkMod / Attack / ATK / A</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>
    atkmod<br>attack<br>atk<br>a
    </td>
    <td>✔️</td>
    <td>✔️</td>
    <td>E>C>W>G</td>
    <td>Sum</td>
</tr>
</table>
Used to set attack mod for attack up buffs like Charisma.
<br><br>
Positive Values:
<br>
<img src="./images/icons/atk_up.png" alt="Atk Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
Attack Up
<br><br>
Negative Values:
<br>
<img src="./images/icons/atk_down.png" alt="Atk Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
Attack Down
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal a30</code>
<br>
This would calculate Ereshkigal's Noble Phantasm with 30% Attack Up.
<br><br>
<code>/calc2 string: Ereshkigal a-30</code>
<br>
This would calculate Ereshkigal's Noble Phantasm with 30% Attack Down.
</details>
<details>
  <summary><b>
    <img src="./images/icons/def_up.png" alt="Def Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub">
    <img src="./images/icons/def_down.png" alt="Def Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub">
    DefMod / Defence / Defense / Def / D</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>
    defmod<br>defence<br>defense<br>def<br>d
    </td>
    <td>✔️</td>
    <td>✔️</td>
    <td>E>C>W>G</td>
    <td>Sum</td>
</tr>
</table>
Used to set defense mod for defense up buffs. Note that defense UP will reduce your damage, and 
defense DOWN will increase your damage. So for Skadi's defense down skill, you'll want to use NEGATIVE 30.
<br><br>
Positive Values:
<br>
<img src="./images/icons/def_up.png" alt="Def Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
Defense Up
<br><br>
Negative Values:
<br>
<img src="./images/icons/def_down.png" alt="Def Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
Defense Down
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal d30</code>
<br>
This would calculate Ereshkigal's Noble Phantasm against an enemy with 30% defense up.
<br><br>
<code>/calc2 string: Ereshkigal d-30</code>
<br>
This would calculate Ereshkigal's Noble Phantasm against an enemy with 30% defense down.
</details>
<details>
  <summary><b>
    <img src="./images/icons/sp_atk_up.png" alt="Sp Atk Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub">
    <img src="./images/icons/sp_atk_down.png" alt="Sp Atk Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub">
    PowerMod / Power / PMod / P</b></summary>
 <table>
  <tr>
    <th>Arg</th>
    <th>Number?</th>
    <th>Decimals?</th>
    <th>Priority</th>
    <th>Duplicate</th>
  </tr>
  <tr>
    <td>
    powermod<br>power<br>pmod<br>p
    </td>
    <td>✔️</td>
    <td>✔️</td>
    <td>E>C>W>G</td>
    <td>Sum</td>
</tr>
</table>
Used to set power mod / special attack buffs. This is <b>NOT</b> for servants like Gilgamesh. This is for things 
like event damage bonuses or Musashi's first skill.
<br><br>
Positive Values:
<br>
<img src="./images/icons/sp_atk_up.png" alt="Sp Atk Up" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
Special Attack Up
<br><br>
Negative Values:
<br>
<img src="./images/icons/sp_atk_down.png" alt="Sp Atk Down" style="width: 19px; height:auto; border:none; padding:0; margin:0; vertical-align: sub"> 
Special Attack Down
<br><br>
<b>Usage Examples:</b>
<br>
<code>/calc2 string: Ereshkigal p30</code>
<br>
This would calculate Ereshkigal's Noble Phantasm with 30% special attack up.
<br><br>
<code>/calc2 string: Ereshkigal p-30</code>
<br>
This would calculate Ereshkigal's Noble Phantasm with 30% special attack down.
</details>


### Shorthands
brave, super, hyper, xss, xssd, xmm, etc.