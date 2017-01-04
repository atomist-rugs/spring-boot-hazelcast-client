# Atomist 'spring-boot-hazelcast-client'

[![Build Status](https://travis-ci.org/atomist-rugs/spring-boot-hazelcast-client.svg?branch=master)](https://travis-ci.org/atomist-rugs/spring-boot-hazelcast-client)
[![Slack Status](https://join.atomist.com/badge.svg)](https://join.atomist.com)

This [Rug][rug] archive contains a Generator for a [Spring Boot][boot]
[Hazelcast][hazelcast] client project.

In Hazelcast, *client* processes connect to an existing cluster of *server* processes.
Clients are independent of other clients, don't host data as such but may keep a near-cache
local copy. Server processes are generated by a different [Rug][rug], see [Server][server].

[rug]: http://docs.atomist.com/
[boot]: https://projects.spring.io/spring-boot/
[hazelcast]: https://hazelcast.org/
[server]: https://github.com/atomist-rugs/spring-boot-hazelcast-server

## Rugs

### NewSpringBootHazelcastClient

The NewSpringBootHazelcastClient Generator creates a new [Spring
Boot][boot] [Hazelcast][hazelcast] client project.

[boot]: https://projects.spring.io/spring-boot/
[hazelcast]: https://hazelcast.org/

#### Prerequisites

There are no prerequisites to running this generator.

#### Parameters

To run this generator you must supply the following parameters.

Name | Required | Default | Description
-----|----------|---------|------------
`project_name` | Yes | |  A valid GitHub repository name.  It must be 21 characters or less to avoid truncating name when the its Slack channel is created.
`artifact_id` | No | myartifact | Maven artifact ID, e.g., "fiddle-riddle".
`group_id` | No | mygroup |  Maven group ID, e.g., "com.pany.project".
`version` | No | 0.1.0-SNAPSHOT | [Semantic version][semver] of the project.
`description` | No | Hazelcast Client | A brief description of the project.
`new_package` | No | mygroup | The package for the generated client class.
`main_class_name` | No | MyClient | Name for the generated client class.

[semver]: http://semver.org

#### Running

Run it as follows:

```
$ cd parent/directory
$ rug generate atomist-rugs:spring-boot-hazelcast-client:NewSpringBootHazelcastClient \
    pet-shoppe-client \
    artifact_id=pet-shop-client \
    group_id=uk.co.lndn \
    version=0.1.0-SNAPSHOT \
    description="Spring Boot Hazelcast client for remote data access" \
    new_package=uk.co.lndn.electronic \
    main_class_name=PetShopClient
```

Note the first parameter, the `project_name`, is different in that you
do not need to supply the name of the parameter, just the value.  This
is because the `project_name` parameter is required for all
generators.  This will create a directory named `pet-shoppe-client` and
populate it with a working Spring Boot Hazelcast client.  If you are happy
with the change, commit the changes.

```
$ cd pet-shoppe-client
$ git init
$ git add .
$ git commit -m 'Initial version generated by Atomist'
```

See the README in the generated project for further instructions.

## Support

General support questions should be discussed in the `#support`
channel on our community Slack team
at [atomist-community.slack.com][slack].

If you find a problem, please create an [issue][].

[issue]: https://github.com/atomist-rugs/spring-boot-hazelcast-client/issues

## Development

You can build, test, and install the project locally with
the [Rug CLI][cli].

[cli]: https://github.com/atomist/rug-cli

```
$ rug test
$ rug install
```

To create a new release of the project, simply push a tag of the form
`M.N.P` where `M`, `N`, and `P` are integers that form the next
appropriate [semantic version][semver] for release.  For example:

[semver]: http://semver.org

```
$ git tag -a 1.2.3
```

The Travis CI build (see badge at the top of this page) will
automatically create a GitHub release using the tag name for the
release and the comment provided on the annotated tag as the contents
of the release notes.  It will also automatically upload the needed
artifacts.

---
Created by [Atomist][atomist].
Need Help?  [Join our Slack team][slack].

[atomist]: https://www.atomist.com/
[slack]: https://join.atomist.com/
