# Feed templating

Template supports Twig syntax and all its filters and functions. You can read more about Twig here: https://twig.symfony.com/doc/2.x/

List of supported product properties:

id, article_id, title, gtin, link, mpn, description, primary_image_link, image_link, brand, weight, price, sale_price, availability, adult, condition, category, category_path, google_product_category, extra

## Some useful constructions:

Custom stock text
````
{{ product.quantity > 0 ? 'in stock' : 'out of stock' }}
````

Price with currency
````
{{ product.price | formatCurrency }}
````

Extra tab content assigned to tab title with ID:1
````
{{ product.extra.1 }}
````

Render html text without encoding to special chars
````
{{ product.extra.1 | raw }}
````

Remove html tags
````
{{ product.extra.1 | striptags }}
````

Features (product-level attributes)
```
{{ product.features|map(f => "#{f.attribute}: #{f.value}")|join(', ') }}
```
will output Color: Black, Material: Cotton
