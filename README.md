## KPATHS Swagger Codegen Utility
This utility will generate a collection of  [Angular](https://angular.io/) `5.0+` librarie projects that will be staged in the CCCS repository for upload to the secure, Nexus repository for consumption in the `Kpaths-ui` project. There are many additional features this utility provides about what the Swagger Code Generation provides by default. 

### Key features

1. Multiple Projects: Generation of multiple projects simultaneously

2. Version Bumping: Automatically bump the version of each time a new build is generated (active components)

3. Gradle: [Gradle](https://gradle.org/) Gradle build script and configurable wrapper

4. Documentation: [Compodoc](https://compodoc.github.io/website/guides/getting-started.html)

5. Templates: Templates for additional project configuration, formatting and functionality

6. Packaging & Consumption: Easily package and create `.tgz` (Tarball files) for easly consuming in local projects

7. Beautifying Swagger Specification Files: Easily read or validate Swagger Specification files downloaded locally

8. Component Project Details: Index.html manifest detailing project information & dependencies

9. Future Capability: There is much more room for extending the capabilty of this script

## Configuration

### Configuration Properties
Located inside the `Configuration` folder is file named `kpaths-swagger-config.json`. Listed below is a list of configurations that can be set from various properites for updating the functionality of the `KPATHS Swagger Codegen` utility.

### Building with Gradle

To build an compile the typescript sources to javascript use:
```
./gradlew generateCode

```

#### To include the Gradle Wrapper in Generated Component build:
( location `config.gradle` )

``` 
  "gradle": {
            "includeWrapper": true
        }
``` 

#### To update the component version:
( location `config.kpaths` )

```
 bumpVersion: `true`
 bumpVersionStep: `patch` \\ patch, minor, major

```

#### To update the component details:
( location `config.kpaths.componentList` )

```
// Note: Setting `active` to false will exclude the component from being generated

"componentList": [
                {
                    "key": "booking",
                    "title": "Booking",
                    "endpoint": "http://my-endpoint/api/v2/api-docs",
                    "version": "1.0.0",
                    "active": true 
                }]

```

#### To update the build directories:
( location `config.swagger.dir` )

``` 
 "dir": {
            "root": "build/swagger",
            "clientApi": "build/swagger/clientApi",
            "clientSpec": "build/swagger/clientSpec",
            "deployment": "build/swagger/deploy"
        }

```

#### To update the template directories:
( location `config.templates.dir` )

``` 
"dir": {
            "clientRoot": "templates/client-root",
            "clientSrc": "templates/client-src",
            "clientSrcLib": "templates/client-src-lib",
            "clientSrcApp": "templates/client-src-app",
            "project": "templates/project",
            "gradle": "templates/gradle-wrapper",
            "deploy": "deploy"
        }

