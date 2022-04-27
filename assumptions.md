<h2>Assumptions</h2>

Given that `/calc2 string: Ereshkigal` is  a valid calculation, you may have noticed that EreshBot
must be assuming some arguments by default. This is indeed the case. Below is a list of everything that 
is included by default in a calculation if not explicitly specified:

Structure Arguments:
<ol>
<li>If a card is not specified, <code>card1</code> will be set to an NP.</li>
<li>If an enemy isn't specified, a blank enemy <code>enemy1</code> will be created.</li>
<li>If <code>wavesize</code> isn't specified, it will be set to 3.</li>
<li>If exactly three cards are provided, none of them are blank cards (<code>x</code>), none of them are 
extra cards, and at least one card is not an NP, an extra card will be added to the command chain.</li>
<li>If a single card is calculated, EreshBot will assume it is in position one and benefits from 
the <code>firstCardBonus</code> of its card type.</li>
<li>If a card chain is calculated, card positions and first card bonuses are included accordingly.</li>
</ol>

Servant Attributes / Buffs:
 <ol>
  <li>If a servant's level isn't specified, it will be set to their max level without grails.</li>
  <ul>
      <li>5 Star: 90</li>
      <li>4 Star: 80</li>
      <li>3 Star: 70</li>
      <li>2 Star: 65</li>
      <li>1 Star: 60</li>
      <li>0 Star: 65</li>
  </ul>
  <li>If no fou value is specified, it will be set to 1000.</li>
  <li style="color: #B70000FF;font-weight:bold">If no NP Level is specified, it will be set to NP 5.</li>
  <li>If no NP strengthening level is specified, it will be set to the highest strengthening 
    available on the NA server.</li>
  <li>Passive skills that are not conditional are always included.</li>
  <ul>
      <li>For example, 
    <a href="https://apps.atlasacademy.io/db/JP/servant/305">Caren's</a> 20% ATK 
    <a href="https://apps.atlasacademy.io/db/JP/skill/845650">passive</a> is not included since
    it is a conditional passive skill and relies on the presence of a debuff to take effect.
</li>
<li>
On the other hand, <a href="https://apps.atlasacademy.io/db/JP/servant/196">Ereshkigal's</a> 225 damage plus
<a href="https://apps.atlasacademy.io/db/JP/skill/30450">passive</a> and 11% Arts Damage
<a href="https://apps.atlasacademy.io/db/JP/skill/83551">passive</a> are both included, as they
are not conditional and are always active.
</li>
  </ul>
<li> Internal stats, like base star gen etc. are always included.</li>
<li> If an enemy class is specified, class affinity, enemy server mod (for NP Gen), and enemy server rate 
(for Star Gen) are all included.</li>
<li> If an enemy attribute is specified, attribute affinity is included.</li>
</ol>