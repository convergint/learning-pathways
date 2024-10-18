# Convergint learning pathways

This is a custom content pack served by GitHub Pages from a repository forked from [https://github.com/pnp/custom-learning-office-365](https://github.com/pnp/custom-learning-office-365). The content pack allows customizations to Categories, Technologies, and other lists that aren't configurable in the administration web part.

[Learning pathways](https://1651wilkening.sharepoint.com/sites/M365LP/) is a SharePoint application for organizing training assets (pages) into playlists, viewable within a web part on any SharePoint page in the tenant. 

This application serves as a lightweight Learning Management System (LMS) alternative, delivering easily accessible training and communication content to colleagues.

Application installation and maintenance is handled by Convergint SharePoint Administrators 

# Useful links and references

Microsoft Learn documentation. Configurations schema is in the “Partner“ section. 

[Overview of Microsoft 365 learning pathways](https://learn.microsoft.com/en-ca/office365/customlearning/)

## In-app configuration

| Property | Value | Notes |
| --- | --- | --- |
| Content Pack Id/Partner Id | a3899658-4f97-420b-8119-dcd5f583f533 | Automatically generated when content pack is added. |
| Display name | Convergint learning pathways | Used in viewer webpart to select which content pack to draw assets from |
| Base URL | https://github.com/convergint/learning-pathways | This is the base GitHub Pages URL. It’s published from the root of the /Docs directory in the repo. |

# Configuration backup

M365LP stores tenant configuration in Lists on the site. [A Power Automate flow](https://make.powerautomate.com/environments/Default-2b4de1bd-251e-4878-bdb8-5180f7d15525/flows/shared/c6d9dcd9-ba64-4d28-8514-d55cb942abe0/details) copies select items from those lists and deposits them in lists on the [OCM SharePoint site](https://1651wilkening.sharepoint.com/sites/OCM) as a precaution.

CSV backups of the list are troublesome because the JSONData column contains JSON data 🤯 that doesn’t play nice with comma separation without tedious manipulation of the data that would complicate restoring from backup.

The Power Automate flow is owned by the OCM group and runs with @chambers connection to SharePoint.
