
// How to use grunt in Magento 2?
https://aureatelabs.com/magento-2/how-to-use-grunt-in-magento-2/

// to compile js using grunt
grunt clean: This command removes static files related to your theme in both pub/static and var directories.
grunt exec: This one republishes source files symlinks to pub/static/frontend/<Divante>/<rapid>/<locale>.


grunt less: This command compile all the css file using the symlinks in this location pub/static/frontend/<Vendor>/<theme>/<locale>
grunt watch: This command is used to start the grunt tool to track the changes done in the main files like .less and re-compiles into CSS files. Every time you change any of this in the source file, grunt watch will show notification in the terminal about the specific change and recompiles the changes simultaneously.
