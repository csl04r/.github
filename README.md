# .github
This is github actions template repo  

# Available self-hosted runner labels 
sw-ubuntu-latest  
sw-windows-latest

# gradle notes
You must add a step in your build.gradle to publish the artifacts.  
```
  // you must add this publishing block to your build.gradle 
       publishing {
         repositories {
             maven {
               name = "artifactory"
               url = "https://artifactory.sherwin.com/artifactory/sherwin-release-local"
               credentials {
                 username = System.getenv("ARTIFACTORY_USERNAME")
                 password = System.getenv("ARTIFACTORY_API_KEY")
               }
             }
```
# maven notes  
If going to dev-sherwin-release-apps, you must add this parent block in pom.xml
```
<parent>
		<groupId>com.sherwin.parent.devsherwinreleaseapps</groupId>
		<artifactId>pom</artifactId>
		<version>1.0</version>
	</parent> 
```
If going to sherwin-release-local, you must add this parent block in pom.xml
```
<parent>
		<groupId>com.sherwin.parent.sherwinreleaselocal</groupId>
		<artifactId>pom</artifactId>
		<version>1.0</version>
	</parent> 
```
