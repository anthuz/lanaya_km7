#Lanaya
Lanaya is a PHP framework created by Andreas Thuresson. Lanaya is based on another framework called Lydia, created by Mikael Roos. Lydia can be found at: https://github.com/mosbth/lydia

##Downloading
To clone lanaya use the following command: `git clone git://github.com/anthuz/lanaya_km7.git`

##Installing
First you have to make the data folder writeable. The data folder contains all the database information in Lanaya. To make the folder writeable write:  
`cd lanaya; chmod 777 site/data`
	

###.htaccess
The Rewrite option must be changed if you want to run Lanaya from another directory than root on a web server. Simply remove the comment tag and link to the Lanaya directory.
`RewriteBase /change/this/to/Lanaya/folder`
	

###Initialize modules
The modules in Lanaya is used for the user, content and guestbook. You need to initialize them by entering the following link:
`modules/install`
	
##Configuration
The configuration file can be found in the folder `site/config.php`. It contains information for controllers, themes, menues, routing, footer, etc...

### Add a controller
To add a controller you have to change the controllers array in config.php. This is an example of adding a contoller:
`'example' => array('enabled' => true, 'class' => 'CCExample'),`

This will make it possible to reach the controller from `lanaya_km7/example`. The PHP file must use the name CCExample and you can choose to enable or disable the controller.

###Add a menu
Create a new array inside the "menus" array in the configuration file. The name of your menu will be used inside the "theme" array to add the menu.

	'examle-navbar' => array(
	  'about'     => array('url'=>'my', 'label'=>'About Me'),
	  'blog'   	=> array('url'=>'my/blog', 'label'=>'My Blog'),
	  'guestbook'	=> array('url'=>'my/guestbook', 'label'=>'My Guestbook'),
	),

This will create a menu with the tabs about, blog and guestbook. To this menu to the site you have to change the value of **menu_to_region** in the theme array. Change it to:
`'menu_to_region'  => array('example_navbar'=>'nav'),`

**nav** is the name of the div element for the element so do not change that. Only change the first value in the array.

###Routing
You can create your own links to a controller by changing the values inside the rouing array. Example:
`'home' => array('enabled' => true, 'url' => 'index/index'),`

The link `lanaya_km7/home` will now point to the controller index and the method index.

##How to create a controller
Look at the example `https://github.com/anthuz/lanaya_km7/tree/master/site/controllers/CCMycontroller/CCMycontroller.php`.