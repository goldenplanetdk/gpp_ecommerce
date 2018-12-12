# Feed templating

Template supports Twig syntax and all its filters and functions. You can read more about Twig here: https://twig.symfony.com/doc/2.x/

List of supported product properties:

id, variant_id, variant_title, title, model, url, description, ean, image, brand, supplier, category, created_at, weight, price, price_with_tax, cost_price, cost_price_with_tax

## Some useful constructions:

Display date according to format, e.g. ``12/29/2018``
````
{{ product.created_at | date('m/d/Y') }}
````

Custom stock text
````
{{ product.quantity > 0 ? 'in stock' : 'out of stock' }}
````

Absolute url to the original main product's image, e.g. ``http://yourshop.com/product-images/1/apple-iphone.png``
````
{{ product.image ? absolute_url(product.image) : '' }}
````

Absolute url to the product's thumb **product_info_main_thumb**. It is name of thumb used on product's page: 
``http://yourshop.com/media/cache/product_info_main_thumb/product-images/1/apple-iphone.png``
````
{{ product.image ? absolute_url(product.image | imagine_filter(''product_info_main_thumb'')) : '' }}
````

Format price, e.g. 1125 will be displayed as 1.125,00
````
{{ product.price | formatCurrency }}
````
