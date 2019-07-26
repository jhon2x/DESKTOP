https://www.indeed.com/hire/interview-questions/web-developer
https://www.youtube.com/watch?v=Pi0X47Bj3oA
english native
1.1 DESCRIBE MAGENTO’S MODULE-BASED ARCHITECTURE
1. 5 areas
2. The three necessary files to bootstrap a module
are
3. Modules live in one of two places,
  2 possible place for module.
4. different ways to install modules ?
  - via composer.json
  - app/code
  - wizard
5. The only required files to initiate a module is  
6. how enable module
7. How do diferent modules interact with each other?
    - using PSR-44
    - service contract
    - depency injection
8. Dependency injection is a means of giving a class what it needs to function.
9. ObjectManager is Magento’s internal object storage unit and should rarely be directly accessed.
10. The ObjectManager makes implementing the Composition over Inheritance principle possible.
11. Dependency injection makes testing easier, application more configurable and provides options for powerful features such as plugins.

12. plugins - Plugins allow you to wrap another class’ public functions, add a before method to modify the input arguments, or add an after method to modify the output.
  around - You can use an around plugin to validate the incoming request and cancel the save if the result is invalid. (use single responsibilty princile)
  before method - to modify the input arguments
  after method - to modify the output.

13. Preferences - Preferences are used to substitute entire classes.   
14. When to use events or plugins?
  - if you want to transform data use plugin else observer

15. Magento 2 includes two means of caching: server caching, Varnish caching and
browser caching.  

16.
  url_rewrite table
  request_path: "super-blue-widget" target_path: "catalog/product/view/id/1234"



```
app/
  code/ - place for custom module installed
    AcmeWidgets/
      ProductPromoter/
        Api/ - stores service contract
          ProductPromoterRepositoryInterface.php - used for preferences to Model/ProductPromoterRepository.php
          Data/ - stores data representation
            ProductPromoterInterface.php
            ProductPromoterInterfaceFactory.php
        Block/  - responsible for outputting its contents to phtml
        Console/
        Controller/
          Router.php - use to create new router which implements \Magento\Framework\App\RouterInterface
          Adminhtml/ - path for admin controller
        Cron/  
        ViewModel/  - view model handles the logic of block. can be used to provide data to a template (.phtml)
        etc/
          adminhtml/ - area 1
            system.xml - Specifies configuration tabs, sections, groups and fields found in Store Configuration.
            menu.xml - Configures the menu in the adminhtml area.
            events.xml - This file registers event listeners. This file can often be put into a specific area.
            routes.xml - configuration file (specific)
            sections.xml - configuration file (specific)
            di.xml - configuration file (global or area specific ), This configures dependency injection for your module.
          frontend/  - area 2
            events.xml -This file registers event listeners. This file can often be put into a specific area.
            di.xml - configuration file (specific), This configures dependency injection for your module. Register the new created router
            routes.xml - configuration file (global or area specific )                  
          webapi_rest/ - area 3
            events.xml -This file registers event listeners. This file can often be put into a specific area.
          webapi_soap/ - area 4
            events.xml -This file registers event listeners. This file can often be put into a specific area.  
          base/ - area 5
            events.xml -This file registers event listeners. This file can often be put into a specific area.
          mview.xml - Triggers a type of event when data is modified in a database column (materialized views). This is most often used for indexing.  
          indexer.xml - Configures Magento indexers.  
          acl.xml - configuration files (global), This defines the permissions for accessing protected resources
          di.xml - configuration file (global or area specific)
          email_templates.xml - Specifies email templates that are used in Magento.
          module.xml - important files to bootstrap module, initiate module, configuration files (global)
          cache.xml - stored cache configuration.
          crontab.xml - configuration files (global), This identifies actions that are to occur on a schedule
          config.xml - configuration files (global), This loads in default configuration in to Store > Configuration
          webapi.xml - configuration files (global), Configures API access and routes.
          di.xml - configuration files (global), This configures dependency injection for your module.
          events.xml -This file registers event listeners. This file can often be put into a specific area.
          view.xml - Similar to config.xml but used for specifying default values for design configuration.
          widget.xml - Configures widgets to be used in products, CMS pages, and CMS blocks.
          address_formats.xml - the output types for an address
          extension_attributes.xml - generic entity extensibility system.
          product_options.xml - types of product options (text, file, select, etc.)
          product_types.xml - stores product types (simple, configurable, etc.)
        Helper/ - use for small reusable code  
        i18n/
        Model/
          ProductPromoterRepository.php
          ProductPromoter/
            Proxy.php
          ResourceModel/ - crud data from the database
        Observer/
        Plugin/ - function modification (for class and interface only that are instantiated by the ObjectManager)
        Setup/ - Database Modification
          InstallSchema.php - sets up table/column schema when the module is installed.
          UpgradeSchema.php - modifies table / column schema when the module version is upgraded.
          Recurring.php - runs after every install or upgrade.
          InstallData.php - sets up data when the module is installed. An example would be adding a custom CMS block.
          UpgradeData.php - modifies data after the module is installed, when the module version is upgraded.
          RecurringData.php - applies to data after every install or upgrade.
        Test/
        Ui/ - UI Component Data Providers  
        view/ - Frontend-related files are found  
          adminhtml/ - area
            layout/
            templates/  - store .phtml file
            ui_component/ - UI Components
            web/ - Web Assets
              js/ - stores js
              css/ - stores css
              template/ - JS Templates
            requirejs-config.js  
          frontend/ - area
            layout/
            templates/ - store .phtml file
            page_layout/ - New page structures
            web/ - Web Assets
              js/ - stores js
              css/ - stores css
              template/ - JS Templates
            requirejs-config.js - This configuration is used to control Javascript module dependencies, create aliases, and declare mixins

        composer.json - important files to bootstrap module
        registration.php  - important files to bootstrap module, initiate module
    etc/
      config.php - lists all module installed
      NonComposerComponentRegistration.php - loop all module registration.php from each module, included in composer.json    
  lib/ - place for supporting js and css files  
  pub/ - primary directory
    index.php - entry point
  generated/ - store auto created ClassNameFactory class  
  vendor/ - place for module installed via composer
    magento/ - place for magento module core     
      framework/
        App/
          AreaList.php - identify which module and controller corresponds to a given URL?
            ::getCodeByFrontName
          Action/
            Action.php - (abstract) extends in your controller which extends AbstractAction.php
            AbstractAction - (abstract) extends ActionInterface.php
          ActionInterface - (interface) if route is finally found this will be used. This action is the
            ::execute
          controller that will be executed. Controllers must implement this interface.
          Bootstrap.php - used in index to create bootstraping
            ::create
            ::createApplication - pass the Http.php
            ::run
          FrontControllerInterface.php - implemented by FrontController.php
            ::dispatch
          FrontController.php - Route finder. Is tasked with figuring out where to direct the request
            ::dispatch -
              ::match - from RouterInterface to check if route is match
          Http.php - area, used in pub/index.php
            ::::launch - checks area code, Object manager is configured for that area.Front controller is created. This is based on the area
          AppInterface.php - implemented by Http.php which has launch method that used in Http.php
          ResponseInterface.php - returned by execute() method, returning raw output
          RouterInterface.php -  is asked if it can match the route
          RouterListInterface.php - list of routers
          Router/
            Base.php - Default router (for most frontend requests)
              ::matchAction - Class creation at the time of injection
              ::parseRequest -  handles this operation. will look into conroller if route is march
        Controller/
            Result
              Forward.php - A controller can forward to another route, extends AbstractResult.php
              Json.php - extends AbstractResult.php
              Raw.php - extends AbstractResult.php
              Redirect.php - Redirect Controller to another URL, extends AbstractResult.php
            AbstractResult.php - implements ResultInterface.php   
            ResultInterface.php - returned by execute() method, this one assists in rendering HTML, JSON, or any other type of output.  It returns a 30x HTTP code with the URL for the browser to redirect to.
        component/
          ComponentRegistrar.php - This adds the module (component) to the static list of components. Once it is there, Magento will look for etc/module.xml.
        Config/
          Reader/
            Filesystem.php - extended by virtual type created. specifies the converter, schemaLocator, and filename. use for creating custom configuration files
          ConverterInterface.php - implement to your Converter class.
          SchemaLocatorInterface.php - implement to your SchemaLocater class
          Data.php - Implement to your  Data class  
        Event\
          ObserverInterface.php - implement by observer   
        Interceptor/
          Interceptor.php - it handles automatic create of an Interceptor when creating plugins using your own module which auto generated in generated folder.    
        ObjectManager/
          Factory/
            Dynamic/
              Developer.php - php bin/magento deploy:mode:show - developer
              Production.php - php bin/magento deploy:mode:show - production
        Model/
          ResourceModel/
            Db/
              AbstractDb.php - load and save objects
          AbstractModel.php      
        Module/
          ModuleList/
            Loader.php  -   connected to module.xml sequence
        View/
          Element/
            Template.php
            AbstractElement.php -
              ::toHtml() - html output is rendered
          Model/
            Layout/
              Merge.php - The layout XML files are merged into a large XML document and saved to the cache
              ::_loadFileUpdatesXml - debug your layout xml
          Result/
            Page.php -   
          TemplateEngine/
            Php.php
              ::render - The block that renders HTML from a template       
      module-catalog-url-rewrite/ - handles url rewrite
      module-theme/
        view/
          base/
            templates/
              root.phtml -  is the basic building block for Magento HTML output.    
      module-url-rewrite/ - handles url rewrite      
        Controller/
          Router.php -  handles the conversion of the pretty url into something that Magento better understands.
      module-webapi/
        Controller/
          Rest.php - area    
          Soap.php - area  
  composer.json - can install module, included     
```
1.2 DESCRIBE MAGENTO’S DIRECTORY STRUCTURE
1.3 UTILIZE CONFIGURATION XML AND VARIABLES SCOPE
  - Determine how to use configuration files in Magento.: Magento’s XML configuration is loaded on an as-needed basis. When di.xml is needed, Magento finds all di.xml files and merges them together

1.6 CONFIGURE EVENT OBSERVERS AND SCHEDULED JOBS
1.8 DEMONSTRATE THE ABILITY TO MANAGE THE CACHE

```
.
└── technotrends
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
    │   │   │       │   ├── acl.xml
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
    │   │   ├── AcmeWidgets0
    │   │   │   ├── ExtensionAttributes
    │   │   │   │   ├── Api
    │   │   │   │   │   └── Data
    │   │   │   │   │       └── ExtensionAttributesInterface.php
    │   │   │   │   ├── Controller
    │   │   │   │   │   └── Index
    │   │   │   │   │       └── Index.php
    │   │   │   │   ├── etc
    │   │   │   │   │   ├── di.xml
    │   │   │   │   │   ├── extension_attributes.xml
    │   │   │   │   │   ├── frontend
    │   │   │   │   │   │   └── routes.xml
    │   │   │   │   │   └── module.xml
    │   │   │   │   ├── Extension
    │   │   │   │   │   └── GetAttributes.php
    │   │   │   │   ├── Model
    │   │   │   │   │   └── ExtensionAttributes.php
    │   │   │   │   ├── Plugin
    │   │   │   │   │   └── ExtensionAttributesRepository.php
    │   │   │   │   └── registration.php
    │   │   │   └── ProductPromoter
    │   │   │       ├── Api
    │   │   │       │   ├── Data
    │   │   │       │   │   ├── ProductPromoterInterface.php
    │   │   │       │   │   └── ProductPromoterSearchResultInterface.php
    │   │   │       │   └── ProductPromoterRepositoryInterface.php
    │   │   │       ├── Block
    │   │   │       │   ├── ProductPromoter
    │   │   │       │   │   └── Page.php
    │   │   │       │   └── Sales
    │   │   │       │       └── Order
    │   │   │       │           └── Fee.php
    │   │   │       ├── Controller
    │   │   │       │   ├── Form
    │   │   │       │   │   ├── Ajaxcontact.php
    │   │   │       │   │   └── Contactus.php
    │   │   │       │   ├── Index
    │   │   │       │   │   ├── Deletebyid.php
    │   │   │       │   │   ├── Del.php
    │   │   │       │   │   ├── Getbyid.php
    │   │   │       │   │   └── Save.php
    │   │   │       │   ├── Product
    │   │   │       │   └── Results
    │   │   │       │       ├── Forward.php
    │   │   │       │       ├── Json.php
    │   │   │       │       ├── Page.php
    │   │   │       │       ├── Raw.php
    │   │   │       │       └── Redirect.php
    │   │   │       ├── etc
    │   │   │       │   ├── adminhtml
    │   │   │       │   │   └── system.xml
    │   │   │       │   ├── config.xml
    │   │   │       │   ├── di.xml
    │   │   │       │   ├── frontend
    │   │   │       │   │   ├── di.xml
    │   │   │       │   │   └── routes.xml
    │   │   │       │   ├── module.xml
    │   │   │       │   ├── payment.xml
    │   │   │       │   ├── sales.xml
    │   │   │       │   └── webapi.xml
    │   │   │       ├── Model
    │   │   │       │   ├── ProductLoader.php
    │   │   │       │   ├── ProductPromoterInterfaceModel.php.bk
    │   │   │       │   ├── ProductPromoter.php
    │   │   │       │   ├── Repository
    │   │   │       │   │   └── ProductPromoterRepository.php
    │   │   │       │   ├── ResourceModel
    │   │   │       │   │   ├── ProductPromoter
    │   │   │       │   │   │   └── Collection.php
    │   │   │       │   │   └── ProductPromoter.php
    │   │   │       │   └── Total
    │   │   │       │       └── Fee.php
    │   │   │       ├── Plugin
    │   │   │       │   └── Product.php
    │   │   │       ├── README.md
    │   │   │       ├── registration.php
    │   │   │       ├── Setup
    │   │   │       │   ├── InstallSchema.php
    │   │   │       │   └── ProductPromoterSetup.php.bk
    │   │   │       ├── view
    │   │   │       │   ├── adminhtml
    │   │   │       │   │   └── layout
    │   │   │       │   └── frontend
    │   │   │       │       ├── layout
    │   │   │       │       │   ├── checkout_cart_index.xml
    │   │   │       │       │   ├── checkout_index_index.xml
    │   │   │       │       │   ├── customer_account.xml
    │   │   │       │       │   ├── productpromoter_form_contactus.xml
    │   │   │       │       │   ├── productpromoter_results_page.xml
    │   │   │       │       │   └── sales_order_view.xml
    │   │   │       │       ├── templates
    │   │   │       │       │   ├── contactus.phtml
    │   │   │       │       │   └── page.phtml
    │   │   │       │       └── web
    │   │   │       │           ├── css
    │   │   │       │           │   └── jquery.dataTables.min.css
    │   │   │       │           ├── js
    │   │   │       │           │   ├── jquery.dataTables.min.js
    │   │   │       │           │   └── view
    │   │   │       │           │       └── checkout
    │   │   │       │           │           ├── cart
    │   │   │       │           │           │   └── totals
    │   │   │       │           │           │       └── fee.js
    │   │   │       │           │           └── summary
    │   │   │       │           │               └── fee.js
    │   │   │       │           └── template
    │   │   │       │               └── checkout
    │   │   │       │                   ├── cart
    │   │   │       │                   │   └── totals
    │   │   │       │                   │       └── fee.html
    │   │   │       │                   └── summary
    │   │   │       │                       └── fee.html
    │   │   │       └── ViewModel
    │   │   │           └── ProductPromoter.php
    │   │   └── etc
    │   │       ├── config.php
    │   │       └── NonComposerComponentRegistration.php
    │   └── design
    │       └── frontend
    │           └── Divante
    │               └── rapid
    │                   └── Magento_Theme
    │                       ├── layout
    │                       │   └── layouts.xml
    │                       └── page_layout
    │                           └── 2columns-left.xml
    ├── composer.json
    ├── generated
    ├── lib
    ├── pub
    │   └── index.php
    ├── tree.md
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
            │   │   ├── AbstractExtensibleModel.php
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
            │   │   ├── CategoryRepositoryInterface.php
            │   │   ├── Data
            │   │   │   ├── CategoryInterfaceFactory.php
            │   │   │   └── ProductInterface.php
            │   │   └── ProductRepositoryInterface.php
            │   ├── Model
            │   │   ├── Category
            │   │   │   └── Tree.php
            │   │   ├── Product
            │   │   │   └── Type
            │   │   │       └── Price.php
            │   │   ├── ProductRepository.php
            │   │   └── ResourceModel
            │   │       └── Category.php
            │   └── view
            │       ├── base
            │       │   ├── layout
            │       │   │   └── default.xml
            │       │   ├── templates
            │       │   │   ├── js
            │       │   │   │   └── components.phtml
            │       │   │   └── product
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
            │       │           └── product
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
            │           └── IndexBuilder.php
            ├── module-catalog-url-rewrite
            ├── module-checkout
            │   ├── Controller
            │   │   └── Cart
            │   │       └── Add.php
            │   └── Model
            │       └── Session.php
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
            │               └── catalog_product_view_type_downloadable.xml
            ├── module-payment
            │   └── Model
            │       ├── Method
            │       │   └── AbstractMethod.php
            │       └── MethodInterface.php
            ├── module-quote
            │   ├── Api
            │   │   └── Data
            │   │       └── PaymentMethodInterface.php
            │   └── Model
            │       ├── Quote
            │       │   ├── Address
            │       │   │   └── Total
            │       │   │       └── AbstractTotal.php
            │       │   ├── Address.php
            │       │   └── Item.php
            │       └── Quote.php
            ├── module-sales
            │   ├── Controller
            │   │   └── AbstractController
            │   │       └── Reorder.php
            │   └── Model
            │       └── Quote.php
            ├── module-shipping
            │   └── Model
            │       └── Carrier
            │           ├── AbstractCarrierOnline.php
            │           ├── AbstractCarrier.php
            │           └── CarrierInterface.php
            ├── module-tax
            │   └── etc
            │       └── sales.xml
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
                        └── Cart.php




```
1. How would you design a customization that should act on every request and capture output data regardless of the controller?
2. Describe the URL rewrite process and its role in creating userfriendly URLs
3. Describe how action controllers and results function

three types of layout ?
  -  page layout (define the structure for a page)
      ex: for example one-column layout or two-column layout.
  -  page configuration (the details/meta for a particular page)
  -  generic layout (declare blocks for a particular page)

5 page layout types ?
  - empty, 1column, 2columns-left, 2columns-right, and 3columns

3 page layout types for the backend
  - (admin-empty, admin-1column, and admin-2columns-left).  


4. 2.5 DETERMINE THE STRUCTURE OF
BLOCK TEMPLATES

FINISHED

DATABASE

Describe how to extend existing entities. What mechanisms are
available to extend existing classes, for example by adding a new
attribute, a new field in the database, or a new related entity? -- stopped  
