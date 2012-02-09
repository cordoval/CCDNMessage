CCDNMessage Message Bundle(s) README.
=====================================


Notes:  
------
  
This bundle is for the symfony framework and thusly requires Symfony 2.0.x and PHP 5.3.6
  
This project uses Doctrine 2.0.x and so does not require any specific database.
  

This file is part of the CCDNMessage MessageBundle

(c) CCDN (c) CodeConsortium <http://www.codeconsortium.com/> 

Available on github <http://www.github.com/codeconsortium/>

For the full copyright and license information, please view the LICENSE
file that was distributed with this source code.


Dependencies:
-------------

1. [PagerFanta](https://github.com/whiteoctober/Pagerfanta).
2. [CCDNComponent BBCodeBundle](https://github.com/codeconsortium/BBCodeBundle).
3. [CCDNComponent CrumbTrailBundle](https://github.com/codeconsortium/CrumbTrailBundle).
4. [CCDNComponent CommonBundle](https://github.com/codeconsortium/CommonBundle).

	  
Installation:
-------------

1) Download and install the dependencies.
    
2) Create the directory src/CCDNMessage in your Symfony directory.
  
3) Add the MessageBundle to CCDNMessage directory.  

4) In your AppKernel.php add the following bundles to the registerBundles method array:  

	new CCDNMessage\MessageBundle\CCDNMessageMessageBundle(),    
	  
5) In your app/config/config.yml add:    

	ccdn_message_message:  
	    user:
	        profile_route: cc_profile_show_by_id
	    template:
	        engine: twig
	        theme: CCDNMessageMessageBundle:Form:fields.html.twig
	    folder:
	        messages_per_page: 40
	        layout_templates:
	            show: CCDNComponentCommonBundle:Layout:layout_body_left.html.twig
	    message:
	        layout_templates:
	            compose: CCDNComponentCommonBundle:Layout:layout_body_left.html.twig
	            show: CCDNComponentCommonBundle:Layout:layout_body_left.html.twig


6) In your app/config/routing.yml add:  

	message:  
	    resource: "@CCDNMessageMessageBundle/Resources/config/routing.yml"  

7) Symlink assets to your public web directory by running this in the command line:

	php app/console assets:install --symlink web/

Then your done, if you need further help/support, have suggestions or want to contribute please join the community at [www.codeconsortium.com](http://www.codeconsortium.com)
