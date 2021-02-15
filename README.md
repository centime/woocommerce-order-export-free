
## Free & easy solution to export WooCommerce orders to CSV


[version française](LISEZMOI.md)

We're just going to create a special kind of bookmark, refered to as "bookmarklet" (bookmark + applet).

* Create a new bookmark to whichever page you want. I suggest to just right-click this link: [Export Order](https://github.com/centime/woocommerce-order-export-free)
* Edit the bookmark target url (right-click > edit...)
* Instead of the url (http...), paste the code below:

```
javascript:(()=>{ var items = document.querySelectorAll('.item'); var order = []; var csv = "name;item_cost;quantity;line_cost;line_tax<br/>"; function s(str){ return str.replaceAll(';',',')} for (let i=1; i<items.length; i++){  var $item = items[i];  var item = {   'name': $item.querySelector('.wc-order-item-name').innerText,   'item_cost': $item.querySelector('.item_cost').innerText,   'quantity': $item.querySelector('.quantity').innerText,   'line_cost': $item.querySelector('.line_cost').innerText,   'line_tax': $item.querySelector('.line_tax').innerText  };  order.push(item);  csv += s(item['name']) + ';' + s(item['quantity']) + ';' + s(item['line_tax']) + ';' + s(item['line_cost']) + ';' + s(item['line_tax']) + '<br/>' } document.write(csv);})()
```

* When on the page for your order, click the bookmark from your browser
* The page will be rewritten to display your order formatted as CSV
* Just copy/paste it into a spreadsheet for easy order preparation

Note: this is nothing but a quick and dirty javascript snippet, but as long as it gets the job done...


## Find it useful ? Buy me a beer !

[Buy Vincent a beer](https://paypal.me/VincentDelaunay/5)

This code was created as a favor to [la Pause locale](https://boutique.lapauseduperche.fr/)


## BEERWARE LICENSE

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
