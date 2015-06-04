#Bidvest insurance Site Specification

This document serves to outline the required deliverables for the Bidvest Insurgance Group Website

Bidvest insurance has tasked Sugar to prepare a proposal regarding the development of a new website for the business.The current website has certain structural issues that are preventing it from being found in the search engines.The remit for this proposal is the following
* Improve the layout of the site to better assist in the conversion of visitorsinto leads for the call centre.* Display Bidvest Insurance’s social campaigns, it’s corporate responsibilityin a complementary manner
* Provide a resource for all agents of the business, be it brokers, dealersand others* Provide a repository of information that will enable clients to find what they are looking for quickly.* Fix the inherent SEO problems with the old site.* Provide a base for online transactions further along the line.

##Site Structure

We are obtaining two servers with LAMP architecture within Bidvest Firewalls

* We will need to install and configure WP
* We will need to harden it for security
* We will need to ensure the website performs to the agreed minimums of 
* Performance Grade 90%, page requests under 50, load time under 2 seconds, and page size of under 1MB.
* We will use gravity forms for the form submissions.
* All form submissions will need to open in unblockable modal windows.
* We will use Wordpress as it is intended with pages for static pages, posts, for blog posts, and create custom post types for products, in order to future proof the installation, and make it user friendly.
* A number of page templates will need to be created.
* Key client expectation are the site will not go down, and if does we have multiple quickly accessible back ups that we can bring online very quickly.
* The site will need tone responsive and work on all modern smartphones. We have designed pages that fall back gracefully into  tablet view and mobile view.
* We will need to load as many scripts in the footer and via CDN if possible to increase speed of the website.
* Conditional plugin loading on a per page basis

#Project Plan

##Content

We have begun sourcing content and have already installed it on http://bidvestinsurancegroup.sugarclients.co.za. 

We will continue to optimise this content while development occurs. This allows us two streams of work. Once the development site is up and running we will export this content direct into the new website using wordpress xml, and then configure as we need to.

We are gathering existing site content, and then optimising it for SEO.

The client has access to this site and is making edits and changes to content as we progress.

##Plugins

We should only install plugins we need to.

* ACF
* Gravity Forms
* Yoast SEO
* W3 Total Cache

We should also only conditionally load certain plugins on the pages that require them as per these articles.

[http://customcreative.co.uk/conditionally-loading-plugin-scripts-in-wordpress/](http://customcreative.co.uk/conditionally-loading-plugin-scripts-in-wordpress/)
[http://www.organizedthemes.com/loading-scripts-conditionally/](http://www.organizedthemes.com/loading-scripts-conditionally/)

##Site Template Map

* Home Page
* Product Template
* Contact Us Template - Specced
* Blog Template
* Blog Category Template
* Blog Single Post Template
* Page Template

##Sitewide Elements

Overall the site will be full width with the content grid being set to 1280 by 760 screen resolution.

#Inclusions

* FontAwesome Icon font - We will be using the icons throughout the website, so using an icon font makes sense. 

####Icon Values

* Warranty - fa-cogs
* Bodyguard- fa-automobile
* Tyre guard - fa-warning
* Theft buster - fa-user-secret
* Motor & Home - fa-home
* Shortfall - fa-money
* Auto-settlement - fa-group
* Travel Insurance - fa-plane

####Social icons

* Facebok - fa-facebook-f
* Twitter - fa-twitter
* Youtube - fa-youtube
* Linkedin - fa-linkedin 
* Google-plus - fa-google-plus

###Top Menu

This has been removed.

###Main Menu

The main menu will contain the main menu, with these being either headings or click through to various pages. This will need to be managed from the backend.

The menu's will have drop down options with headings that will then group the links to the pages underneath them. This will need to be arranged with columns. 

I have made examples of how the menu will need to look. Basically under each topic, the menu options will need to be aligned.

The menu will drop down full width as in this example here

[https://www.hollard.co.za/](https://www.hollard.co.za/)

Other examples are here

* [http://codepen.io/patskot/pen/sumop](http://codepen.io/patskot/pen/sumop)
* [http://geedmo.github.io/yamm/#](http://geedmo.github.io/yamm/#)	

Sketch Mockups of each menu are included in the mockup file.

Insert Image here

###Footer

The footer will be full width and will be divided into 4 column, basically 1/2/1 with custom menus ; so they can be easily managed from the backend. 

It will also contain image sprites of social icons that will be used across the site in various colours. The social icons will also be sourced from Font Awesome, so perhaps

Thee will contain links to the various pages improving SEO.

###Sub footer

This is the final footer and will contain site info and an image.

Please ensure that this footer remains "sticky" to the view port.

Mobile Considerations

On tablets the footer will remain as is, however on narrower portrait, mobile screens we will not show these footer links ( products, who we are etc)

###Breadcrumbs

We need to have breadcrumbs on each page to improve the SEO of each page and the User Experience.

##UI Touches

* Can we add to home screen, as per this article?
* [http://webdesign.tutsplus.com/articles/quick-tip-give-your-website-an-ios-home-screen-icon--webdesign-10067](http://webdesign.tutsplus.com/articles/quick-tip-give-your-website-an-ios-home-screen-icon--webdesign-10067)
*  

##Forms , Conversion, Post Sale

Key to the ongoing relationship with SUGAR and Bidvest will be on site conversion. I need to be able to track as much as possible, and have that data for analysis.

To that end, and for simplicity's sake, we have chosen gravity forms, but we will use it to post data to a table on the database, or even a separate database. 

When the gravity form submits, we need to track UTM data if present and GCLID data, and save that with the lead record.

* [https://github.com/medius/utm_form](https://github.com/medius/utm_form)

Once the form has been submitted, we need to show a modal response that is generic across the website.

Once a lead has been submitted, it will need to go into the database, and then have a scheduled task of every 10 minutes posting the product to 2 API's. 

Then we will need to send a response email to the client, using knowitfy.io to ensure deliverability and that it does get there.

The choice of API will be determined by the product. I would like to gather as much information as possible and host it, then only post what is needed to the relevant API.

I have requested the details on the API numerous times, and I have got this response.

I have attached a web service link which we will use going forward to feed the system with live leads. We have added the additional fields as requested by Bidvest. Can we start testing the service with additional fields. Please also share with other lead providers.
 
Below is the Web service Details:
 
Service url:  http://leadservice.ics.co.za/AddLeads.svc/InsertLead  
Method: InsertLead
Input JSON Format :  
{"CustomerKey":"BFC8BEC3-405B-E311-8B05-40618694EEE1","Title":"MR","Name":"donotcall,donotcall","ContactNo":"0726167863","Email":"donotcall@donotcall.do","Source":"Website","Product":"Funeral Plan","HomeContactNo":"0120098765","WorkContactNo":"0115680092","Gender":"F","PostalAddress1":"1 Jean Ave","PostalAddress2":"Centurion","PostalAddress3":"Pretoria","PostalCode":"0123","IDNumber":"8007081234089","ResidentialAddress1":"1 jean ave","ResidentialAddress2":"Centurion","ResidentialAddress3":"Pretoria","ResidentialPostalCode":"0123"}
Output JSON:  {"InsertLeadResult":"Lead is added successfully."}

###Optional

##Contact Template

The contact template will be used on two pages, directly accessible from the main menu bar.

These will have a full width google amp with a custom address icon.

I have found a plugin / tutorial  that will do this, how we need it to work.

####Plugin

[https://premium.wpmudev.org/project/wordpress-google-maps-plugin/](https://premium.wpmudev.org/project/wordpress-google-maps-plugin/) - Issue with this is the ongoing subscription fee?

####Tutorial

[]http://webdesignledger.com/tutorials/how-to-add-a-color-tinted-full-width-google-map-in-wordpress](http://webdesignledger.com/tutorials/how-to-add-a-color-tinted-full-width-google-map-in-wordpress)

I'm leaning towards this, as we can code it once and be done with it, and not worry about updates.

####Contact Form

This contact form will need to gather the standard information fields, and route the notification using the gravity forms standard process. I'm concerned about having to change the email notification, and how gravity forms mangles the HTML on occasion. I do like how gravity forms keeps a copy of the message though.

####Email Response

If we are using Knowtify.io, should we build the various templates within the interface to speed up time?

##Product Template

The product template is the next most important part of the entire website.

The website needs to covert customers, and this is where that will happen.

The page is basically laid out  in 70/30 split and will need to be a custom post type, and have its own sidebar. We will need to set SEO options on these

Within the page, we should, make heavy use of custom fields to ensure the pages are complete when we add new products, and to make it as bulletproof as possible.

The client wants to use accordions that open and close on click to hide and show content. Once clicked they must remain open though.

Require fields

* Product Title = Page Title
* Product Detail
* Product How It Works
* 