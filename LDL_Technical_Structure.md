# LDL technical structure

The Islandora LDL site is at http://ldl.lib.lsu.edu, although when the migration is complete and CONTENTdm is abandoned, it is expected that the domain will be changed to http://www.louisianadigitallibrary.org, which is the address of the CONTENTdm hosted site. 

## Infrastructure

Islandora refers to a suite of open source applications. Digital objects and metadata are stored in an instance of [Fedora Commons digital repository system](http://www.fedora-commons.org/). The front end display is provided by [Drupal](https://www.drupal.org/), a content management system used for many websites, including [LSU Libraries' website](http://lib.lsu.edu). Search is handled by [Apache Solr](https://lucene.apache.org/solr/). More information about the software framework of Islandora is provided in the [Islandora documentation](https://wiki.duraspace.org/display/ISLANDORA/About+Islandora).

### Cloud hosting

The LDL is hosted on Amazon Web Services (AWS), an industry standard web services platform. This provides the LDL with a responsive, reliable, secure, and scalable environment that is also cost-effective. Due to the distributed nature of the AWS cloud, multiple copies of any application or object exist.

### Backups

Backups are automated through AWS. Database, application, and application data (Fedora objects) are backed up nightly. Database backups are taken and managed by Amazon RDS. On the application server, each data volume is snapshotted each night, invoked in a cron-like way from Amazon CloudWatch.

## Multi-site configuration

While there is a single instance of Islandora, Drupal allows for a mult-site configuration, so that each institution has its own subsite, each serving as a portal into the institution's collections. Each subsite is branded for the institution, with an eye to maintain consistent theming throughout the entire site. Subsite codes are appended as to the beginning of the primary domain as subdomains. Since the domain is likely changing from ldl.lib.lsu.edu to louisianadigitallibrary.org, the URLs listed below will change, with the subdomain staying the same (for example, hnoc.ldl.lib.lsu.edu will become hnoc.louisianadigitallibrary.org).

* http://hnoc.ldl.lib.lsu.edu
* http://latech.ldl.lib.lsu.edu
* http://loyno.ldl.lib.lsu.edu
* http://lsm.ldl.lib.lsu.edu
* http://lsu.ldl.lib.lsu.edu
* http://lsuhsc.ldl.lib.lsu.edu
* http://lsuhscs.ldl.lib.lsu.edu
* http://lsus.ldl.lib.lsu.edu
* http://mcneese.ldl.lib.lsu.edu
* http://nicholls.ldl.lib.lsu.edu
* http://nsu.ldl.lib.lsu.edu
* http://state.ldl.lib.lsu.edu
* http://subr.ldl.lib.lsu.edu
* http://tahil.ldl.lib.lsu.edu 
* http://tulane.ldl.lib.lsu.edu
* http://ull.ldl.lib.lsu.edu
* http://ulm.ldl.lib.lsu.edu
* http://uno.ldl.lib.lsu.edu

Note that while most of the subdomains refer to institutions, there may be cases where certain collaborative collections have their own subdomain, such as tahil.ldl.lib.lsu.edu

### Namespace and PID

Items in the LDL have a persistent URL that consists of a namespace and a PID. The namespace is collection based, with the first portion of it consisting of the institution code, and the second being the collection code. Collection codes were retained from the CONTENTdm instance of the LDL. The PID is a system generated number that is unique to the namespace. If an object is deleted and recreated, a new PID is generated, so care should be taken when editing existing objects.

Here's an example:

`http://lsu.ldl.lib.lsu.edu/islandora/object/lsu-p15140coll12%3A192`

`http://[institution subdomain][ldl main domain]/islandora/object/[institution code]-[collection code]%3A[PID]`

institution subdomain = lsu   
ldl main domain = ldl.lib.lsu.edu   
institution code (first half of namespace) = lsu   
collection code (second half of namespace) = p15140coll12   
thus the namespace is the institution code+collection code, separated by a dash = lsu-p15140coll12   
URL-encoded code for colon ":" = %3A   
PID = 192   


### Collection landing pages

Although it's not necessarily an "out-of-the-box" feature of Islandora, the LDL Development Team sought to maintain the collection landing pages that are used in the CONTENTdm version of the LDL. These landing pages often include a description of the collection, sometimes with additional content and/or context. Many of the landing pages include a banner image as well. From the landing page are links to the collection objects.

### Test instances

In addition to the production instance of the LDL at http://ldl.lib.lsu.edu, there is a test instance of the LDL at http://ldltest.lib.lsu.edu as well as for each institution subsite, such as http://hnoc.ldltest.lib.lsu.edu. It can be used to test out new features, new collections, or as a training instance.

The application configuration is scripted in such a way using Ansible scripts in conjuction with Vagrant and VirtualBox (open source virtualization software), so that a new, customized instance of Islandora can be created and used on one's local desktop. The LDL Development Team uses these local instances to experiment with configuration and customization.

## Theming

The theming of the LDL has been developed by Kyle Tanglao. One point of emphasis is that the site be mobile friendly and that the pages be responsive to the size of the screen.

While there is a unifying theme for the entire site, there will be custom theming available for each institution's subsite, with a custom banner and color scheme. Site administrators should contact the LDL Development Team for more information about theming options.

## Navigation features

Subsite navigation, collection navigation, and other browsing navigation will be developed in Spring 2017.

## Searching

Basic and advanced search modes are available. Search results include facets that can be chosen to further refine results. 

Searches can be limited to certain collections or subsites. *As of March 2017 - to be implemented*

