http://techjeffyu.com/blog/magento-2-add-a-custom-field-to-checkout-shipping
steps:
app\
	code\
		AcmeWidgets\
			ProductPromoter\
				etc\
          di.xml - 2 create plugin (LayoutProcessor),
                 - 6 (ShippingInformationManagement)  
          extension_attributes.xml - 5
          events.xml - custom_fields_sales_address_save - 8
        Setup\
          UpgradeSchema.php - 1
        Plugin\
          Block\
            Checkout\
              LayoutProcessor.php - 2
          Quote\
            SaveToQuote.php - 7    
        view\
          frontend\
            web\
              js\
                shipping-save-processor.js  - 3   
            requirejs-config.js - 4    
        Observer\
          SaveCustomFieldsInOrder.php - 9    


1. What is the relationship between carriers and rates?
2. Describe how to troubleshoot shipping methods and rate results.
3. Where do shipping rates come from?
