Ce module est un module de démonstration **demo module** utile pour installer tous les
modules Odoo liés à la certification du point de vente, dans un contexte législatif
français.

**Ce module est inutile en production.**

Pour faire fonctionner correctement Odoo dans un contexte de certification.

### Paramétrage à réaliser

- Configurer la `decimal.precision` `product.decimal_product_uom` (Product Unit of
  Measure) à la valeur `3`.

- Configurer la `uom.uom` `product.decimal_product_uom` (kg) à la précision d'arrondi
  `0.001`.

### Module Odoo à installer

- Module Odoo CE `point_of_sale`.

- Module OCA `pos_scale_usability` (https://github.com/OCA/pos/pull/1620).

  - Ce module corrige un bug d'affichage présent dans l'écran de mesure du poid du
    produit.

- Module OCA `pos_tare` (https://github.com/OCA/pos/blob/16.0/pos_tare).

  - Ce module permet de saisir la tare d'un contenant (saisie manuelle ou bien par scan
    de code barre) et d'envoyer le montant de la tare à la balance qui calcule et
    renvoie le poid net.
  - Le module affiche à l'écran et sur le ticket le montant du poid brut, du poid net et
    de la tare.

- Module `pos_driver_device_list`
  (https://gitlab.com/odoo-driver/odoo-addons-driver/-/blob/16.0/pos_driver_device_list/)

  - Ce module permet de lister le (ou les) périphérique(s) connecté(s) avec leur numéro
    de série.
  - Il permet aussi de récupérer le hash du code source du driver `odoo-driver`.

- Module `pos_driver_scale`
  (https://gitlab.com/odoo-driver/odoo-addons-driver/-/blob/16.0/pos_driver_scale/)
  - Ce module rajoute des badges qui affichent l'état de connexion de la balance. (pas
    de connexion, poid nul, mesure en cours, mesure réalisée, ...)
