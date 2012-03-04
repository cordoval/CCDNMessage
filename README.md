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
2. [PagerFantaBundle](http://github.com/whiteoctober/WhiteOctoberPagerfantaBundle).
3. [CCDNComponent BBCodeBundle](https://github.com/codeconsortium/BBCodeBundle).
4. [CCDNComponent CrumbTrailBundle](https://github.com/codeconsortium/CrumbTrailBundle).
5. [CCDNComponent CommonBundle](https://github.com/codeconsortium/CommonBundle).

	  
Installation:
-------------

1) Download and install the dependencies.
   
   You can set deps to include:

```sh
[pagerfanta]
    git=http://github.com/whiteoctober/Pagerfanta.git

[PagerfantaBundle]
    git=http://github.com/whiteoctober/WhiteOctoberPagerfantaBundle.git
    target=/bundles/WhiteOctober/PagerfantaBundle

[CommonBundle]
    git=http://github.com/codeconsortium/CommonBundle.git
    target=/bundles/CCDNComponent/CommonBundle

[BBCodeBundle]
    git=http://github.com/codeconsortium/BBCodeBundle.git
    target=/bundles/CCDNComponent/BBCodeBundle

[CrumbTrailBundle]
    git=http://github.com/codeconsortium/CrumbTrailBundle.git
    target=/bundles/CCDNComponent/CrumbTrailBundle

[CCDNMessageMessageBundle]
	git=http://github.com/codeconsortium/CCDNMessage.git
	target=/bundles/CCDNMessage/MessageBundle
```

add to your autoload:

```php
    'CCDNComponent'    => __DIR__.'/../vendor/bundles',
    'CCDNMessage'      => __DIR__.'/../vendor/bundles',
```
and then run `bin/vendors install` script.

2) In your AppKernel.php add the following bundles to the registerBundles method array:  

```php
	new CCDNComponent\CommonBundle\CCDNComponentCommonBundle(),
	new CCDNComponent\BBCodeBundle\CCDNComponentBBCodeBundle(),
	new CCDNComponent\CrumbTrailBundle\CCDNComponentCrumbTrailBundle(),
	new CCDNMessage\MessageBundle\CCDNMessageBundle(),
```
	
3) In your app/config/config.yml add (this is configs for all 3 forum bundles):    

```sh
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
```

4) In your app/config/routing.yml add:  

```sh
CCDNMessageMessageBundle:
    resource: "@CCDNMessageMessageBundle/Resources/config/routing.yml"
    prefix:   /
```

5) Symlink assets to your public web directory by running this in the command line:

```sh
	php app/console assets:install --symlink web/
```

Then your done, if you need further help/support, have suggestions or want to contribute please join the community at [www.codeconsortium.com](http://www.codeconsortium.com)
