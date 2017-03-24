# LDL Overview

## What is the Louisiana Digital Library (LDL)?

The Louisiana Digital Library (LDL) is an online library containing photographs, maps, manuscript materials, books, oral histories, and more that document history and culture. Libraries, museums, archives, historical groups, and other institutions across the State contribute materials to the LDL.

The LDL is an instance of Islandora, an open source digital library system based on Fedora Commons, Drupal, Solr/Lucene and other applications.

## Purpose of this documentation

This documentation is aimed at site collection administrators and collaborators. 

Another set of documentation will be written for public users and yet another set for the LDL Development Team *(yet to be written as of March 2017)*.

### Where to find other documentation

Detailed documentation about the Islandora software can be found at [Islandora Documentation](https://wiki.duraspace.org/display/ISLANDORA/Islandora).

FLVC maintains excellent documentation as a publicly available wiki at [FL-Islandora Guides](https://fig.wiki.flvc.org/wiki/index.php/Main_Page).

## LDL Governance and Development

The LDL is governed by the Louisiana Digital Consortium. The LDL Steering Committee serves as an advisor to provide feedback and set priorities for the LDL Development Team.

### Louisiana Digital Consortium

The Louisiana Digital Consortium (LDC) is a partnership of participating Louisiana libraries, museums, archives and cultural heritage institutions. The purpose of the LDC is to be the Louisiana entity under which a variety of digital initiatives and services and cooperative programs are developed and or sponsored. The LDC provides governance and leadership to ensure the effective operation, orderly growth and fiscal sustainability of the Louisiana Digital Library and other cooperative programs. 

There are currently 22 participating libraries, archives, museums, and historical centers participating in the LDL. Each institution contributes the digital items and the descriptive text for their collections. You will find that some of the collections, such as the GUMBO Project and the Teaching History in Louisiana Project, are collaborative projects that include materials from many institutions. 

#### Executive Board

Chair: Lora Amsberryaugier, UNO   
Vice-Chair: Diane Brown, State Library   
Immediate Past Chair: Carol Bartels, HNOC   
Treasurer: Debbie Sibley, LSUHSC – NO   
Secretary: Jeff Rubin, Tulane   
At Large: Deborah Poole, Loyola   
At Large: Gina Costello, LSU   

[LDC Bylaws](http://www.louisianadigitallibrary.org/ui/custom/default/collection/default/resources/custompages/home/LDC_Bylaws_rev20151112.pdf)   
[LDC Membership Form](http://www.louisianadigitallibrary.org/ui/custom/default/collection/default/resources/custompages/home/LDC_membership_form2016.pdf)   
[Additional information including LDC Board Meeting Minutes can be found here](http://www.louisianadigitallibrary.org/index.php?browseby=about)      
 *note: the above links will need to be updated when the LDC site is moved/reconfigured in summer 2017*

#### LDL Steering Committee

The LDL Steering Committee works closely with the LDL Development team to ensure that the new Louisiana Digital Library has the features and look that the LDC membership wants. 

The charge of the LDL Steering Commitee is to:

* Develop short and long-term goals for Islandora technical implementation and the website redesign
* Prioritize product feature development and releases
* Provide feedback to the LSU Development Team about new features and site changes
* Attend monthly product review meetings with the LSU Development Team in person or via web conference
* Communicate with all LDL stakeholders (including the LDC Board and membership) to inform of changes and to gather feedback about new features, bugs or issues, and potential enhancements.

LDL Steering Committee members include: 

Chair: Jeff Rubin, Tulane   
Member: Charlene Bonnette, State Library of Louisiana   
Member: Gina Costello, LSU   
Member: Elizabeth Kelly, Loyola   
Member: Pati Threatt, McNeese   
Member: Kent Woynowski, HNOC   

#### LDL Development Team

The LDL Development Team consists of staff of LSU Libraries, primarily from the Technology Initiatives Team. As of the spring 2017, this includes:

Garrett Armstrong, Digital Projects Programmer, garmstrong@lsu.edu   
Dave Comeaux, Web Development Librarian, davidcomeaux@lsu.edu   
William W. Conlin, Digital Projects Programmer, wconli1@lsu.edu   
Gina Costello, Associate Dean for Technology Initiatives, gcoste1@lsu.edu   
Gabe Harrell, Digitization Lab Manager, jharre7@lsu.edu   
Cara Key, Metadata Librarian, carakey@lsu.edu   
Jason Peak, Application Development/Computer Manager, jpeak5@lsu.edu   
Kyle Tanglao, User Interface Designer, ktanglao@lsu.edu   
Mike Waugh, Systems Librarian, mwaugh2@lsu.edu 

### Migration 

Much of the development work of 2016 and early 2017 was to migrate 186 digital collections from the CONTENTdm platform to the new Islandora platform. The LDL Development Team migrated over 100,000 *(update with final count after migration is complete)* digital objects and transformed the accompanying metadata from Dublin Core to MODS.

The Extract/Transform/Load (ETL) process was facilitated by using code repositories such as [MIK, the Move to Islandora Kit](https://github.com/MarcusBarnes/mik) (developed by Marcus Barnes, Simon Fraser University), and scripts developed locally: [cDM_to_MODS](https://github.com/lsulibraries/cDM_to_mods) and [cdm_exporter](https://github.com/lsulibraries/cdm_xporter). Batch imports into Islandora were facilitated by using drush scripts.