# Faculty Directory - with jQuery Datatables

This package contains all the basic code that is needed to add a simple Faculty Directory to your site. This code is intended to be added to an existing implementation or the starter package, which includes standard OU code skeleton files, such as common.xsl and other shared XSL files. This solution, while created for faculty, could also function as a directory for generic profiles or staff listings. 

## Overview

The Faculty Directory code provided in this package provides a simple, XSL-based solution that allows for easy creation and maintenance of a faculty directory, consisting of a number of profile pages and a listing page that aggregates the information from each individual profile page into a consolidated list. This solution ensures the profiles all follow a standard layout that remains consistent across each profile and pulls them together as a whole. In addition, this makes it possible to easily grab important information for display on a listing page. 

This package provides code for a listing page that will utilize the jQuery DataTables library by default. With some XSL knowledge, it is possible to adjust this code to output other custom HTML structures and their supporting code. 

Once this package is implemented, you will be able to easily create profile, modify, and delete profile pages in a special Faculty Directory section. Through XSL, you will then be able to aggregate them automatically into a listing page for display and easy navigation within the directory. 

## End User Workflow

Once it is implemented, the basic process to create a faculty directory is as follows:

### Step 1: Use the included template to create a new profile section, where the faculty directory will live. 

The profile section template will create a new folder, with the standard _nav.inc and _props.pcf files. The main listing page for the faculty directory will also be created as the index page. 

### Step 2: Begin creating the profile pages.

Use the New Page Wizard to create the individual profile pages. Each page should then be populated with the appropriate information. In particular, the MultiEdit fields are important in order to standardize the output that will be aggregated into the listing page. 

### Step 3: Publish all unpublished or modified profile pages. 

This is a very important step in the process. Publishing each profile not only publishes the profile's page, but also an individual XML data file containing the information that will be aggregated into the listing page. **Unpublished profiles will NOT appear in the directory listing.** 

### Step 4: Publish/Republish the listing page. 

Since this solution utilizes XSL to aggregate the profile data files, the listing page must be published after a profile is modified and published. When published, the listing page will scan all published XML files in the directory and aggregate them into the listing. If a profile is not published, this scan will not see that profile and it will be omitted from the listing. 

If you anticipate a lot of changes to the profiles, the listing page can be set on a scheduled publish to "refresh" the data periodically. If the updates are more infrequent, than a manual publish of the listing page after a change or set of changes may make more sense. 

## Components

The Faculty Directory solution consists of the following components:

File | Required | Description
---- | -------- | -----------
helper.xsl | YES | Helps the profile.xsl.
profile-xml.xsl | YES | Generates the xml output of your profiles, be sure to call this file in your PCF.
profile.xsl | YES | Where the magic happens.
_profile_section.tcf | YES | Creates a new profile section, update as necessary.
profile.tcf | YES | Starts the creation of a new individual profile page.
profile.tmpl | YES | Finalizes the individual profile creation process, creates a MultiEdit page for each profile.  Suggestion would be to base this off an existing template in the site and copy over the profile node with the MultiEdit.
profile_landing.tmpl | YES | Creates the profile landing page to list the profiles. From the _profile_section.tcf.

#### jQuery dataTables

* [https://datatables.net/](https://datatables.net/)
* [https://github.com/DataTables/DataTables](https://github.com/DataTables/DataTables)

