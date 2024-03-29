## Business Catalyst for developers

Business Catalyst's open platform enables web developers of all skill levels to extend the system and build complex applications on top of our infrastructure.

This guide will run you through the core concepts you should understand before developing on Business Catalyst.

### Key concepts

The Business Catalyst platform consists of several key components which work together in rendering your sites. These are:

#### Pages

Pages are simple HTML files that control the structure of your Business Catalyst website. These can be created and edited via SFTP and Admin Console's "Develop" mode. Learn more about creating and editing pages [in this article.](http://helpx.adobe.com/business-catalyst/using/pages.html)

Once created, you can add dynamic content to your pages using Modules. 

#### Modules

Modules reflect dynamic functionality that you can insert on your pages, such as an online shop, a blog, photo gallery, and more. Modules are inserted using the following syntax: `{module_blogpostlist,ID,count,tag}` - with the parameters such as `ID`, `count` and `tag` replaced with you how you'd like the Module rendered.

Business Catalyst includes a range of pre-built Modules out of the box, but you can easily build your own custom Modules using our "Web Apps" feature.

You can customize the look and feel of how Modules are rendered using Tags inside Layouts. 

For a complete list of available Modules, refer to our [Module reference guide.](/content/module-reference/index.html)

#### Tags

Tags are used inside Layouts or Module Templates to structure the data rendered by a Module. For example, the `{module_announcement}` Module by default uses the "News List Layout". 

Layouts are simple HTML files contained in the file system of your site. The default "News List Layout" can be found at ` /layouts/announcement/list.html` and contains the following HTML:

~~~
<div class="announcement-list">   
	<h2>{tag_subject}<span class="date">{tag_eventfromdate}</span></h2>      
	<p>{tag_body, 100}</p>  
</div>    
~~~

As you can see, Tags render specific data for each item. For example, `{tag_subject` outputs the subject of the current New items. This list template would be looped through for each News item that exists. 

Some Modules allow you to define custom Layouts or Module Templates, giving you an unlimited number of usable layouts. 

For a complete list of available Tags and the layouts they can be used in, refer to our [Tag reference guide.](/content/tag-reference/index.html)  

### Extending Business Catalyst

You can extend Business Catalyst's default functionality using a range of available APIs, and customize the Admin Console your clients see using the Open Admin feature. 

#### APIs

Using our SOAP and RESTful APIs, you can interact with the system and create custom applications on top of the Business Catalyst infrastructure.

To get started, refer to our [Getting started with APIs guide.](/content/developer-guides/APIs/getting-started-with-apis.html)

You can also find a full list of supported API methods in our [API reference guide.](/content/API-endpoints/index.html)

#### Open Admin

Open Admin allows you to easily customize the Admin Console menu your clients see using JSON files. This allows to create a tailored user experience for clients and build custom Admin interfaces for managing their site. 

To get started, refer to our [Getting started with Open Admin guide.](/content/developer-guides/open-admin/getting-started-with-open-admin.html)

