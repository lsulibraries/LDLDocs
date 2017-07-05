# LDL technical structure

The Islandora LDL site is at http://ldl.lib.lsu.edu, although when the migration is complete and CONTENTdm is abandoned, it is expected that the domain will be changed to http://www.louisianadigitallibrary.org, which is the address of the CONTENTdm hosted site. 

## Infrastructure

Islandora refers to a suite of open source applications. Digital objects and metadata are stored in an instance of [Fedora Commons digital repository system](http://www.fedora-commons.org/). The front end display is provided by [Drupal](https://www.drupal.org/), a content management system used for many websites, including [LSU Libraries' website](http://lib.lsu.edu). Search is handled by [Apache Solr](https://lucene.apache.org/solr/). More information about the software framework of Islandora is provided in the [Islandora documentation](https://wiki.duraspace.org/display/ISLANDORA/About+Islandora).

### Cloud hosting

The LDL is hosted on Amazon Web Services (AWS), an industry standard web services platform. This provides the LDL with a responsive, reliable, secure, and scalable environment that is also cost-effective. Due to the distributed nature of the AWS cloud, multiple copies of any application or object exist.

### Backups

Backups are automated through AWS. Database, application, and application data (Fedora objects) are backed up nightly. Database backups are taken and managed by Amazon RDS. On the application server, each data volume is snapshotted each night, invoked in a cron-like way from Amazon CloudWatch.

### Namespace and PID

Items in the LDL have a persistent URL that consists of a namespace and a PID. The namespace is collection based, and the second is the collection code. Collection codes were retained from the CONTENTdm instance of the LDL. The PID is a system generated number that is unique to the namespace. If an object is deleted and recreated, a new PID is generated, so care should be taken when editing existing objects.

Here's an example:

`http://louisianadigitallibrary.org/islandora/object/lsu-p15140coll12%3A192`

`http://louisianadigitallibrary.org/islandora/object/[institution code]-[collection code]%3A[PID]`

LDL main domain = louisianadigitallibrary.org   
institution code (first half of namespace) = lsu   
collection code (second half of namespace) = p15140coll12   
thus the namespace is the institution code+collection code, separated by a dash = lsu-p15140coll12   
URL-encoded code for colon ":" = %3A   
PID = 192   


### Branding and institution pages

Permissions and branding 


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

