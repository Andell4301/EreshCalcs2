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
</table>
All arguments following the card argument will apply only to the specified card until a new card is specified. 
The card argument does not define new cards. If you use <code>card6</code> when there are only 5 cards, 
<code>card6</code> and all arguments that would apply to <code>card6</code> will be treated as invalid.

Usage Examples:
<br>
<code>/calc2 string: Ereshkigal card1 a30 m30 n50</code>
<br>
<code>/calc2 string: Ereshkigal bnqe card1 a30 m30 n50 card2 a20 d30 m70</code>
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
</table>
All arguments following the enemy argument will apply only to the specified enemy until a new card is specified. 
The enemy argument also defines new enemies. If you use <code>enemy3</code> when there are only 2 enemies, 
a new enemy in position 3 will be created.

Usage Examples:
<br>
<code>/calc2 string: Ereshkigal enemy1 saber hp1000</code>
<br>
<code>/calc2 string: Ereshkigal enemy1 saber hp1000 enemy2 berserker hp5000</code>
<br>
<code>/calc2 string: Ereshkigal enemy1 m40 d-30 enemy2 m60 d-20</code>
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
</table>
Used for targeting enemies with a card. If provided after a card, the card will only hit
the specified enemy. For AoE Noble Phantasms, multiple <code>e</code> args can be specified.

The <code>e</code> argument can only be used if provided after first explicitly switching to a card.

If an invalid enemy is provided, the argument will be ignored. Ex. if there are only 2 enemies, 
<code>e3</code> will be ignored.

Usage Examples:
<br>
<code>/calc2 string: Ereshkigal nwave1 card1 e1</code>
<br>
<code>/calc2 string: Ereshkigal bba nwave1 card1 e1 card2 e3 card3 e2</code>
<br>
<code>/calc2 string: Ereshkigal npbb enemy1 enemy2 card2 e2 card3 e2</code>
<br>
<code>/calc2 string: Ereshkigal nwave1 card1 e1 e2</code>
</details>