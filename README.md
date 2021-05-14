# jee8-bom

A BOM to chain JEE8 projects

## Searching for updates

    mvn clean site:site site:stage-deploy -DstagingSiteURL=file:///tmp/mysite -DtopSiteURL=https://www.ds-2.de/ -Pno-repo-man,with-version-updates-report
