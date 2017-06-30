# Adding new collections #

--------------------------
> Work still needed on this segment: 
> 
> *	Integrate namespace helper 

--------------------------

## Create a collection container ##

1. Sign in to a collection admin account and navigate to to the Islandora Repository (`islandora:root`).

1. Click the `Manage` tab.

1. Click `+ Add an object to this Collection`.

1. Enter the Collection PID using the format *institution code, hyphen, collection code, colon, "collection"* 
	* Example: loyno-p16313coll24:collection
	* _Note: You __must__ use your established institution code in your Collection Namespace / PID!_

1. `Inherit collection policy` should be checked. `Inherit XACML policy from` should have the value "None."

1. Do not choose a MARCXML file; just click `Next`.

## Complete the Collection Metadata form ##
1. Enter the Collection Title.

1. In the LDL Collection Owner field set:
	* Type and Label attributes should not be changed.
	* Select the owning/contributing institution from the Repository drop-down list.
	* If the collection includes materials from more than one repository, click `Add`, then choose the subsequent numbered tab in the Name field block to add another repository.
	* _If the institution or sub-institution is not represented in the list, please contact LSU staff to have it added._

1. In the Type of Resource field, use the drop-down to select the type of resource that comprises the collection. If the collection includes multiple types of materials, select "mixed material."
	* _MODS will not validate without this field._

1. In the Collection ID field, enter the Collection's namespace (institution code, hyphen, collection code).
	* Example: loyno-p16313coll24

1. For new collections, please ignore the "Migrated From" field; this is for use only in collections that were migrated from CONTENTdm, for link redirection.

1. In the Collection Description, enter a detailed summary of the collection contents and/or context.
	* This is similar to former landing page's "About this collection."
	* You may use basic HTML tags to enhance the description, to add links, formatting, etc.

1. Optionally, enter miscellaneous notes in the Note field.

1. Provide contact information, including a dedicated/departmental email address.
	* A standardized contact information statement for each institution is preferred.

1. When the collection metadata is complete, click `Ingest` at the bottom of the form.