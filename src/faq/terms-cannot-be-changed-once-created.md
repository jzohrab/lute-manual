# Why can't I change a Term?

Lute won't let you change a Term's actual text once it has been created and saved, you can only change the case of existing characters.  For example, you could change "CAT" to "Cat" or "cat", but not to "dog".

Allowing Terms themselves to be changed once created creates potential problems, so (for now) Lute just disables that.

> _As I get more experience with this feature of Lute, I may do away with this restriction._

Reasons for this restriction:

* a typo or other mistake would cause previously entered information to get accidentally overwritten.  For example, if you'd created a Spanish Term and translation "chico / boy", and then accidentally edited another existing term "CHICA / girl" to "chic**o** / girl" (accidentally hitting "o" instead of "a") and saved it, the existing "chico / boy" term would be updated instead.

* During reading, if you click on an unknown word, and decide to change the term's capitalization, Lute won't let you mis-type the word.  For example, if you're reading a shocking Spanish newspaper article about "GATOS SALVAJES" (wild cats!), you might want to save the term "GATOS", but as lowercase "gatos".  Lute stops you from typing "gattos" during the fix, so the new term is created correctly.