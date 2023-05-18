# Correction MCD

Pour la correction de ce MCD j'ai utilisé l'outil [MOCODO](https://www.mocodo.net/)

## Cardinalitées

- Relation USER/ADDRESS **ManyToOne**
  
Un utilisateur peut avoir au minimum une adresse et au maximum plusieurs (`1N`)
Une adresse appartient à un utilisateur au minimum et a un seul au maximum (`11`)

- Relation USER/ORDER **ManyToOne**
  
Un utilisateur peut ne pas passer de commande ou en passer plusieures (`0N`)
Une commande peut etre passer au minum et au maximum par un utilisateur (`11`)

- Relation ORDER/PRODUCT **ManyToMany**
  
Une commande doit contenir au moins un produit et peut en contenir plusieurs (`1N`)
Un produit peut ne pas etre lier a une commande ou etre  contenu dans plusieures (`ON`)

- Relation USER/PRODUCT **ManyToMany**

Un utilisateur peut aimer aucun produit ou plusieurs (`0N`)
Un produit peut etre aimer par aucun utilisateur ou par plusieurs (`0N`)

## Identifiants

Les identifiants uniques (ID) n'apparaissent par sur le Modèle Conceptuel de Données. Le MCD se concentre sur la modélisation des entitées, des relations et des attributs.

Les identifiants seront répertoirés dans le Modèle Physique de Données.

## MOCODO

```mcd
ADDRESS:_address, city, postal_code
HAS, 1N USER, 11 ADDRESS
USER:_email, password
LIKE, ON USER, ON PRODUCT
PRODUCT:_name, description, mug_type, amount

:
:
GENERATE, 0N USER, 11 ORDER
ORDER:_total_amount, status
CONTAIN, 1N ORDER, 0N PRODUCT
```

## Conclusion

Dans ce MCD, il existe deux relations ManyToMany qui se traduirons par la création de **_table pivot_** par la suite dans le MPD.
