# Defense Rating

### !!! WARNING : LOTS OF NUMBERS AHEAD !!!

{% hint style="danger" %}
#### Due to a Minecraft limitation, armor sets cannot give more than 20 total Armor Points (the armor icons on your hotbar).
{% endhint %}

&#x20;   To make things a lot simpler than the normal formulae for Minecraft damage calculations, which look something like this:

![Armor Damage Reduction by % and Damage Received](<../../.gitbook/assets/image (48).png>)

&#x20;   As you may notice, as damage increases, you armor's effectiveness actually decreases. This works just fine in Vanilla gameplay since nothing is ever going to hit you for 80 damage, but that is a sure possibility on PrometheumMC. Just to drive the point home, here is a graph of perceived damage.

![Damage After Reduction / Damage Before Reduction](<../../.gitbook/assets/image (94).png>)

&#x20;   In this graph, all reduced damage eventually reaches a linear relationship with damage before reduction, which means that past a certain point your armor becomes useless.

### The Solution:

#### &#x20;   Implement a new damage reduction method.

&#x20;   Using the new Defense stat, all armor now uses a much simpler formula of:

$$
f(x) = d(1-{D \above{1pt} D+100})
$$

​    Where:

&#x20;   _f(x)_ = damage after reduction\
&#x20;   _d_ = unmodified damage recieved\
&#x20;   _D_ = total defense points

&#x20;   Here's what that looks like on a graph:

&#x20;   Given 20 initial damage:

&#x20;   With _d_ = 20, let's see a graph of damage over upward scaling defense points.

![ ](<../../.gitbook/assets/image (64).png>)

&#x20;   You can see that at around 100 defense, the damage is halved. That is due to the formula giving flat damage negation at all damage levels.&#x20;



![Damage Reduction in % over Increasing Defense Points](<../../.gitbook/assets/image (82).png>)

&#x20;   Flat number chart of actual damage taken for a specific amount of received damage and defense points:

![](<../../.gitbook/assets/image (56).png>)

&#x20;   Here's another visualization, this time instead of putting flat damage against scaling defense points, let's put scaling damage over flat defense points:

![Scaling damage over Flat Defense Points](<../../.gitbook/assets/image (66).png>)

&#x20;    Here it is really easy to tell that with _D_ being 100, incoming damage is reduced by 50% for all damage values.

### So, What does this all mean?

&#x20;   Put simply, defense is easier to manage. Defense will work better with larger damage numbers, and can be increased by upgrading armor.
