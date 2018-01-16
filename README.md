# INFO
Command line utility for converting text files encoding


## Usage

`java -jar encoder.jar -i <input-file> -ic <input-file-encoding> -o <output-file> -oc <output-file-encoding>`


## Example
`java -jar encoder.jar -i test.txt -ic MIK -o test.utf8.txt -oc UTF-8`

[Read more about MIK and Pravetz 16](https://en.wikipedia.org/wiki/MIK_(character_set))

# Release
1. Change maven settings.xml and add account for OSSRH
```<settings>
  <servers>
    <server>
      <id>ossrh</id>
      <username>your-jira-id</username>
      <password>your-jira-pwd</password>
    </server>
  </servers>
</settings>
``` 
More information can be obtain from [OSSRH guide](http://central.sonatype.org/pages/ossrh-guide.html) and [Maven configuration](http://central.sonatype.org/pages/apache-maven.html)

1. `mvn clean install`

1. Remove -SNAPSHOT from the version in pom.xml file. Commit the changes and create new tag with the version. (optionally push to github)

1. `release.sh mysecret-password-for-gpg`

1. Go to [https://oss.sonatype.org/#stagingRepositories](https://oss.sonatype.org/#stagingRepositories) find the staging repository from the previous step and click release

1. Add -SNAPSHOT to pom.xml file and increase the version (e.g. 1.0.0 to 1.0.1-SNAPSHOT). Commit and **push** the change
