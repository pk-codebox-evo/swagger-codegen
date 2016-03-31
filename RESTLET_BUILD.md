# How to deploy a new release to Restlet's Nexus

- Run `mvn versions:set -DgenerateBackupPoms=false`.
- When prompted for the version, enter `<version-of-swagger-codegen>.<release-number>-restlet`. For example, if your branch is based on swagger-codegen 2.1.3 and it's the second Restlet release, then the version is `2.1.3.1-restlet`.
- Commit the new POMs with the message `Release <version>`.
- Tag this new commit with `v<version>`. For example, `v2.1.3.1-restlet`.
- Push the new tag.
- Run `mvn deploy`.
- Run `mvn versions:set` again.
- When prompted for the version, enter `<version-of-swagger-codegen>.<release+1>-restlet-SNAPSHOT`. For example, `2.1.3.2-restlet-SNAPSHOT`.
- Commit the new POMs with the message `Prepare next development version`.
