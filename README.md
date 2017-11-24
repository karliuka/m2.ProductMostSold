# Magento2 Product Most Sold

Extension displays the top most sold products for your stores.

### Home page

<img alt="Magento2 ProductMostSold" src="https://karliuka.github.io/m2/product-most-sold/home.png" style="width:100%"/>

### Category page

<img alt="Magento2 ProductMostSold" src="https://karliuka.github.io/m2/product-most-sold/category.png" style="width:100%"/>

## Install with Composer as you go

1. Go to Magento2 root folder

2. Enter following commands to install module:

    ```bash
    composer require faonni/module-product-most-sold
    ```
   Wait while dependencies are updated.

3. Enter following commands to enable module:

    ```bash
	php bin/magento setup:upgrade
	php bin/magento setup:static-content:deploy
    ```

4. Refresh Statistics
    
## Display and configuration

1. A shortcode to Homepage and to other CMS pages or CMS blocks.

    ```bash
	{{block class='Faonni\ProductMostSold\Block\ProductList' 
			template='Faonni_ProductMostSold::product/list/items.phtml' 
			title='Most Sold Products' 
			interval='45'
			num_products='6'
	}}
    ```
    
2. A Layout Update XML to all categories.

    ```xml
	 <referenceBlock name="catalog.product.most.sold">
		 <action method="setTitle">
			 <argument name="title" xsi:type="string" translate="true">Most Sold Products of Category</argument>
		 </action>
		 <action method="setNumProducts">
			 <argument name="num_products" xsi:type="string">6</argument>
		 </action>
		 <!-- last 45 days, if 0 - all lifetime -->
		 <action method="setInterval">
			 <argument name="interval" xsi:type="string">45</argument>
		 </action>	
	 </referenceBlock>
    ```
    
* [Magento2 Product Most Ordered](https://github.com/karliuka/m2.ProductMostOrdered)
* [Magento2 Product Most Viewed](https://github.com/karliuka/m2.ProductMostViewed)
