## Full Argument List

### Structure Arguments
Utilized for setting up the structure of the calculation. How many enemies, which card 
hits who, etc.

<b>Card#</b><br>
Arguments supplied after a `card#` argument will only be applied to the specified card until a 
new structure argument is supplied.

Ex. `/calc2 string: Ereshkigal buster arts card1 m30 m40 card2 m50 m60`
<br>
In this example, a buster and arts card are first specified. Then we have the `card1` argument followed 
by `m30` and `m40` and the `card2` argument followed by `m50` and `m60`.
In this example, the buster card is `card1` and the arts card is `card2`, so `m30` and `m40`
will only be applied to the buster card and `m50` and `m60` will only be applied to the arts card.