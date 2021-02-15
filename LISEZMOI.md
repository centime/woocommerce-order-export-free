
# olution gratuite et facile pour exporter les commandes WooCommerces en CSV

[english version](README.md)

Il s'agit simplement de faire un marquepage spécial, appelé "bookmarklet" (bookmark + applet), qui va exécuter une opération simple de formatage.

* Créez un marquepage vers n'importe quel lien. Par exemple, avec un click droit sur: [Exporter Commande](https://github.com/centime/woocommerce-order-export-free)
* Modifiez la cible du marquepage (clic droit > modifier...)
* Au lieu de l'url http..., mettez le code suivant:

```
javascript:(()=>{ var items = document.querySelectorAll('.item'); var order = []; var csv = "name;item_cost;quantity;line_cost;line_tax<br/>"; function s(str){ return str.replaceAll(';',',')} for (let i=1; i<items.length; i++){  var $item = items[i];  var item = {   'name': $item.querySelector('.wc-order-item-name').innerText,   'item_cost': $item.querySelector('.item_cost').innerText,   'quantity': $item.querySelector('.quantity').innerText,   'line_cost': $item.querySelector('.line_cost').innerText,   'line_tax': $item.querySelector('.line_tax').innerText  };  order.push(item);  csv += s(item['name']) + ';' + s(item['quantity']) + ';' + s(item['line_tax']) + ';' + s(item['line_cost']) + ';' + s(item['line_tax']) + '<br/>' } document.write(csv);})()
```

* Ensuite, depuis la page affichant votre commande, cliquez ce marque-page. 
* La page sera réecrite avec votre commande formatée en CSV
* Vous pouvez la copier dans votre tableur pour la préparer efficacement.

Note: ce n'est qu'un petit code javascript fait à la va-vite, mais tant que ça marche...


## Ca t'est utile ? Paye-moi une bière !

[Payer une bière à Vincent](https://paypal.me/VincentDelaunay)


Ce code a été créé pour dépanner [la Pause locale](https://boutique.lapauseduperche.fr/)


## LICENSE BEERWARE

```
/*
 * ----------------------------------------------------------------------------
 * "THE BEER-WARE LICENSE" (Revision 42):
 * vinc.delaunay@gmail.com wrote this file.  As long as you retain this notice you
 * can do whatever you want with this stuff. If we meet some day, and you think
 * this stuff is worth it, you can buy me a beer in return.   Vincent Delaunay.
 * ----------------------------------------------------------------------------
 */
```