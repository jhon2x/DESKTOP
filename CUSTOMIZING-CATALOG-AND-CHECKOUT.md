    technotrends
    ├── app
    │   ├── code
    │   │   ├── AcmeWidgets
    │   │   │   └── ProductPromoter
    │   │   │       ├── Api
    │   │   │       │   ├── Data
    │   │   │       │   │   ├── ProductPromoterInterfaceFactory.php
    │   │   │       │   │   └── ProductPromoterInterface.php
    │   │   │       │   └── ProductPromoterRepositoryInterface.php
    │   │   │       ├── Block
    │   │   │       ├── composer.json
    │   │   │       ├── Console
    │   │   │       ├── Controller
    │   │   │       │   ├── Adminhtml
    │   │   │       │   ├── Index
    │   │   │       │   │   └── Index.php
    │   │   │       │   └── Router.php
    │   │   │       ├── Cron
    │   │   │       │   ├── AcmeWidgetsProductPromoterByConfigTask.php
    │   │   │       │   └── AcmeWidgetsProductPromoterTask.php
    │   │   │       ├── etc
    │   │   │       │   ├── acl.xml - (6.1) restrict access to REST and SOAP APIs and extension attributes
    │   │   │       │   ├── address_formats.xml
    │   │   │       │   ├── adminhtml
    │   │   │       │   │   ├── di.xml
    │   │   │       │   │   ├── events.xml
    │   │   │       │   │   ├── menu.xml
    │   │   │       │   │   ├── routes.xml
    │   │   │       │   │   ├── sections.xml
    │   │   │       │   │   └── system.xml
    │   │   │       │   ├── base
    │   │   │       │   │   └── events.xml
    │   │   │       │   ├── cache.xml
    │   │   │       │   ├── config.xml
    │   │   │       │   ├── cron_groups.xml
    │   │   │       │   ├── crontab.xml
    │   │   │       │   ├── di.xml
    │   │   │       │   ├── email_templates.xml
    │   │   │       │   ├── events.xml
    │   │   │       │   ├── extension_attributes.xml
    │   │   │       │   ├── frontend
    │   │   │       │   │   ├── di.xml
    │   │   │       │   │   ├── events.xml
    │   │   │       │   │   └── routes.xml
    │   │   │       │   ├── indexer.xml
    │   │   │       │   ├── module.xml
    │   │   │       │   ├── mview.xml
    │   │   │       │   ├── product_options.xml
    │   │   │       │   ├── product_types.xml
    │   │   │       │   ├── view.xml
    │   │   │       │   ├── webapi_rest
    │   │   │       │   │   └── events.xml
    │   │   │       │   ├── webapi_soap
    │   │   │       │   │   └── events.xml
    │   │   │       │   ├── webapi.xml
    │   │   │       │   └── widget.xml
    │   │   │       ├── Helper
    │   │   │       ├── i18n
    │   │   │       ├── Model
    │   │   │       │   ├── ProductPromoter
    │   │   │       │   │   └── Proxy.php
    │   │   │       │   ├── ProductPromoterRepository.php
    │   │   │       │   └── ResourceModel
    │   │   │       ├── Observer
    │   │   │       │   └── AssignData.php
    │   │   │       ├── Plugin
    │   │   │       ├── registration.php
    │   │   │       ├── Setup
    │   │   │       │   ├── InstallData.php
    │   │   │       │   ├── InstallSchema.php
    │   │   │       │   ├── RecurringData.php
    │   │   │       │   ├── Recurring.php
    │   │   │       │   ├── UpgradeData.php
    │   │   │       │   └── UpgradeSchema.php
    │   │   │       ├── Test
    │   │   │       ├── tuts.md
    │   │   │       ├── Ui
    │   │   │       ├── view
    │   │   │       │   ├── adminhtml
    │   │   │       │   │   ├── layout
    │   │   │       │   │   ├── requirejs-config.js
    │   │   │       │   │   ├── templates
    │   │   │       │   │   ├── ui_component
    │   │   │       │   │   └── web
    │   │   │       │   │       ├── css
    │   │   │       │   │       ├── js
    │   │   │       │   │       └── template
    │   │   │       │   └── frontend
    │   │   │       │       ├── layout
    │   │   │       │       │   ├── layouts.xml
    │   │   │       │       │   └── productpromoter_index_index.xml
    │   │   │       │       ├── page_layout
    │   │   │       │       │   └── 2columns-left.xml
    │   │   │       │       ├── requirejs-config.js
    │   │   │       │       ├── templates
    │   │   │       │       │   └── index.phtml
    │   │   │       │       └── web
    │   │   │       │           ├── css
    │   │   │       │           ├── js
    │   │   │       │           └── template
    │   │   │       └── ViewModel
    │   │   │           └── ProductPromoter.php


    └── vendor
        └── magento
            ├── framework
            │   ├── Api
            │   │   ├── CustomAttributesDataInterface.php
            │   │   ├── ExtensibleDataInterface.php
            │   │   ├── FilterBuilder.php
            │   │   ├── Search
            │   │   │   └── SearchCriteriaBuilderFactory.php
            │   │   ├── SearchCriteriaBuilder.php
            │   │   ├── SearchCriteriaInterface.php
            │   │   └── SearchResultsInterface.php
            │   ├── App
            │   │   ├── Action
            │   │   │   ├── AbstractAction.php
            │   │   │   └── Action.php
            │   │   ├── ActionInterface.php
            │   │   ├── AppInterface.php
            │   │   ├── AreaList.php
            │   │   ├── Bootstrap.php
            │   │   ├── FrontControllerInterface.php
            │   │   ├── FrontController.php
            │   │   ├── Http.php
            │   │   ├── ObjectManager.php
            │   │   ├── ResponseInterface.php
            │   │   ├── Router
            │   │   │   ├── Base.php
            │   │   │   └── NoRouteHandlerList.php
            │   │   ├── RouterInterface.php
            │   │   └── RouterListInterface.php
            │   ├── Component
            │   │   └── ComponentRegistrar.php
            │   ├── Config
            │   │   ├── ConverterInterface.php
            │   │   ├── Data.php
            │   │   ├── Reader
            │   │   │   └── Filesystem.php
            │   │   └── SchemaLocatorInterface.php
            │   ├── Controller
            │   │   ├── AbstractResult.php
            │   │   ├── Result
            │   │   │   ├── Forward.php
            │   │   │   ├── Json.php
            │   │   │   ├── Raw.php
            │   │   │   └── Redirect.php
            │   │   └── ResultInterface.php
            │   ├── DB
            │   │   ├── Adapter
            │   │   │   └── AdapterInterface.php
            │   │   └── Ddl
            │   │       └── Table.php
            │   ├── Event
            │   │   └── ObserverInterface.php
            │   ├── Filesystem.php
            │   ├── Interceptor
            │   │   └── Interceptor.php
            │   ├── Message
            │   │   └── ManagerInterface
            │   ├── Model
            │   │   ├── AbstractExtensibleModel.php - (11)
            │   │   ├── AbstractModel.php
            │   │   └── ResourceModel
            │   │       └── Db
            │   │           ├── AbstractDb.php
            │   │           └── Collection
            │   │               └── AbstractCollection.php
            │   ├── Module
            │   │   └── ModuleList
            │   │       └── Loader.php
            │   ├── ObjectManager
            │   │   └── Factory
            │   │       └── Dynamic
            │   │           ├── Developer.php
            │   │           └── Production.php
            │   ├── ObjectManagerInterface.php
            │   ├── Setup
            │   │   ├── InstallSchemaInterface.php
            │   │   ├── ModuleContextInterface.php
            │   │   ├── ModuleDataSetupInterface.php
            │   │   ├── SchemaSetupInterface.php
            │   │   ├── SetupInterface.php
            │   │   └── UpgradeDataInterface.php
            │   └── View
            │       ├── Element
            │       │   ├── AbstractBlock.php
            │       │   ├── Block
            │       │   │   └── ArgumentInterface.php
            │       │   └── Template.php
            │       ├── Model
            │       │   └── Layout
            │       │       └── Merge.php
            │       ├── Result
            │       │   └── Page.php
            │       └── TemplateEngine
            │           └── Php
            ├── MediaStorage
            │   └── Model
            │       └── File
            │           └── UploaderFactory.php
			├── module-backend
            │   └── Block
            │       └── AbstractBlock.php
			├── module-catalog
            │   ├── Api
            │   │   ├── CategoryRepositoryInterface.php table::catalog_category_entity - (7)
            │   │   ├── Data
            │   │   │   ├── CategoryInterfaceFactory.php - (6)
            │   │   │   └── ProductInterface.php
            │   │   └── ProductRepositoryInterface.php
            │   ├── Model
            │   │   ├── Category
            │   │   │   └── Tree.php - (8)
            │   │   ├── Product
            │   │   │   └── Type
            │   │   │       └── Price.php::calculatePrice - (1)
            │   │   ├── ProductRepository.php
            │   │   └── ResourceModel
            │   │       └── Category.php::changeParent - (9)
            │   └── view
            │       ├── base
            │       │   ├── layout
            │       │   │   └── default.xml - (2) - p.p.r.d
            │       │   ├── templates
            │       │   │   ├── js
            │       │   │   │   └── components.phtml
            │       │   │   └── product - (4)
            │       │   │       ├── composite
            │       │   │       │   └── fieldset
            │       │   │       │       └── options
            │       │   │       │           └── view
            │       │   │       │               └── checkable.phtml
            │       │   │       └── price
            │       │   │           ├── amount
            │       │   │           │   └── default.phtml
            │       │   │           ├── configured_price.phtml
            │       │   │           ├── default.phtml
            │       │   │           ├── final_price.phtml
            │       │   │           └── tier_prices.phtml
            │       │   └── web
            │       │       └── template
            │       │           └── product - (5)
            │       │               ├── final_price.html
            │       │               ├── link.html
            │       │               ├── name.html
            │       │               └── price
            │       │                   ├── max_price.html
            │       │                   ├── max_regular_price.html
            │       │                   ├── minimal_price.html
            │       │                   ├── minimal_regular_price.html
            │       │                   ├── price_box.html
            │       │                   ├── pricetype_box.html
            │       │                   ├── regular_price.html
            │       │                   └── special_price.html
            │       └── frontend
            │           └── layout
            │               └── catalog_product_view.xml
            ├── module-catalog-rule
            │   └── Model
            │       └── Indexer
            │           └── IndexBuilder.php - (10) -- Customizing the Catalog end here.
            ├── module-catalog-url-rewrite
            ├── module-checkout
            │   ├── Controller
            │   │   └── Cart
            │   │       └── Add.php - (21) add item to the cart from product page
            			└── Configure.php - (25) handles cart edit functionality
            │   └── Model
            │       └── Session.php::getQuote() - (12)
            ├── module-customer
            │   ├── Controller
            │   │   └── Account
            │   │       └── Login.php
            │   ├── etc
            │   │   └── frontend
            │   │       └── routes.xml
            │   └── Setup
            │       └── CustomerSetup.php
            ├── module-downloadable
            │   └── view
            │       └── frontend
            │           └── layout
            │               └── catalog_product_view_type_downloadable.xml - (3)
            ├── module-payment
            │   └── Model
            │       ├── Method
            │       │   └── AbstractMethod.php::isAvailable - (29) check to troubleshoot payment methods
            │       └── MethodInterface.php - (28) Payment methods implement
            ├── module-quote
            │   ├── Api
            │   │   └── Data
            │   │       └── PaymentMethodInterface.php - (27) Payment methods implement
            │   └── Model
            │       ├── Quote
            │       │   ├── Address
            │       │   │   └── Total
            │       │   │       └── AbstractTotal.php - (18) Every total model extends
            │       │   ├── Address.php - (15) represents quote address
            │       │   └── Item.php - (14) represent quote item
            │       └── Quote.php - (13) The model containing the quote’s data
            			- (24) add product to cart
            			Events triggered:
            			•	 sales_quote_add_item (in quote entity)
            ├── module-sales
            │   ├── Controller
            │   │   └── AbstractController
            │   │       └── Reorder.php - (23) add item to the cart from whislist page
            				Events triggered:
            				•	 checkout_cart_product_add_after (in cart entity, applicable to frontend, backend, and REST)
            				•	 sales_quote_product_add_after (in quote entity)
            				•	 sales_quote_add_item (in quote entity)
            │   └── Model
            │       └── Quote.php::addItem - (19) adding item to the cart
            			Events triggered (object provided):
            			•	 checkout_cart_add_product_complete
            			•	 checkout_cart_product_add_after (in cart entity, applicable to frontend, backend, and REST)
            			•	 sales_quote_product_add_after (in quote entity)
            			•	 sales_quote_add_item (in quote entity)

            ├── module-sales-rule - (16) handles shopping cart rules logic
	        ├── module-shipping
            │   └── Model
            │       └── Carrier
            │           ├── AbstractCarrierOnline.php - Shipping methods extends
            					::canCollectRates
            │           ├── AbstractCarrier.php - Shipping methods extends
            					::collectRates
            │           └── CarrierInterface.php - (26) Shipping methods implement
            ├── module-tax
            │   └── etc
            │       └── sales.xml - (17) provides an example of how the tax module links this UploaderFactory
            ├── module-theme
            │   └── view
            │       ├── base
            │       │   └── templates
            │       │       └── root.phtml
            │       └── frontend
            │           ├── layout
            │           │   └── layouts.xml
            │           └── page_layout
            │               ├── 1column.xml
            │               ├── 2columns-left.xml
            │               └── 3columns.xml
            ├── module-url-rewrite
            │   └── Controller
            │       └── Router.php
            ├── module-webapi
            │   └── Controller
            │       ├── Rest.php
            │       └── Soap.php
            └── module-wishlist
                └── Controller
                    └── Index
                        └── Cart.php - (22) add item to the cart from whislist page
                        	Events triggered (object provided):
                        	•	 checkout_cart_product_add_after (in cart entity, applicable to frontend, backend, and REST)
                        	•	 sales_quote_product_add_after (in quote entity)
                        	•	 sales_quote_add_item (in quote entity)
