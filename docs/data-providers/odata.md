---
title: OData
page_title: OData - Data Providers - Kendo UI Builder
description: "Use the available OData service which is supported by the Kendo UI Builder tool for creating and managing Angular and AngularJS-based web applications."
slug: odata_kuib
position: 3
---

# OData

[OData (Open Data Protocol)](http://www.odata.org/getting-started/basic-tutorial/) is a standard for specifying REST endpoint services.

The Builder supports:
* OData version 4 for Angular.
* OData versions 2, 3, and 4 for AngularJS.

## Adding OData Providers

1. On the Dashboard, click the card (or list item) of the application to open the **App Design** page.
1. On the **App Design** page, click **Add Data Provider**. As a result, the **Add Data Provider** dialog box appears.
1. Select among the **OData**, **Generic REST**, and **Progress Data** data providers.
1. In **Name**, provide the name of the data provider.
1. In **Service URI**, enter the URI of the data provider.

4. Enter the root URI of the data provider:
* For a Progress Data Provider, this a Service URI. When accessing an OpenEdge Data Object Service, this is the URI of the web application, which hosts and represents the root URI of the Data Object Service. When accessing a Rollbase Data Object Service, this is the root URI of the Data Object Service on a Rollbase server. For example, your service URI might look something like http://Your-IP-Address:8980/MyDataWebApp.
* For an OData Provider, this is also a Service URI, which is the root URI of the OData Service. For example, http://Your-IP-Address:8980/OData/Inventory.svc.
* For a Generic REST Provider, this is a Base URI, which is the root URI of a REST Service. For example, http://Your-IP-Address:8980/api.
5. Click Test Connection to verify that the specified service is live.
6. For a Progress Data Provider only, enter the Catalog URI. This is the URI of the Data Service Catalog file generated when the Data Object Service is built and deployed on the server. For an OpenEdge Data Object Service, see the help system in Progress Developer's Studio for OpenEdge (PDSOE) for more information.
Note: In this release, the specified catalog must be unprotected at design time. If the Catalog URI specifies a protected URI, you must use the Enable Local Catalog option to specify an unprotected catalog file for design-time access, as described in the next step.
7. (Optional) For a Progress Data Provider only, select Enable Local Catalog if you want to use a local catalog file at design time. This allows you to browse for a catalog file to use on your system, which is then saved as part of your meta-data. Note that at run time, the Catalog URI is always used.
Note: Once entered and saved, the Provider Type, Name, Service URI, and Catalog URI of a data provider cannot be further edited in the Designer. However, after you publish a deployment build, you can change both the published Service URI and Catalog URI in the generated build settings. For more information on app generation and deployment builds, see Kendo UI Builder by Progress: Modernizing OpenEdge Applications.
8. (Optional) For a Progress Data Provider or an OData Provider only, you have the option to manually create data sources after you have finished creating your data provider. However, you can also select Auto-create Data Sources to allow the Designer to automatically generate your data sources based on the defined resources. A data source corresponds to a single table found in a data provider. For a Progress Data Provider, a data source is created using the schema definition in the catalog. For an OData Provider, a data source is created from a request to the Service URI for meta-data. When Auto-create Data Sources is selected, data sources are automatically generated for each of the following cases, given that the resource is enabled for at least one CRUD operation:
* A single table: A data source is created using the resource name of the table from the catalog file.
* For an OpenEdge Data Object Service only, a ProDataSet with a single, top-level table: A data source is created using the resource name of the top-level table from the catalog file
* For an OpenEdge Data Object Service only, a ProDataSet with more than one top-level table: A data source for each top-level table is created with the following naming convention: ProDataSet_resource_name + "." + table_name
Note: For a Generic REST Provider, this option is not available, and you must create its data sources manually.
9. (Optional) For an OpenEdge Data Object Service only, select Create Data Sources for child tables to allow the Designer to automatically generate data sources for child tables in a ProDataSet with related tables. These child table resources are created with the same naming convention as for top-level tables.
Note: You must also select Auto-create Data Sources to enable this option.
10. For a Progress Data Provider only, select the Authentication Model. This is the security model for the Service URI and Catalog URI, and it must match the authentication model of the web application (server) that provides the Data Object Service.
Click Add Data Provider to the data provider with the current settings. With one or more data providers created, you can now create data sources using these providers.





1. (Optional) Test whether the URI is working by clicking **Test Connection**.
1. (Optional) By default, the automatic creation of data sources is enabled.

  > If you uncheck the **Auto-create Data Sources** box, you will have to manually create and relate the data sources. For more information, refer to the article on [data sources]({% slug datasources_kuib %}).    

1. Depending on the data provider you selected, choose the related option from the **Authentication Type** drop-down field.
1. Click **Add Data Provider** to save the data provider properties and close the **Add Data Provider** dialog box. As a result, the **App Design** page displays the card for your new data provider with the properties you defined.


## Suggested Links
