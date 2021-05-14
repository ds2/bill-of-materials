# jee8-bom

A BOM to chain JEE8 projects.

Website should be here: <https://ds2-internal.gitlab.io/jee8-bom/>

## Searching for updates

    mvn clean site:site site:stage-deploy -DstagingSiteURL=file://$(pwd)/public -DtopSiteURL=https://www.ds-2.de/
