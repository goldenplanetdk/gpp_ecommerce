# Feed templating

Template supports Twig syntax and all its filters and functions. You can read more about Twig here: https://twig.symfony.com/doc/2.x/

List of supported product properties:

id, article_id, title, gtin, link, mpn, description, image_link, brand, weight, price, sale_price, availability, adult, condition, category, category_path, google_product_category

## Some useful constructions:

Custom stock text
````
{{ product.quantity > 0 ? 'in stock' : 'out of stock' }}
````

Price with currency

````
{{ product.price | formatCurrency }}
````
