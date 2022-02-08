# DS/2 JEE Bill of Materials

A BOM to chain JEE projects.

Website should be here: <https://ds2-internal.gitlab.io/jee8-bom/> or here: <https://ds2.github.io/bill-of-materials/>

## Searching for updates

    mvn clean site:site site:stage-deploy -DstagingSiteURL=file://$(pwd)/public -DtopSiteURL=https://www.ds-2.de/

## Using the BOM

### Maven

Add this snippet to your project's pom.xml:

    <parent>
        <groupId>ds2.bom</groupId>
        <artifactId>jee9-web</artifactId>
        <version>1.0.0</version>
    </parent>

Now you can add your dependency via:

    <dependency>
        <groupId>commons-codec</groupId>
        <artifactId>commons-codec</artifactId>
    </dependency>

### Gradle

Add this dependency to your project:

    implementation(platform("ds2.bom:jee9-web:1.0.0"))

Now you can add your dependency via:

    implementation("commons-codec:commons-codec")

Check via

    ./gradlew -q dependencies --configuration compileClasspath

## Perform a release

You must be on the releases branch. Then run:

    mvn -B release:clean release:prepare -DdevelopmentVersion=1.0.0-SNAPSHOT -DreleaseVersion=1.1.5 -DdryRun=true

Gitlab will perform the live rollout of the version.
