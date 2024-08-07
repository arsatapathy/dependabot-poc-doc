## Install dependabot cli
- Install go latest version and run below command to install dependabot cli

```shell
go install github.com/dependabot/cli/cmd/dependabot@latest
```

## start docker desktop 
- install and run docker desktop
- a docker daemon is required to be running for the updater to work, as it pulls the updater and proxy images from the container registry to create and configure the container network to exclusively communicate through the proxy

## set GitHub access token 
```shell
set LOCAL_GITHUB_ACCESS_TOKEN=<access-token>
```

## run update 

```console
Perform an update job

Usage:
  dependabot update [<package_manager> <repo> | -f <input.yml>] [flags]

Examples:
$ dependabot update go_modules rsc/quote
$ dependabot update -f input.yml


Flags:
  -a, --api-url string            the api dependabot should connect to.
  -b, --branch string             target branch to update
      --cache string              cache import/export directory
      --collector-config string   path to an OpenTelemetry collector config file
      --commit string             commit to update
      --debug                     run an interactive shell inside the updater
      --dep stringArray           dependencies to update
  -d, --directory string          directory to update (default "/")
      --extra-hosts stringArray   Docker extra hosts setting on the proxy
  -f, --file string               path to input file
      --flamegraph                generate a flamegraph and other metrics
  -h, --help                      help for update
      --input-port int            port to use for securely passing input to the updater
      --local string              local directory to use as fetched source
  -o, --output string             write scenario to file
  -p, --provider string           provider of the repository (default "github")
      --proxy-cert string         path to a certificate the proxy will trust
      --pull                      pull the image if it isn't present (default true)
  -t, --timeout duration          max time to run an update
  -v, --volume stringArray        mount volumes in Docker

Global Flags:
      --collector-image string   container image to use for the OpenTelemetry collector (default "ghcr.io/open-telemetry/opentelemetry-collector-releases/opentelemetry-collector-contrib:latest")
      --proxy-image string       container image to use for the proxy (default "ghcr.io/github/dependabot-update-job-proxy/dependabot-update-job-proxy:latest")
      --updater-image string     container image to use for the updater
```

### `dependabot update maven arsatapathy/spring-boot-jdbc-demo`

```console
C:\Users\Gudu>dependabot update maven arsatapathy/spring-boot-jdbc-demo
    cli | 2024/05/29 06:15:42 Inserting $LOCAL_GITHUB_ACCESS_TOKEN into credentials
    cli | 2024/05/29 06:15:56 pulling image: ghcr.io/github/dependabot-update-job-proxy/dependabot-update-job-proxy:latest
    cli | 2024/05/29 06:16:56 using image ghcr.io/github/dependabot-update-job-proxy/dependabot-update-job-proxy:latest at sha256:4160c354214891899b0026b6e77b08490f19c33ca4a342f70cb92b6d12d2a900
    cli | 2024/05/29 06:16:56 pulling image: ghcr.io/dependabot/dependabot-updater-maven
    cli | 2024/05/29 06:43:21 using image ghcr.io/dependabot/dependabot-updater-maven at sha256:0ba49d0996fc17e1121a10b0d833abafdb58700759f7b6a68c0371006ed7d5ee
  proxy | 2024/05/29 06:43:28 proxy starting, commit: d85fbd08cee81b78b7f408b09b558cac7a0cee5c
  proxy | 2024/05/29 06:43:28 Listening (:1080)
updater | Updating certificates in /etc/ssl/certs...
updater | rehash: warning: skipping ca-certificates.crt,it does not contain exactly one certificate or CRL
updater | 1 added, 0 removed; done.
updater | Running hooks in /etc/ca-certificates/update.d...
updater | done.
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/httparty-0.21.0/lib/httparty.rb:10: warning: csv was loaded from the standard library, but will no longer be part of the default gems since Ruby 3.4.0. Add csv to your Gemfile or gemspec. Also contact author of httparty-0.21.0 to add csv into its gemspec.
updater | 2024/05/29 06:43:34 INFO Starting job processing
updater | 2024/05/29 06:43:34 INFO Job definition: {"job":{"package-manager":"maven","allowed-updates":[{"update-type":"all"}],"debug":false,"dependency-groups":[],"dependencies":null,"dependency-group-to-refresh":null,"existing-pull-requests":[],"existing-group-pull-requests":[],"experiments":null,"ignore-conditions":[],"lockfile-only":false,"requirements-update-strategy":null,"security-advisories":[],"security-updates-only":false,"source":{"provider":"github","repo":"arsatapathy/spring-boot-jdbc-demo","directory":"/","hostname":null,"api-endpoint":null},"update-subdependencies":false,"updating-a-pull-request":false,"vendor-dependencies":false,"reject-external-code":false,"repo-private":false,"commit-message-options":null,"credentials-metadata":[{"host":"github.com","type":"git_source"}],"max-updater-run-time":0}}
  proxy | 2024/05/29 06:43:35 [002] GET https://github.com:443/arsatapathy/spring-boot-jdbc-demo/info/refs?service=git-upload-pack
  proxy | 2024/05/29 06:43:35 [002] * authenticating git server request (host: github.com)
  proxy | 2024/05/29 06:43:45 [002] 200 https://github.com:443/arsatapathy/spring-boot-jdbc-demo/info/refs?service=git-upload-pack
  proxy | 2024/05/29 06:43:45 [004] POST https://github.com:443/arsatapathy/spring-boot-jdbc-demo/git-upload-pack
  proxy | 2024/05/29 06:43:45 [004] * authenticating git server request (host: github.com)
  proxy | 2024/05/29 06:43:45 [004] 200 https://github.com:443/arsatapathy/spring-boot-jdbc-demo/git-upload-pack
  proxy | 2024/05/29 06:43:45 [006] POST https://github.com:443/arsatapathy/spring-boot-jdbc-demo/git-upload-pack
  proxy | 2024/05/29 06:43:45 [006] * authenticating git server request (host: github.com)
  proxy | 2024/05/29 06:43:46 [006] 200 https://github.com:443/arsatapathy/spring-boot-jdbc-demo/git-upload-pack
updater | 2024/05/29 06:43:47 INFO Base commit SHA: 44ffb2cada3b43e49bcfe8ca14651903022afc01
updater | 2024/05/29 06:43:47 INFO Finished job processing
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/httparty-0.21.0/lib/httparty.rb:10: warning: csv was loaded from the standard library, but will no longer be part of the default gems since Ruby 3.4.0. Add csv to your Gemfile or gemspec. Also contact author of httparty-0.21.0 to add csv into its gemspec.
updater | 2024/05/29 06:43:49 INFO Starting job processing
  proxy | 2024/05/29 06:43:49 [007] POST http://host.docker.internal:56185/update_jobs/cli/update_dependency_list
{"data":{"dependencies":[{"name":"org.springframework.boot:spring-boot-starter-parent","requirements":[{"file":"pom.xml","groups":[],"metadata":{"packaging_type":"pom"},"requirement":"2.4.5","source":null}],"version":"2.4.5"},{"name":"org.springframework.boot:spring-boot-starter-web","requirements":[{"file":"pom.xml","groups":[],"metadata":{"packaging_type":"jar"},"requirement":null,"source":null}],"version":null},{"name":"org.springframework.boot:spring-boot-starter-test","requirements":[{"file":"pom.xml","groups":["test"],"metadata":{"packaging_type":"jar"},"requirement":null,"source":null}],"version":null},{"name":"org.springframework.boot:spring-boot-starter-log4j2","requirements":[{"file":"pom.xml","groups":[],"metadata":{"packaging_type":"jar"},"requirement":null,"source":null}],"version":null},{"name":"org.springframework.boot:spring-boot-starter-jdbc","requirements":[{"file":"pom.xml","groups":[],"metadata":{"packaging_type":"jar"},"requirement":null,"source":null}],"version":null},{"name":"com.oracle.database.jdbc:ojdbc8","requirements":[{"file":"pom.xml","groups":[],"metadata":{"packaging_type":"jar"},"requirement":"21.13.0.0","source":null}],"version":"21.13.0.0"},{"name":"org.springframework.boot:spring-boot-maven-plugin","requirements":[{"file":"pom.xml","groups":[],"metadata":{"packaging_type":"jar"},"requirement":null,"source":null}],"version":null}],"dependency_files":["/pom.xml"]},"type":"update_dependency_list"}
  proxy | 2024/05/29 06:43:49 [007] 200 http://host.docker.internal:56185/update_jobs/cli/update_dependency_list
  proxy | 2024/05/29 06:43:49 [008] POST http://host.docker.internal:56185/update_jobs/cli/increment_metric
{"data":{"metric":"updater.started","tags":{"operation":"update_all_versions"}},"type":"increment_metric"}
  proxy | 2024/05/29 06:43:49 [008] 200 http://host.docker.internal:56185/update_jobs/cli/increment_metric
updater | 2024/05/29 06:43:49 INFO Starting update job for arsatapathy/spring-boot-jdbc-demo
updater | 2024/05/29 06:43:49 INFO Checking all dependencies for version updates...
updater | 2024/05/29 06:43:49 INFO Checking if org.springframework.boot:spring-boot-starter-parent 2.4.5 needs updating
  proxy | 2024/05/29 06:43:50 [010] GET https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-parent/2.4.5/spring-boot-starter-parent-2.4.5.pom
  proxy | 2024/05/29 06:43:51 [010] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-parent/2.4.5/spring-boot-starter-parent-2.4.5.pom
  proxy | 2024/05/29 06:43:51 [012] GET https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-dependencies/2.4.5/spring-boot-dependencies-2.4.5.pom
  proxy | 2024/05/29 06:43:51 [012] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-dependencies/2.4.5/spring-boot-dependencies-2.4.5.pom
  proxy | 2024/05/29 06:43:51 [014] GET https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-parent/maven-metadata.xml
  proxy | 2024/05/29 06:43:51 [014] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-parent/maven-metadata.xml
  proxy | 2024/05/29 06:43:51 [016] HEAD https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-parent/3.3.0/spring-boot-starter-parent-3.3.0.pom
  proxy | 2024/05/29 06:43:51 [016] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-parent/3.3.0/spring-boot-starter-parent-3.3.0.pom
updater | 2024/05/29 06:43:51 INFO Latest version is 3.3.0
updater | 2024/05/29 06:43:51 INFO Requirements to unlock own
updater | 2024/05/29 06:43:51 INFO Requirements update strategy
updater | 2024/05/29 06:43:51 INFO Updating org.springframework.boot:spring-boot-starter-parent from 2.4.5 to 3.3.0
updater | 2024/05/29 06:43:51 INFO Submitting org.springframework.boot:spring-boot-starter-parent pull request for creation
  proxy | 2024/05/29 06:43:52 [018] GET https://api.github.com:443/repos/arsatapathy/spring-boot-jdbc-demo/commits?per_page=100
  proxy | 2024/05/29 06:43:52 [018] * authenticating github api request with token for api.github.com
  proxy | 2024/05/29 06:43:57 [020] GET https://api.github.com:443/repos/arsatapathy/spring-boot-jdbc-demo/commits?per_page=100
  proxy | 2024/05/29 06:43:57 [020] * authenticating github api request with token for api.github.com
  proxy | 2024/05/29 06:44:02 [022] GET https://api.github.com:443/repos/arsatapathy/spring-boot-jdbc-demo/commits?per_page=100
  proxy | 2024/05/29 06:44:02 [022] * authenticating github api request with token for api.github.com
  proxy | 2024/05/29 06:44:02 [018] 200 https://api.github.com:443/repos/arsatapathy/spring-boot-jdbc-demo/commits?per_page=100
  proxy | 2024/05/29 06:44:02 [018] WARN: Cannot write TLS response header from mitm'd client: write tcp 172.18.0.2:1080->172.18.0.3:42076: write: broken pipe
  proxy | 2024/05/29 06:44:02 [022] 200 https://api.github.com:443/repos/arsatapathy/spring-boot-jdbc-demo/commits?per_page=100
  proxy | 2024/05/29 06:44:03 [024] GET https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-parent/3.3.0/spring-boot-starter-parent-3.3.0.pom
  proxy | 2024/05/29 06:44:03 [024] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-parent/3.3.0/spring-boot-starter-parent-3.3.0.pom
  proxy | 2024/05/29 06:44:03 [026] GET https://spring.io:443/status
  proxy | 2024/05/29 06:44:03 [026] 404 https://spring.io:443/status
  proxy | 2024/05/29 06:44:03 [028] GET https://api.github.com:443/repos/spring-projects/spring-boot/releases?per_page=100
  proxy | 2024/05/29 06:44:03 [028] * authenticating github api request with token for api.github.com
  proxy | 2024/05/29 06:44:04 [020] 200 https://api.github.com:443/repos/arsatapathy/spring-boot-jdbc-demo/commits?per_page=100
  proxy | 2024/05/29 06:44:04 [020] WARN: Cannot write TLS response header from mitm'd client: write tcp 172.18.0.2:1080->172.18.0.3:42078: write: broken pipe
  proxy | 2024/05/29 06:44:05 [028] 200 https://api.github.com:443/repos/spring-projects/spring-boot/releases?per_page=100
  proxy | 2024/05/29 06:44:09 [030] GET https://api.github.com:443/repos/spring-projects/spring-boot/contents/
  proxy | 2024/05/29 06:44:09 [030] * authenticating github api request with token for api.github.com
  proxy | 2024/05/29 06:44:09 [030] 200 https://api.github.com:443/repos/spring-projects/spring-boot/contents/
  proxy | 2024/05/29 06:44:10 [032] GET https://github.com:443/spring-projects/spring-boot.git/info/refs?service=git-upload-pack
  proxy | 2024/05/29 06:44:10 [032] * authenticating git server request (host: github.com)
  proxy | 2024/05/29 06:44:10 [032] 200 https://github.com:443/spring-projects/spring-boot.git/info/refs?service=git-upload-pack
  proxy | 2024/05/29 06:44:28 Skipping sending metrics because api endpoint is empty
  proxy | 2024/05/29 06:44:29 [034] GET https://api.github.com:443/repos/spring-projects/spring-boot/contents/?ref=v3.3.0
  proxy | 2024/05/29 06:44:29 [034] * authenticating github api request with token for api.github.com
  proxy | 2024/05/29 06:44:29 [034] 200 https://api.github.com:443/repos/spring-projects/spring-boot/contents/?ref=v3.3.0
  proxy | 2024/05/29 06:44:29 [036] GET https://github.com:443/spring-projects/spring-boot.git/info/refs?service=git-upload-pack
  proxy | 2024/05/29 06:44:29 [036] 200 https://github.com:443/spring-projects/spring-boot.git/info/refs?service=git-upload-pack
  proxy | 2024/05/29 06:44:30 [038] GET https://api.github.com:443/repos/spring-projects/spring-boot/commits?sha=v2.4.5
  proxy | 2024/05/29 06:44:30 [038] * authenticating github api request with token for api.github.com
  proxy | 2024/05/29 06:44:30 [038] 200 https://api.github.com:443/repos/spring-projects/spring-boot/commits?sha=v2.4.5
  proxy | 2024/05/29 06:44:31 [040] GET https://api.github.com:443/repos/spring-projects/spring-boot/commits?sha=v3.3.0
  proxy | 2024/05/29 06:44:31 [040] * authenticating github api request with token for api.github.com
  proxy | 2024/05/29 06:44:31 [040] 200 https://api.github.com:443/repos/spring-projects/spring-boot/commits?sha=v3.3.0
  proxy | 2024/05/29 06:44:31 [042] GET https://api.github.com:443/repos/spring-projects/spring-boot/commits?sha=v2.4.5
  proxy | 2024/05/29 06:44:31 [042] 200 https://api.github.com:443/repos/spring-projects/spring-boot/commits?sha=v2.4.5
  proxy | 2024/05/29 06:44:31 [044] GET https://api.github.com:443/repos/spring-projects/spring-boot/commits?sha=v3.3.0
  proxy | 2024/05/29 06:44:31 [044] 200 https://api.github.com:443/repos/spring-projects/spring-boot/commits?sha=v3.3.0
  proxy | 2024/05/29 06:44:31 [046] GET https://api.github.com:443/repos/spring-projects/spring-boot/commits?sha=v2.4.5
  proxy | 2024/05/29 06:44:31 [046] 200 https://api.github.com:443/repos/spring-projects/spring-boot/commits?sha=v2.4.5
  proxy | 2024/05/29 06:44:31 [048] GET https://api.github.com:443/repos/spring-projects/spring-boot/commits?sha=v3.3.0
  proxy | 2024/05/29 06:44:31 [048] 200 https://api.github.com:443/repos/spring-projects/spring-boot/commits?sha=v3.3.0
  proxy | 2024/05/29 06:44:32 [049] POST http://host.docker.internal:56185/update_jobs/cli/create_pull_request
{"data":{"base-commit-sha":"44ffb2cada3b43e49bcfe8ca14651903022afc01","dependencies":[{"name":"org.springframework.boot:spring-boot-starter-parent","previous-requirements":[{"file":"pom.xml","groups":[],"metadata":{"packaging_type":"pom"},"requirement":"2.4.5","source":null}],"previous-version":"2.4.5","requirements":[{"file":"pom.xml","groups":[],"metadata":{"packaging_type":"pom"},"requirement":"3.3.0","source":{"type":"maven_repo","url":"https://repo.maven.apache.org/maven2"}}],"version":"3.3.0"}],"updated-dependency-files":[{"content":"\u003c?xml version=\"1.0\" encoding=\"UTF-8\"?\u003e\n\u003cproject xmlns=\"http://maven.apache.org/POM/4.0.0\" xmlns:xsi=\"http://www.w3.org/2001/XMLSchema-instance\"\n\txsi:schemaLocation=\"http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd\"\u003e\n\t\u003cmodelVersion\u003e4.0.0\u003c/modelVersion\u003e\n\t\u003cparent\u003e\n\t\t\u003cgroupId\u003eorg.springframework.boot\u003c/groupId\u003e\n\t\t\u003cartifactId\u003espring-boot-starter-parent\u003c/artifactId\u003e\n\t\t\u003cversion\u003e3.3.0\u003c/version\u003e\n\t\t\u003crelativePath/\u003e \u003c!-- lookup parent from repository --\u003e\n\t\u003c/parent\u003e\n\t\u003cgroupId\u003ecom.arsatapathy\u003c/groupId\u003e\n\t\u003cartifactId\u003espring-boot-jdbc-demo\u003c/artifactId\u003e\n\t\u003cversion\u003e0.0.1-SNAPSHOT\u003c/version\u003e\n\t\u003cname\u003espring-boot-jdbc-demo\u003c/name\u003e\n\t\u003cdescription\u003eDemo Project for Spring Boot\u003c/description\u003e\n\t\u003cproperties\u003e\n\t\t\u003cjava.version\u003e16\u003c/java.version\u003e\n\t\u003c/properties\u003e\n\t\u003cdependencies\u003e\n\t\t\u003cdependency\u003e\n\t\t\t\u003cgroupId\u003eorg.springframework.boot\u003c/groupId\u003e\n\t\t\t\u003cartifactId\u003espring-boot-starter-web\u003c/artifactId\u003e\n\t\t\u003c/dependency\u003e\n\n\t\t\u003cdependency\u003e\n\t\t\t\u003cgroupId\u003eorg.springframework.boot\u003c/groupId\u003e\n\t\t\t\u003cartifactId\u003espring-boot-starter-test\u003c/artifactId\u003e\n\t\t\t\u003cscope\u003etest\u003c/scope\u003e\n\t\t\u003c/dependency\u003e\n\n\t\t\u003cdependency\u003e\n\t\t\t\u003cgroupId\u003eorg.springframework.boot\u003c/groupId\u003e\n\t\t\t\u003cartifactId\u003espring-boot-starter-log4j2\u003c/artifactId\u003e\n\t\t\u003c/dependency\u003e\n\n\t\t\u003cdependency\u003e\n\t\t\t\u003cgroupId\u003eorg.springframework.boot\u003c/groupId\u003e\n\t\t\t\u003cartifactId\u003espring-boot-starter-jdbc\u003c/artifactId\u003e\n\t\t\u003c/dependency\u003e\n\n\t\t\u003cdependency\u003e\n\t\t\t\u003cgroupId\u003ecom.oracle.database.jdbc\u003c/groupId\u003e\n\t\t\t\u003cartifactId\u003eojdbc8\u003c/artifactId\u003e\n\t\t\t\u003cversion\u003e21.13.0.0\u003c/version\u003e\n\t\t\u003c/dependency\u003e\n\t\u003c/dependencies\u003e\n\n\t\u003cbuild\u003e\n\t\t\u003cplugins\u003e\n\t\t\t\u003cplugin\u003e\n\t\t\t\t\u003cgroupId\u003eorg.springframework.boot\u003c/groupId\u003e\n\t\t\t\t\u003cartifactId\u003espring-boot-maven-plugin\u003c/artifactId\u003e\n\t\t\t\u003c/plugin\u003e\n\t\t\u003c/plugins\u003e\n\t\u003c/build\u003e\n\n\u003c/project\u003e\n","content_encoding":"utf-8","deleted":false,"directory":"/","name":"pom.xml","operation":"update","support_file":false,"type":"file","mode":""}],"pr-title":"Bump org.springframework.boot:spring-boot-starter-parent from 2.4.5 to 3.3.0","pr-body":"Bumps [org.springframework.boot:spring-boot-starter-parent](https://github.com/spring-projects/spring-boot) from 2.4.5 to 3.3.0.\n\u003cdetails\u003e\n\u003csummary\u003eRelease notes\u003c/summary\u003e\n\u003cp\u003e\u003cem\u003eSourced from \u003ca href=\"https://github.com/spring-projects/spring-boot/releases\"\u003eorg.springframework.boot:spring-boot-starter-parent's releases\u003c/a\u003e.\u003c/em\u003e\u003c/p\u003e\n\u003cblockquote\u003e\n\u003ch2\u003ev3.3.0\u003c/h2\u003e\n\u003ch2\u003e:star: New Features\u003c/h2\u003e\n\u003cul\u003e\n\u003cli\u003eAdd support for descriptions of record components in configuration metadata generation \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/pull/29403\"\u003e#29403\u003c/a\u003e\u003c/li\u003e\n\u003c/ul\u003e\n\u003ch2\u003e:lady_beetle: Bug Fixes\u003c/h2\u003e\n\u003cul\u003e\n\u003cli\u003egradlew bootBuildImage fails with Podman on macOS Sonoma \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40871\"\u003e#40871\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003ePulsar auth parameters don't properly encode JSON values \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40869\"\u003e#40869\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eWhen using JPA and ImportTestcontainers, test context may fail to refresh due to \u0026quot;Mapped port can only be obtained after the container is started\u0026quot; \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40863\"\u003e#40863\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eDefault MIME mappings are not loaded unless additional mappings are configured \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40860\"\u003e#40860\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eStarting from 3.2.x, \u003ccode\u003e@SpyBean\u003c/code\u003e is not able to initialise MongoRepository bean of the generic type \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40855\"\u003e#40855\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eAuto-configuration ordering change breaks DocumentReference (in non-reactive MongoTemplate) when depending on mongodb-driver-reactivestreams \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40851\"\u003e#40851\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eNeo4jReactiveDataAutoConfiguration creates incorrectly named bean \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/pull/40836\"\u003e#40836\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eImage building fails during cleanup when bind mount has read-only content \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40799\"\u003e#40799\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eFailure Analysis for InvalidConfigurationPropertyValueException is skipped when the property is not set \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40691\"\u003e#40691\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eIllegalArgumentException can be thrown when running an uber jar on a shared drive \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40643\"\u003e#40643\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003esetReadTimeout can't be set via Reflective factory on JettyClientHttpRequestFactory \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40638\"\u003e#40638\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eURISyntaxException is raised if the spring boot application is started in a location that contains invalid URI characters \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40616\"\u003e#40616\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eresolveMainClassName fails when building with Gradle using Java 22 \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40613\"\u003e#40613\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eAnsiOutput.detectIfAnsiCapable broken on JDK22 \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40609\"\u003e#40609\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eHelp information for spring init's build option has the wrong default \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40606\"\u003e#40606\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eJarUrlConnection.getPermission() can throw NullPointerException if jarFileConnection is null \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40599\"\u003e#40599\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eWhitespace is not correctly trimmed when generating configuration properties metadata from records \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40593\"\u003e#40593\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eIn some situations, the failure when the AOT-generated initializer cannot be loaded is less helpful than before \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40584\"\u003e#40584\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eProperties binding eagerly creates superfluous maps \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40561\"\u003e#40561\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eConfiguring SSL bundle reload for non-file resource types causes errors that are difficult to diagnose \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40560\"\u003e#40560\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003espring-boot-dependencies cannot be used with repositories that ban com.oracle.database.jdbc:ojdbc-bom \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40535\"\u003e#40535\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eBuildpacks do not support Docker with containerd image store \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40526\"\u003e#40526\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eSpringBootMockMvcBuilderCustomizer can crash cryptically while collecting data that it would have discarded anyway \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40517\"\u003e#40517\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eContainers not shut down between tests when using .withReuse(true) but env. does not support reuse (e.g. CI builds) \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40509\"\u003e#40509\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eCookieSameSiteSupplier influences session cookie \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40501\"\u003e#40501\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003e\u003ccode\u003e\u0026lt;springProperty\u0026gt;\u003c/code\u003e and \u003ccode\u003e\u0026lt;springProfile\u0026gt;\u003c/code\u003e do not work in \u003ccode\u003e\u0026lt;include\u0026gt;\u003c/code\u003e after Logback upgrade \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40491\"\u003e#40491\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eRuntime hint registration for property binding should not fail when parameter information is unavailable \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40486\"\u003e#40486\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eServiceLevelObjectiveBoundary properties cannot be bound in a native image application \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40483\"\u003e#40483\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eserver.error.include-binding-errors does not recognize MethodValidationResult exceptions \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40474\"\u003e#40474\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003espring.data.redis.cluster.nodes and spring.data.redis.sentinel.nodes do not handle IPv6 addresses correctly \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40467\"\u003e#40467\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eUsing relative paths to describe the classpath in the error message from ResolveMainClassName hinders problem diagnosis \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40465\"\u003e#40465\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eJartools extract command doesn't extract all files from META-INF \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40456\"\u003e#40456\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eNative image doesn't start and doesn't log anything if an environment post processor throws an exception \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40451\"\u003e#40451\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eUnlike DataSourceAutoConfiguration, DevToolsDataSourceAutoConfiguration assumes that javax.sql.DataSource will always be available \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40441\"\u003e#40441\u003c/a\u003e\u003c/li\u003e\n\u003c/ul\u003e\n\u003ch2\u003e:notebook_with_decorative_cover: Documentation\u003c/h2\u003e\n\u003cul\u003e\n\u003cli\u003eImprove graceful shutdown documentation to remove ambiguity \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40846\"\u003e#40846\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eDocument ways to opt out from immutable \u003ccode\u003e@ConfigurationProperties\u003c/code\u003e binding with single constructor \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40844\"\u003e#40844\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eDocument that a custom HttpMessageConverters bean can be used to reorder json message converters when needed \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40839\"\u003e#40839\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eAddress ambiguity now that Testcontainers has two classes named KafkaContainer \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40756\"\u003e#40756\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003ePublish API documentation for Spring Boot's Kotlin APIs \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/issues/40692\"\u003e#40692\u003c/a\u003e\u003c/li\u003e\n\u003cli\u003eFix typo in features doc \u003ca href=\"https://redirect.github.com/spring-projects/spring-boot/pull/40631\"\u003e#40631\u003c/a\u003e\u003c/li\u003e\n\u003c/ul\u003e\n\u003c!-- raw HTML omitted --\u003e\n\u003c/blockquote\u003e\n\u003cp\u003e... (truncated)\u003c/p\u003e\n\u003c/details\u003e\n\u003cdetails\u003e\n\u003csummary\u003eCommits\u003c/summary\u003e\n\u003cul\u003e\n\u003cli\u003e\u003ca href=\"https://github.com/spring-projects/spring-boot/commit/a25e1ebe41bc02c5e7341ed1464d61c496cffe7c\"\u003e\u003ccode\u003ea25e1eb\u003c/code\u003e\u003c/a\u003e Release v3.3.0\u003c/li\u003e\n\u003cli\u003e\u003ca href=\"https://github.com/spring-projects/spring-boot/commit/ed0a3fd90845ebfa6a851c7c5d712a0ba0dcaa69\"\u003e\u003ccode\u003eed0a3fd\u003c/code\u003e\u003c/a\u003e Update publish-to-sdkman job to make new candidates the default\u003c/li\u003e\n\u003cli\u003e\u003ca href=\"https://github.com/spring-projects/spring-boot/commit/42d6f2c7a85690a444c1555fea2d72f3576f6d0b\"\u003e\u003ccode\u003e42d6f2c\u003c/code\u003e\u003c/a\u003e Merge branch '3.2.x'\u003c/li\u003e\n\u003cli\u003e\u003ca href=\"https://github.com/spring-projects/spring-boot/commit/234e0fd1f395ed284cd8b4726c9b73d695c28b27\"\u003e\u003ccode\u003e234e0fd\u003c/code\u003e\u003c/a\u003e Stop mark 3.2.x as the default SDKman release\u003c/li\u003e\n\u003cli\u003e\u003ca href=\"https://github.com/spring-projects/spring-boot/commit/226b900babb25112e0ef0dcb02e2c06ce18564dd\"\u003e\u003ccode\u003e226b900\u003c/code\u003e\u003c/a\u003e Merge branch '3.2.x'\u003c/li\u003e\n\u003cli\u003e\u003ca href=\"https://github.com/spring-projects/spring-boot/commit/c857eb62d483865bc260ea1becab4bb456468772\"\u003e\u003ccode\u003ec857eb6\u003c/code\u003e\u003c/a\u003e Fix SDKman \u0026quot;make default\u0026quot; step\u003c/li\u003e\n\u003cli\u003e\u003ca href=\"https://github.com/spring-projects/spring-boot/commit/13e13f91c09f5012eb3bc61d39455ae5d4b43eff\"\u003e\u003ccode\u003e13e13f9\u003c/code\u003e\u003c/a\u003e Merge branch '3.2.x'\u003c/li\u003e\n\u003cli\u003e\u003ca href=\"https://github.com/spring-projects/spring-boot/commit/a5ee37c5262270a8d6a0e898a441f35677310d59\"\u003e\u003ccode\u003ea5ee37c\u003c/code\u003e\u003c/a\u003e Next development version (v3.2.7-SNAPSHOT)\u003c/li\u003e\n\u003cli\u003e\u003ca href=\"https://github.com/spring-projects/spring-boot/commit/dffdd6d67ca0f1b46cf2645439a3552fa6c5f5d2\"\u003e\u003ccode\u003edffdd6d\u003c/code\u003e\u003c/a\u003e Explicitly set SDKman's make-default to false\u003c/li\u003e\n\u003cli\u003e\u003ca href=\"https://github.com/spring-projects/spring-boot/commit/86c206a849b746127be234ec3febd5eac5fc357e\"\u003e\u003ccode\u003e86c206a\u003c/code\u003e\u003c/a\u003e Merge branch '3.2.x'\u003c/li\u003e\n\u003cli\u003eAdditional commits viewable in \u003ca href=\"https://github.com/spring-projects/spring-boot/compare/v2.4.5...v3.3.0\"\u003ecompare view\u003c/a\u003e\u003c/li\u003e\n\u003c/ul\u003e\n\u003c/details\u003e\n\u003cbr /\u003e\n","commit-message":"Bump org.springframework.boot:spring-boot-starter-parent\n\nBumps [org.springframework.boot:spring-boot-starter-parent](https://github.com/spring-projects/spring-boot) from 2.4.5 to 3.3.0.\n- [Release notes](https://github.com/spring-projects/spring-boot/releases)\n- [Commits](https://github.com/spring-projects/spring-boot/compare/v2.4.5...v3.3.0)","dependency-group":null},"type":"create_pull_request"}
  proxy | 2024/05/29 06:44:32 [049] 200 http://host.docker.internal:56185/update_jobs/cli/create_pull_request
updater | 2024/05/29 06:44:32 INFO Checking if org.springframework.boot:spring-boot-starter-web  needs updating
  proxy | 2024/05/29 06:44:32 [051] GET https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-parent/2.4.5/spring-boot-starter-parent-2.4.5.pom
  proxy | 2024/05/29 06:44:32 [051] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-parent/2.4.5/spring-boot-starter-parent-2.4.5.pom
  proxy | 2024/05/29 06:44:32 [053] GET https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-dependencies/2.4.5/spring-boot-dependencies-2.4.5.pom
  proxy | 2024/05/29 06:44:32 [053] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-dependencies/2.4.5/spring-boot-dependencies-2.4.5.pom
  proxy | 2024/05/29 06:44:32 [055] GET https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-web/maven-metadata.xml
  proxy | 2024/05/29 06:44:32 [055] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-web/maven-metadata.xml
  proxy | 2024/05/29 06:44:32 [057] HEAD https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-web/3.3.0/spring-boot-starter-web-3.3.0.jar
  proxy | 2024/05/29 06:44:32 [057] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-web/3.3.0/spring-boot-starter-web-3.3.0.jar
updater | 2024/05/29 06:44:32 INFO Latest version is 3.3.0
updater | 2024/05/29 06:44:32 INFO No update needed for org.springframework.boot:spring-boot-starter-web
updater | 2024/05/29 06:44:32 INFO Checking if org.springframework.boot:spring-boot-starter-test  needs updating
  proxy | 2024/05/29 06:44:32 [059] GET https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-parent/2.4.5/spring-boot-starter-parent-2.4.5.pom
  proxy | 2024/05/29 06:44:32 [059] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-parent/2.4.5/spring-boot-starter-parent-2.4.5.pom
  proxy | 2024/05/29 06:44:33 [061] GET https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-dependencies/2.4.5/spring-boot-dependencies-2.4.5.pom
  proxy | 2024/05/29 06:44:33 [061] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-dependencies/2.4.5/spring-boot-dependencies-2.4.5.pom
  proxy | 2024/05/29 06:44:33 [063] GET https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-test/maven-metadata.xml
  proxy | 2024/05/29 06:44:33 [063] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-test/maven-metadata.xml
  proxy | 2024/05/29 06:44:33 [065] HEAD https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-test/3.3.0/spring-boot-starter-test-3.3.0.jar
  proxy | 2024/05/29 06:44:33 [065] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-test/3.3.0/spring-boot-starter-test-3.3.0.jar
updater | 2024/05/29 06:44:33 INFO Latest version is 3.3.0
updater | 2024/05/29 06:44:33 INFO No update needed for org.springframework.boot:spring-boot-starter-test
updater | 2024/05/29 06:44:33 INFO Checking if org.springframework.boot:spring-boot-starter-log4j2  needs updating
  proxy | 2024/05/29 06:44:33 [067] GET https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-parent/2.4.5/spring-boot-starter-parent-2.4.5.pom
  proxy | 2024/05/29 06:44:33 [067] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-parent/2.4.5/spring-boot-starter-parent-2.4.5.pom
  proxy | 2024/05/29 06:44:33 [069] GET https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-dependencies/2.4.5/spring-boot-dependencies-2.4.5.pom
  proxy | 2024/05/29 06:44:33 [069] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-dependencies/2.4.5/spring-boot-dependencies-2.4.5.pom
  proxy | 2024/05/29 06:44:33 [071] GET https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-log4j2/maven-metadata.xml
  proxy | 2024/05/29 06:44:33 [071] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-log4j2/maven-metadata.xml
  proxy | 2024/05/29 06:44:33 [073] HEAD https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-log4j2/3.3.0/spring-boot-starter-log4j2-3.3.0.jar
  proxy | 2024/05/29 06:44:33 [073] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-log4j2/3.3.0/spring-boot-starter-log4j2-3.3.0.jar
updater | 2024/05/29 06:44:33 INFO Latest version is 3.3.0
updater | 2024/05/29 06:44:33 INFO No update needed for org.springframework.boot:spring-boot-starter-log4j2
updater | 2024/05/29 06:44:33 INFO Checking if org.springframework.boot:spring-boot-starter-jdbc  needs updating
  proxy | 2024/05/29 06:44:34 [075] GET https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-parent/2.4.5/spring-boot-starter-parent-2.4.5.pom
  proxy | 2024/05/29 06:44:34 [075] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-parent/2.4.5/spring-boot-starter-parent-2.4.5.pom
  proxy | 2024/05/29 06:44:34 [077] GET https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-dependencies/2.4.5/spring-boot-dependencies-2.4.5.pom
  proxy | 2024/05/29 06:44:34 [077] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-dependencies/2.4.5/spring-boot-dependencies-2.4.5.pom
  proxy | 2024/05/29 06:44:34 [079] GET https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-jdbc/maven-metadata.xml
  proxy | 2024/05/29 06:44:34 [079] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-jdbc/maven-metadata.xml
  proxy | 2024/05/29 06:44:34 [081] HEAD https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-jdbc/3.3.0/spring-boot-starter-jdbc-3.3.0.jar
  proxy | 2024/05/29 06:44:34 [081] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-jdbc/3.3.0/spring-boot-starter-jdbc-3.3.0.jar
updater | 2024/05/29 06:44:34 INFO Latest version is 3.3.0
updater | 2024/05/29 06:44:34 INFO No update needed for org.springframework.boot:spring-boot-starter-jdbc
updater | 2024/05/29 06:44:34 INFO Checking if com.oracle.database.jdbc:ojdbc8 21.13.0.0 needs updating
  proxy | 2024/05/29 06:44:34 [083] GET https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-parent/2.4.5/spring-boot-starter-parent-2.4.5.pom
  proxy | 2024/05/29 06:44:34 [083] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-parent/2.4.5/spring-boot-starter-parent-2.4.5.pom
  proxy | 2024/05/29 06:44:34 [085] GET https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-dependencies/2.4.5/spring-boot-dependencies-2.4.5.pom
  proxy | 2024/05/29 06:44:34 [085] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-dependencies/2.4.5/spring-boot-dependencies-2.4.5.pom
  proxy | 2024/05/29 06:44:34 [087] GET https://repo.maven.apache.org:443/maven2/com/oracle/database/jdbc/ojdbc8/maven-metadata.xml
  proxy | 2024/05/29 06:44:34 [087] 200 https://repo.maven.apache.org:443/maven2/com/oracle/database/jdbc/ojdbc8/maven-metadata.xml
  proxy | 2024/05/29 06:44:35 [089] HEAD https://repo.maven.apache.org:443/maven2/com/oracle/database/jdbc/ojdbc8/23.4.0.24.05/ojdbc8-23.4.0.24.05.jar
  proxy | 2024/05/29 06:44:35 [089] 200 https://repo.maven.apache.org:443/maven2/com/oracle/database/jdbc/ojdbc8/23.4.0.24.05/ojdbc8-23.4.0.24.05.jar
updater | 2024/05/29 06:44:35 INFO Latest version is 23.4.0.24.05
updater | 2024/05/29 06:44:35 INFO Requirements to unlock own
updater | 2024/05/29 06:44:35 INFO Requirements update strategy
updater | 2024/05/29 06:44:35 INFO Updating com.oracle.database.jdbc:ojdbc8 from 21.13.0.0 to 23.4.0.24.05
updater | 2024/05/29 06:44:35 INFO Submitting com.oracle.database.jdbc:ojdbc8 pull request for creation
  proxy | 2024/05/29 06:44:35 [091] GET https://api.github.com:443/repos/arsatapathy/spring-boot-jdbc-demo/commits?per_page=100
  proxy | 2024/05/29 06:44:35 [091] 200 https://api.github.com:443/repos/arsatapathy/spring-boot-jdbc-demo/commits?per_page=100
  proxy | 2024/05/29 06:44:35 [093] GET https://api.github.com:443/repos/arsatapathy/spring-boot-jdbc-demo/commits?per_page=100
  proxy | 2024/05/29 06:44:35 [093] 200 https://api.github.com:443/repos/arsatapathy/spring-boot-jdbc-demo/commits?per_page=100
updater | 2024/05/29 06:44:35 ERROR Error while generating PR name: undefined method `reject' for nil
updater | 2024/05/29 06:44:35 ERROR /home/dependabot/common/lib/dependabot/pull_request_creator/pr_name_prefixer.rb:416:in `last_github_dependabot_commit_message'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:919:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:919:in `block in create_validator_method_medium0'
updater | /home/dependabot/common/lib/dependabot/pull_request_creator/pr_name_prefixer.rb:401:in `last_dependabot_commit_message'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:919:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:919:in `block in create_validator_method_medium0'
updater | /home/dependabot/common/lib/dependabot/pull_request_creator/pr_name_prefixer.rb:391:in `last_dependabot_commit_title'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:919:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:919:in `block in create_validator_method_medium0'
updater | /home/dependabot/common/lib/dependabot/pull_request_creator/pr_name_prefixer.rb:195:in `last_dependabot_commit_style'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:919:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:919:in `block in create_validator_method_medium0'
updater | /home/dependabot/common/lib/dependabot/pull_request_creator/pr_name_prefixer.rb:98:in `commit_prefix'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:919:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:919:in `block in create_validator_method_medium0'
updater | /home/dependabot/common/lib/dependabot/pull_request_creator/pr_name_prefixer.rb:57:in `pr_name_prefix'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:59:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:59:in `block in create_validator_method_fast0'
updater | /home/dependabot/common/lib/dependabot/pull_request_creator/message_builder.rb:277:in `pr_name_prefix'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:59:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:59:in `block in create_validator_method_fast0'
updater | /home/dependabot/common/lib/dependabot/pull_request_creator/message_builder.rb:117:in `pr_name'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:59:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:59:in `block in create_validator_method_fast0'
updater | /home/dependabot/common/lib/dependabot/pull_request_creator/message_builder.rb:174:in `message'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:59:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:59:in `block in create_validator_method_fast0'
updater | /home/dependabot/dependabot-updater/lib/dependabot/dependency_change.rb:76:in `pr_message'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:59:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:59:in `block in create_validator_method_fast0'
updater | /home/dependabot/dependabot-updater/lib/dependabot/api_client.rb:292:in `create_pull_request_data'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:1029:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:1029:in `block in create_validator_method_medium2'
updater | /home/dependabot/dependabot-updater/lib/dependabot/api_client.rb:40:in `block in create_pull_request'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/opentelemetry-api-1.2.3/lib/opentelemetry/trace/tracer.rb:37:in `block in in_span'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/opentelemetry-api-1.2.3/lib/opentelemetry/trace.rb:70:in `block in with_span'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/opentelemetry-api-1.2.3/lib/opentelemetry/context.rb:87:in `with_value'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/opentelemetry-api-1.2.3/lib/opentelemetry/trace.rb:70:in `with_span'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/opentelemetry-api-1.2.3/lib/opentelemetry/trace/tracer.rb:37:in `in_span'
updater | /home/dependabot/dependabot-updater/lib/dependabot/api_client.rb:34:in `create_pull_request'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:734:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:734:in `block in create_validator_procedure_fast2'
updater | /home/dependabot/dependabot-updater/lib/dependabot/service.rb:54:in `create_pull_request'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:734:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:734:in `block in create_validator_procedure_fast2'
updater | /home/dependabot/dependabot-updater/lib/dependabot/updater/operations/update_all_versions.rb:261:in `create_pull_request'
updater | /home/dependabot/dependabot-updater/lib/dependabot/updater/operations/update_all_versions.rb:143:in `check_and_create_pull_request'
updater | /home/dependabot/dependabot-updater/lib/dependabot/updater/operations/update_all_versions.rb:64:in `check_and_create_pr_with_error_handling'
updater | /home/dependabot/dependabot-updater/lib/dependabot/updater/operations/update_all_versions.rb:39:in `block in perform'
updater | /home/dependabot/dependabot-updater/lib/dependabot/updater/operations/update_all_versions.rb:39:in `each'
updater | /home/dependabot/dependabot-updater/lib/dependabot/updater/operations/update_all_versions.rb:39:in `perform'
updater | /home/dependabot/dependabot-updater/lib/dependabot/updater.rb:45:in `run'
updater | /home/dependabot/dependabot-updater/lib/dependabot/update_files_command.rb:44:in `block in perform_job'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/opentelemetry-api-1.2.3/lib/opentelemetry/trace/tracer.rb:37:in `block in in_span'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/opentelemetry-api-1.2.3/lib/opentelemetry/trace.rb:70:in `block in with_span'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/opentelemetry-api-1.2.3/lib/opentelemetry/context.rb:87:in `with_value'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/opentelemetry-api-1.2.3/lib/opentelemetry/trace.rb:70:in `with_span'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/opentelemetry-api-1.2.3/lib/opentelemetry/trace/tracer.rb:37:in `in_span'
updater | /home/dependabot/dependabot-updater/lib/dependabot/update_files_command.rb:18:in `perform_job'
updater | /home/dependabot/dependabot-updater/lib/dependabot/base_command.rb:37:in `run'
updater | bin/update_files.rb:46:in `<main>'
  proxy | 2024/05/29 06:44:35 [095] GET https://repo.maven.apache.org:443/maven2/com/oracle/database/jdbc/ojdbc8/23.4.0.24.05/ojdbc8-23.4.0.24.05.pom
  proxy | 2024/05/29 06:44:35 [095] 200 https://repo.maven.apache.org:443/maven2/com/oracle/database/jdbc/ojdbc8/23.4.0.24.05/ojdbc8-23.4.0.24.05.pom
  proxy | 2024/05/29 06:44:35 [097] GET https://www.oracle.com:443/status
  proxy | 2024/05/29 06:44:36 [097] 301 https://www.oracle.com:443/status
  proxy | 2024/05/29 06:44:36 [099] GET https://api.github.com:443/repos/arsatapathy/spring-boot-jdbc-demo/commits?per_page=100
  proxy | 2024/05/29 06:44:36 [099] 200 https://api.github.com:443/repos/arsatapathy/spring-boot-jdbc-demo/commits?per_page=100
  proxy | 2024/05/29 06:44:36 [101] GET https://api.github.com:443/repos/arsatapathy/spring-boot-jdbc-demo/commits?per_page=100
  proxy | 2024/05/29 06:44:36 [101] 200 https://api.github.com:443/repos/arsatapathy/spring-boot-jdbc-demo/commits?per_page=100
updater | 2024/05/29 06:44:36 ERROR Error while generating PR name: undefined method `reject' for nil
updater | 2024/05/29 06:44:36 ERROR /home/dependabot/common/lib/dependabot/pull_request_creator/pr_name_prefixer.rb:416:in `last_github_dependabot_commit_message'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:919:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:919:in `block in create_validator_method_medium0'
updater | /home/dependabot/common/lib/dependabot/pull_request_creator/pr_name_prefixer.rb:401:in `last_dependabot_commit_message'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:919:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:919:in `block in create_validator_method_medium0'
updater | /home/dependabot/common/lib/dependabot/pull_request_creator/pr_name_prefixer.rb:391:in `last_dependabot_commit_title'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:919:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:919:in `block in create_validator_method_medium0'
updater | /home/dependabot/common/lib/dependabot/pull_request_creator/pr_name_prefixer.rb:195:in `last_dependabot_commit_style'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:919:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:919:in `block in create_validator_method_medium0'
updater | /home/dependabot/common/lib/dependabot/pull_request_creator/pr_name_prefixer.rb:98:in `commit_prefix'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:919:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:919:in `block in create_validator_method_medium0'
updater | /home/dependabot/common/lib/dependabot/pull_request_creator/pr_name_prefixer.rb:57:in `pr_name_prefix'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:59:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:59:in `block in create_validator_method_fast0'
updater | /home/dependabot/common/lib/dependabot/pull_request_creator/message_builder.rb:277:in `pr_name_prefix'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:59:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:59:in `block in create_validator_method_fast0'
updater | /home/dependabot/common/lib/dependabot/pull_request_creator/message_builder.rb:117:in `pr_name'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:59:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:59:in `block in create_validator_method_fast0'
updater | /home/dependabot/common/lib/dependabot/pull_request_creator/message_builder.rb:292:in `commit_subject'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:59:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:59:in `block in create_validator_method_fast0'
updater | /home/dependabot/common/lib/dependabot/pull_request_creator/message_builder.rb:159:in `commit_message'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:59:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:59:in `block in create_validator_method_fast0'
updater | /home/dependabot/common/lib/dependabot/pull_request_creator/message_builder.rb:176:in `message'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:59:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:59:in `block in create_validator_method_fast0'
updater | /home/dependabot/dependabot-updater/lib/dependabot/dependency_change.rb:76:in `pr_message'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:59:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:59:in `block in create_validator_method_fast0'
updater | /home/dependabot/dependabot-updater/lib/dependabot/api_client.rb:292:in `create_pull_request_data'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:1029:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:1029:in `block in create_validator_method_medium2'
updater | /home/dependabot/dependabot-updater/lib/dependabot/api_client.rb:40:in `block in create_pull_request'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/opentelemetry-api-1.2.3/lib/opentelemetry/trace/tracer.rb:37:in `block in in_span'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/opentelemetry-api-1.2.3/lib/opentelemetry/trace.rb:70:in `block in with_span'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/opentelemetry-api-1.2.3/lib/opentelemetry/context.rb:87:in `with_value'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/opentelemetry-api-1.2.3/lib/opentelemetry/trace.rb:70:in `with_span'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/opentelemetry-api-1.2.3/lib/opentelemetry/trace/tracer.rb:37:in `in_span'
updater | /home/dependabot/dependabot-updater/lib/dependabot/api_client.rb:34:in `create_pull_request'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:734:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:734:in `block in create_validator_procedure_fast2'
updater | /home/dependabot/dependabot-updater/lib/dependabot/service.rb:54:in `create_pull_request'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:734:in `bind_call'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/sorbet-runtime-0.5.11353/lib/types/private/methods/call_validation_2_7.rb:734:in `block in create_validator_procedure_fast2'
updater | /home/dependabot/dependabot-updater/lib/dependabot/updater/operations/update_all_versions.rb:261:in `create_pull_request'
updater | /home/dependabot/dependabot-updater/lib/dependabot/updater/operations/update_all_versions.rb:143:in `check_and_create_pull_request'
  proxy | 2024/05/29 06:44:36 [102] POST http://host.docker.internal:56185/update_jobs/cli/create_pull_request
updater | /home/dependabot/dependabot-updater/lib/dependabot/updater/operations/update_all_versions.rb:64:in `check_and_create_pr_with_error_handling'
updater | /home/dependabot/dependabot-updater/lib/dependabot/updater/operations/update_all_versions.rb:39:in `block in perform'
updater | /home/dependabot/dependabot-updater/lib/dependabot/updater/operations/update_all_versions.rb:39:in `each'
updater | /home/dependabot/dependabot-updater/lib/dependabot/updater/operations/update_all_versions.rb:39:in `perform'
updater | /home/dependabot/dependabot-updater/lib/dependabot/updater.rb:45:in `run'
updater | /home/dependabot/dependabot-updater/lib/dependabot/update_files_command.rb:44:in `block in perform_job'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/opentelemetry-api-1.2.3/lib/opentelemetry/trace/tracer.rb:37:in `block in in_span'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/opentelemetry-api-1.2.3/lib/opentelemetry/trace.rb:70:in `block in with_span'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/opentelemetry-api-1.2.3/lib/opentelemetry/context.rb:87:in `with_value'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/opentelemetry-api-1.2.3/lib/opentelemetry/trace.rb:70:in `with_span'
updater | /home/dependabot/dependabot-updater/vendor/ruby/3.3.0/gems/opentelemetry-api-1.2.3/lib/opentelemetry/trace/tracer.rb:37:in `in_span'
updater | /home/dependabot/dependabot-updater/lib/dependabot/update_files_command.rb:18:in `perform_job'
updater | /home/dependabot/dependabot-updater/lib/dependabot/base_command.rb:37:in `run'
updater | bin/update_files.rb:46:in `<main>'
{"data":{"base-commit-sha":"44ffb2cada3b43e49bcfe8ca14651903022afc01","dependencies":[{"name":"com.oracle.database.jdbc:ojdbc8","previous-requirements":[{"file":"pom.xml","groups":[],"metadata":{"packaging_type":"jar"},"requirement":"21.13.0.0","source":null}],"previous-version":"21.13.0.0","requirements":[{"file":"pom.xml","groups":[],"metadata":{"packaging_type":"jar"},"requirement":"23.4.0.24.05","source":{"type":"maven_repo","url":"https://repo.maven.apache.org/maven2"}}],"version":"23.4.0.24.05"}],"updated-dependency-files":[{"content":"\u003c?xml version=\"1.0\" encoding=\"UTF-8\"?\u003e\n\u003cproject xmlns=\"http://maven.apache.org/POM/4.0.0\" xmlns:xsi=\"http://www.w3.org/2001/XMLSchema-instance\"\n\txsi:schemaLocation=\"http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd\"\u003e\n\t\u003cmodelVersion\u003e4.0.0\u003c/modelVersion\u003e\n\t\u003cparent\u003e\n\t\t\u003cgroupId\u003eorg.springframework.boot\u003c/groupId\u003e\n\t\t\u003cartifactId\u003espring-boot-starter-parent\u003c/artifactId\u003e\n\t\t\u003cversion\u003e2.4.5\u003c/version\u003e\n\t\t\u003crelativePath/\u003e \u003c!-- lookup parent from repository --\u003e\n\t\u003c/parent\u003e\n\t\u003cgroupId\u003ecom.arsatapathy\u003c/groupId\u003e\n\t\u003cartifactId\u003espring-boot-jdbc-demo\u003c/artifactId\u003e\n\t\u003cversion\u003e0.0.1-SNAPSHOT\u003c/version\u003e\n\t\u003cname\u003espring-boot-jdbc-demo\u003c/name\u003e\n\t\u003cdescription\u003eDemo Project for Spring Boot\u003c/description\u003e\n\t\u003cproperties\u003e\n\t\t\u003cjava.version\u003e16\u003c/java.version\u003e\n\t\u003c/properties\u003e\n\t\u003cdependencies\u003e\n\t\t\u003cdependency\u003e\n\t\t\t\u003cgroupId\u003eorg.springframework.boot\u003c/groupId\u003e\n\t\t\t\u003cartifactId\u003espring-boot-starter-web\u003c/artifactId\u003e\n\t\t\u003c/dependency\u003e\n\n\t\t\u003cdependency\u003e\n\t\t\t\u003cgroupId\u003eorg.springframework.boot\u003c/groupId\u003e\n\t\t\t\u003cartifactId\u003espring-boot-starter-test\u003c/artifactId\u003e\n\t\t\t\u003cscope\u003etest\u003c/scope\u003e\n\t\t\u003c/dependency\u003e\n\n\t\t\u003cdependency\u003e\n\t\t\t\u003cgroupId\u003eorg.springframework.boot\u003c/groupId\u003e\n\t\t\t\u003cartifactId\u003espring-boot-starter-log4j2\u003c/artifactId\u003e\n\t\t\u003c/dependency\u003e\n\n\t\t\u003cdependency\u003e\n\t\t\t\u003cgroupId\u003eorg.springframework.boot\u003c/groupId\u003e\n\t\t\t\u003cartifactId\u003espring-boot-starter-jdbc\u003c/artifactId\u003e\n\t\t\u003c/dependency\u003e\n\n\t\t\u003cdependency\u003e\n\t\t\t\u003cgroupId\u003ecom.oracle.database.jdbc\u003c/groupId\u003e\n\t\t\t\u003cartifactId\u003eojdbc8\u003c/artifactId\u003e\n\t\t\t\u003cversion\u003e23.4.0.24.05\u003c/version\u003e\n\t\t\u003c/dependency\u003e\n\t\u003c/dependencies\u003e\n\n\t\u003cbuild\u003e\n\t\t\u003cplugins\u003e\n\t\t\t\u003cplugin\u003e\n\t\t\t\t\u003cgroupId\u003eorg.springframework.boot\u003c/groupId\u003e\n\t\t\t\t\u003cartifactId\u003espring-boot-maven-plugin\u003c/artifactId\u003e\n\t\t\t\u003c/plugin\u003e\n\t\t\u003c/plugins\u003e\n\t\u003c/build\u003e\n\n\u003c/project\u003e\n","content_encoding":"utf-8","deleted":false,"directory":"/","name":"pom.xml","operation":"update","support_file":false,"type":"file","mode":""}],"pr-title":"bump com.oracle.database.jdbc:ojdbc8 from 21.13.0.0 to 23.4.0.24.05","pr-body":"Bumps com.oracle.database.jdbc:ojdbc8 from 21.13.0.0 to 23.4.0.24.05.\n","commit-message":"bump com.oracle.database.jdbc:ojdbc8 from 21.13.0.0 to 23.4.0.24.05\n\nBumps com.oracle.database.jdbc:ojdbc8 from 21.13.0.0 to 23.4.0.24.05.","dependency-group":null},"type":"create_pull_request"}
updater | 2024/05/29 06:44:36 INFO Checking if org.springframework.boot:spring-boot-maven-plugin  needs updating
  proxy | 2024/05/29 06:44:36 [102] 200 http://host.docker.internal:56185/update_jobs/cli/create_pull_request
  proxy | 2024/05/29 06:44:36 [104] GET https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-parent/2.4.5/spring-boot-starter-parent-2.4.5.pom
  proxy | 2024/05/29 06:44:36 [104] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-starter-parent/2.4.5/spring-boot-starter-parent-2.4.5.pom
  proxy | 2024/05/29 06:44:36 [106] GET https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-dependencies/2.4.5/spring-boot-dependencies-2.4.5.pom
  proxy | 2024/05/29 06:44:36 [106] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-dependencies/2.4.5/spring-boot-dependencies-2.4.5.pom
  proxy | 2024/05/29 06:44:36 [108] GET https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-maven-plugin/maven-metadata.xml
  proxy | 2024/05/29 06:44:36 [108] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-maven-plugin/maven-metadata.xml
  proxy | 2024/05/29 06:44:37 [110] HEAD https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-maven-plugin/3.3.0/spring-boot-maven-plugin-3.3.0.jar
  proxy | 2024/05/29 06:44:37 [110] 200 https://repo.maven.apache.org:443/maven2/org/springframework/boot/spring-boot-maven-plugin/3.3.0/spring-boot-maven-plugin-3.3.0.jar
updater | 2024/05/29 06:44:37 INFO Latest version is 3.3.0
updater | 2024/05/29 06:44:37 INFO No update needed for org.springframework.boot:spring-boot-maven-plugin
{"data":{"base-commit-sha":"44ffb2cada3b43e49bcfe8ca14651903022afc01"},"type":"mark_as_processed"}
  proxy | 2024/05/29 06:44:37 [111] PATCH http://host.docker.internal:56185/update_jobs/cli/mark_as_processed
  proxy | 2024/05/29 06:44:37 [111] 200 http://host.docker.internal:56185/update_jobs/cli/mark_as_processed
updater | 2024/05/29 06:44:37 INFO Finished job processing
updater | 2024/05/29 06:44:37 INFO Results:
updater | +---------------------------------------------------------------------------------------+
updater | |                          Changes to Dependabot Pull Requests                          |
updater | +---------+-----------------------------------------------------------------------------+
updater | | created | org.springframework.boot:spring-boot-starter-parent ( from 2.4.5 to 3.3.0 ) |
updater | | created | com.oracle.database.jdbc:ojdbc8 ( from 21.13.0.0 to 23.4.0.24.05 )          |
updater | +---------+-----------------------------------------------------------------------------+
  proxy | 2024/05/29 06:44:38 Skipping sending metrics because api endpoint is empty
  proxy | 2024/05/29 06:44:38 21/53 calls cached (39%)
```


# Scenarios 

`dependabot update -f job.yaml -o output.yaml`
## Scan and update all dependencies to any latest version  

### job.yaml
```yaml
job:
  package-manager: maven
  allowed-updates:
    - update-type: all
  source:
    provider: github
    repo: arsatapathy/spring-boot-jdbc-demo
    directory: /
```

### output.yaml
```yaml
input:
    job:
        package-manager: maven
        allowed-updates:
            - update-type: all
        ignore-conditions:
            - dependency-name: org.springframework.boot:spring-boot-starter-parent
              source: output.yml
              version-requirement: '>3.3.0'
            - dependency-name: com.oracle.database.jdbc:ojdbc8
              source: output.yml
              version-requirement: '>23.4.0.24.05'
        source:
            provider: github
            repo: arsatapathy/spring-boot-jdbc-demo
            directory: /
            commit: 23047f72c407aa92249945fc98f128c23d4e1e96
    credentials:
        - host: github.com
          password: $LOCAL_GITHUB_ACCESS_TOKEN
          type: git_source
          username: x-access-token
output:
    - type: update_dependency_list
      expect:
        data:
            dependencies:
                - name: org.springframework.boot:spring-boot-starter-parent
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: pom
                      requirement: 2.4.5
                      source: null
                  version: 2.4.5
                - name: org.springframework.boot:spring-boot-starter-web
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: jar
                      requirement: null
                      source: null
                  version: null
                - name: org.springframework.boot:spring-boot-starter-test
                  requirements:
                    - file: pom.xml
                      groups:
                        - test
                      metadata:
                        packaging_type: jar
                      requirement: null
                      source: null
                  version: null
                - name: org.springframework.boot:spring-boot-starter-log4j2
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: jar
                      requirement: null
                      source: null
                  version: null
                - name: org.springframework.boot:spring-boot-starter-jdbc
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: jar
                      requirement: null
                      source: null
                  version: null
                - name: com.oracle.database.jdbc:ojdbc8
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: jar
                      requirement: 21.13.0.0
                      source: null
                  version: 21.13.0.0
                - name: org.springframework.boot:spring-boot-maven-plugin
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: jar
                      requirement: null
                      source: null
                  version: null
            dependency_files:
                - /pom.xml
    - type: create_pull_request
      expect:
        data:
            base-commit-sha: 23047f72c407aa92249945fc98f128c23d4e1e96
            dependencies:
                - name: org.springframework.boot:spring-boot-starter-parent
                  previous-requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: pom
                      requirement: 2.4.5
                      source: null
                  previous-version: 2.4.5
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: pom
                      requirement: 3.3.0
                      source:
                        type: maven_repo
                        url: https://repo.maven.apache.org/maven2
                  version: 3.3.0
            updated-dependency-files:
                - content: |
                    <?xml version="1.0" encoding="UTF-8"?>
                    <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
                    	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
                    	<modelVersion>4.0.0</modelVersion>
                    	<parent>
                    		<groupId>org.springframework.boot</groupId>
                    		<artifactId>spring-boot-starter-parent</artifactId>
                    		<version>3.3.0</version>
                    		<relativePath/> <!-- lookup parent from repository -->
                    	</parent>
                    	<groupId>com.arsatapathy</groupId>
                    	<artifactId>spring-boot-jdbc-demo</artifactId>
                    	<version>0.0.1-SNAPSHOT</version>
                    	<name>spring-boot-jdbc-demo</name>
                    	<description>Demo Project for Spring Boot</description>
                    	<properties>
                    		<java.version>16</java.version>
                    	</properties>
                    	<dependencies>
                    		<dependency>
                    			<groupId>org.springframework.boot</groupId>
                    			<artifactId>spring-boot-starter-web</artifactId>
                    		</dependency>

                    		<dependency>
                    			<groupId>org.springframework.boot</groupId>
                    			<artifactId>spring-boot-starter-test</artifactId>
                    			<scope>test</scope>
                    		</dependency>

                    		<dependency>
                    			<groupId>org.springframework.boot</groupId>
                    			<artifactId>spring-boot-starter-log4j2</artifactId>
                    		</dependency>

                    		<dependency>
                    			<groupId>org.springframework.boot</groupId>
                    			<artifactId>spring-boot-starter-jdbc</artifactId>
                    		</dependency>

                    		<dependency>
                    			<groupId>com.oracle.database.jdbc</groupId>
                    			<artifactId>ojdbc8</artifactId>
                    			<version>21.13.0.0</version>
                    		</dependency>
                    	</dependencies>

                    	<build>
                    		<plugins>
                    			<plugin>
                    				<groupId>org.springframework.boot</groupId>
                    				<artifactId>spring-boot-maven-plugin</artifactId>
                    			</plugin>
                    		</plugins>
                    	</build>

                    </project>
                  content_encoding: utf-8
                  deleted: false
                  directory: /
                  name: pom.xml
                  operation: update
                  support_file: false
                  type: file
            pr-title: Bump org.springframework.boot:spring-boot-starter-parent from 2.4.5 to 3.3.0
            pr-body: |
                Bumps [org.springframework.boot:spring-boot-starter-parent](https://github.com/spring-projects/spring-boot) from 2.4.5 to 3.3.0.
                <details>
                <summary>Release notes</summary>
                <p><em>Sourced from <a href="https://github.com/spring-projects/spring-boot/releases">org.springframework.boot:spring-boot-starter-parent's releases</a>.</em></p>
                <blockquote>
                <h2>v3.3.0</h2>
                <h2>:star: New Features</h2>
                <ul>
                <li>Add support for descriptions of record components in configuration metadata generation <a href="https://redirect.github.com/spring-projects/spring-boot/pull/29403">#29403</a></li>
                </ul>
                <h2>:lady_beetle: Bug Fixes</h2>
                <ul>
                <li>gradlew bootBuildImage fails with Podman on macOS Sonoma <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40871">#40871</a></li>
                <li>Pulsar auth parameters don't properly encode JSON values <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40869">#40869</a></li>
                <li>When using JPA and ImportTestcontainers, test context may fail to refresh due to &quot;Mapped port can only be obtained after the container is started&quot; <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40863">#40863</a></li>
                <li>Default MIME mappings are not loaded unless additional mappings are configured <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40860">#40860</a></li>
                <li>Starting from 3.2.x, <code>@SpyBean</code> is not able to initialise MongoRepository bean of the generic type <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40855">#40855</a></li>
                <li>Auto-configuration ordering change breaks DocumentReference (in non-reactive MongoTemplate) when depending on mongodb-driver-reactivestreams <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40851">#40851</a></li>
                <li>Neo4jReactiveDataAutoConfiguration creates incorrectly named bean <a href="https://redirect.github.com/spring-projects/spring-boot/pull/40836">#40836</a></li>
                <li>Image building fails during cleanup when bind mount has read-only content <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40799">#40799</a></li>
                <li>Failure Analysis for InvalidConfigurationPropertyValueException is skipped when the property is not set <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40691">#40691</a></li>
                <li>IllegalArgumentException can be thrown when running an uber jar on a shared drive <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40643">#40643</a></li>
                <li>setReadTimeout can't be set via Reflective factory on JettyClientHttpRequestFactory <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40638">#40638</a></li>
                <li>URISyntaxException is raised if the spring boot application is started in a location that contains invalid URI characters <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40616">#40616</a></li>
                <li>resolveMainClassName fails when building with Gradle using Java 22 <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40613">#40613</a></li>
                <li>AnsiOutput.detectIfAnsiCapable broken on JDK22 <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40609">#40609</a></li>
                <li>Help information for spring init's build option has the wrong default <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40606">#40606</a></li>
                <li>JarUrlConnection.getPermission() can throw NullPointerException if jarFileConnection is null <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40599">#40599</a></li>
                <li>Whitespace is not correctly trimmed when generating configuration properties metadata from records <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40593">#40593</a></li>
                <li>In some situations, the failure when the AOT-generated initializer cannot be loaded is less helpful than before <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40584">#40584</a></li>
                <li>Properties binding eagerly creates superfluous maps <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40561">#40561</a></li>
                <li>Configuring SSL bundle reload for non-file resource types causes errors that are difficult to diagnose <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40560">#40560</a></li>
                <li>spring-boot-dependencies cannot be used with repositories that ban com.oracle.database.jdbc:ojdbc-bom <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40535">#40535</a></li>
                <li>Buildpacks do not support Docker with containerd image store <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40526">#40526</a></li>
                <li>SpringBootMockMvcBuilderCustomizer can crash cryptically while collecting data that it would have discarded anyway <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40517">#40517</a></li>
                <li>Containers not shut down between tests when using .withReuse(true) but env. does not support reuse (e.g. CI builds) <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40509">#40509</a></li>
                <li>CookieSameSiteSupplier influences session cookie <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40501">#40501</a></li>
                <li><code>&lt;springProperty&gt;</code> and <code>&lt;springProfile&gt;</code> do not work in <code>&lt;include&gt;</code> after Logback upgrade <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40491">#40491</a></li>
                <li>Runtime hint registration for property binding should not fail when parameter information is unavailable <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40486">#40486</a></li>
                <li>ServiceLevelObjectiveBoundary properties cannot be bound in a native image application <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40483">#40483</a></li>
                <li>server.error.include-binding-errors does not recognize MethodValidationResult exceptions <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40474">#40474</a></li>
                <li>spring.data.redis.cluster.nodes and spring.data.redis.sentinel.nodes do not handle IPv6 addresses correctly <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40467">#40467</a></li>
                <li>Using relative paths to describe the classpath in the error message from ResolveMainClassName hinders problem diagnosis <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40465">#40465</a></li>
                <li>Jartools extract command doesn't extract all files from META-INF <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40456">#40456</a></li>
                <li>Native image doesn't start and doesn't log anything if an environment post processor throws an exception <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40451">#40451</a></li>
                <li>Unlike DataSourceAutoConfiguration, DevToolsDataSourceAutoConfiguration assumes that javax.sql.DataSource will always be available <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40441">#40441</a></li>
                </ul>
                <h2>:notebook_with_decorative_cover: Documentation</h2>
                <ul>
                <li>Improve graceful shutdown documentation to remove ambiguity <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40846">#40846</a></li>
                <li>Document ways to opt out from immutable <code>@ConfigurationProperties</code> binding with single constructor <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40844">#40844</a></li>
                <li>Document that a custom HttpMessageConverters bean can be used to reorder json message converters when needed <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40839">#40839</a></li>
                <li>Address ambiguity now that Testcontainers has two classes named KafkaContainer <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40756">#40756</a></li>
                <li>Publish API documentation for Spring Boot's Kotlin APIs <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40692">#40692</a></li>
                <li>Fix typo in features doc <a href="https://redirect.github.com/spring-projects/spring-boot/pull/40631">#40631</a></li>
                </ul>
                <!-- raw HTML omitted -->
                </blockquote>
                <p>... (truncated)</p>
                </details>
                <details>
                <summary>Commits</summary>
                <ul>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/a25e1ebe41bc02c5e7341ed1464d61c496cffe7c"><code>a25e1eb</code></a> Release v3.3.0</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/ed0a3fd90845ebfa6a851c7c5d712a0ba0dcaa69"><code>ed0a3fd</code></a> Update publish-to-sdkman job to make new candidates the default</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/42d6f2c7a85690a444c1555fea2d72f3576f6d0b"><code>42d6f2c</code></a> Merge branch '3.2.x'</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/234e0fd1f395ed284cd8b4726c9b73d695c28b27"><code>234e0fd</code></a> Stop mark 3.2.x as the default SDKman release</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/226b900babb25112e0ef0dcb02e2c06ce18564dd"><code>226b900</code></a> Merge branch '3.2.x'</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/c857eb62d483865bc260ea1becab4bb456468772"><code>c857eb6</code></a> Fix SDKman &quot;make default&quot; step</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/13e13f91c09f5012eb3bc61d39455ae5d4b43eff"><code>13e13f9</code></a> Merge branch '3.2.x'</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/a5ee37c5262270a8d6a0e898a441f35677310d59"><code>a5ee37c</code></a> Next development version (v3.2.7-SNAPSHOT)</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/dffdd6d67ca0f1b46cf2645439a3552fa6c5f5d2"><code>dffdd6d</code></a> Explicitly set SDKman's make-default to false</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/86c206a849b746127be234ec3febd5eac5fc357e"><code>86c206a</code></a> Merge branch '3.2.x'</li>
                <li>Additional commits viewable in <a href="https://github.com/spring-projects/spring-boot/compare/v2.4.5...v3.3.0">compare view</a></li>
                </ul>
                </details>
                <br />
            commit-message: |-
                Bump org.springframework.boot:spring-boot-starter-parent

                Bumps [org.springframework.boot:spring-boot-starter-parent](https://github.com/spring-projects/spring-boot) from 2.4.5 to 3.3.0.
                - [Release notes](https://github.com/spring-projects/spring-boot/releases)
                - [Commits](https://github.com/spring-projects/spring-boot/compare/v2.4.5...v3.3.0)
    - type: create_pull_request
      expect:
        data:
            base-commit-sha: 23047f72c407aa92249945fc98f128c23d4e1e96
            dependencies:
                - name: com.oracle.database.jdbc:ojdbc8
                  previous-requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: jar
                      requirement: 21.13.0.0
                      source: null
                  previous-version: 21.13.0.0
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: jar
                      requirement: 23.4.0.24.05
                      source:
                        type: maven_repo
                        url: https://repo.maven.apache.org/maven2
                  version: 23.4.0.24.05
            updated-dependency-files:
                - content: |
                    <?xml version="1.0" encoding="UTF-8"?>
                    <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
                    	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
                    	<modelVersion>4.0.0</modelVersion>
                    	<parent>
                    		<groupId>org.springframework.boot</groupId>
                    		<artifactId>spring-boot-starter-parent</artifactId>
                    		<version>2.4.5</version>
                    		<relativePath/> <!-- lookup parent from repository -->
                    	</parent>
                    	<groupId>com.arsatapathy</groupId>
                    	<artifactId>spring-boot-jdbc-demo</artifactId>
                    	<version>0.0.1-SNAPSHOT</version>
                    	<name>spring-boot-jdbc-demo</name>
                    	<description>Demo Project for Spring Boot</description>
                    	<properties>
                    		<java.version>16</java.version>
                    	</properties>
                    	<dependencies>
                    		<dependency>
                    			<groupId>org.springframework.boot</groupId>
                    			<artifactId>spring-boot-starter-web</artifactId>
                    		</dependency>

                    		<dependency>
                    			<groupId>org.springframework.boot</groupId>
                    			<artifactId>spring-boot-starter-test</artifactId>
                    			<scope>test</scope>
                    		</dependency>

                    		<dependency>
                    			<groupId>org.springframework.boot</groupId>
                    			<artifactId>spring-boot-starter-log4j2</artifactId>
                    		</dependency>

                    		<dependency>
                    			<groupId>org.springframework.boot</groupId>
                    			<artifactId>spring-boot-starter-jdbc</artifactId>
                    		</dependency>

                    		<dependency>
                    			<groupId>com.oracle.database.jdbc</groupId>
                    			<artifactId>ojdbc8</artifactId>
                    			<version>23.4.0.24.05</version>
                    		</dependency>
                    	</dependencies>

                    	<build>
                    		<plugins>
                    			<plugin>
                    				<groupId>org.springframework.boot</groupId>
                    				<artifactId>spring-boot-maven-plugin</artifactId>
                    			</plugin>
                    		</plugins>
                    	</build>

                    </project>
                  content_encoding: utf-8
                  deleted: false
                  directory: /
                  name: pom.xml
                  operation: update
                  support_file: false
                  type: file
            pr-title: bump com.oracle.database.jdbc:ojdbc8 from 21.13.0.0 to 23.4.0.24.05
            pr-body: |
                Bumps com.oracle.database.jdbc:ojdbc8 from 21.13.0.0 to 23.4.0.24.05.
            commit-message: |-
                bump com.oracle.database.jdbc:ojdbc8 from 21.13.0.0 to 23.4.0.24.05

                Bumps com.oracle.database.jdbc:ojdbc8 from 21.13.0.0 to 23.4.0.24.05.
    - type: mark_as_processed
      expect:
        data:
            base-commit-sha: 23047f72c407aa92249945fc98f128c23d4e1e96
```

## Scan and update specific dependencies to any latest version  

### job.yaml
```yaml
job:
  package-manager: maven
  allowed-updates:
    - dependency-name: "org.springframework.boot:spring-boot-starter-parent"
      update-type: "all"  # Ensures all types of updates are allowed for this dependency
  source:
    provider: github
    repo: arsatapathy/spring-boot-jdbc-demo
    directory: "/"
```

### output.yaml
```yaml
input:
    job:
        package-manager: maven
        allowed-updates:
            - dependency-name: org.springframework.boot:spring-boot-starter-parent
              update-type: all
        ignore-conditions:
            - dependency-name: org.springframework.boot:spring-boot-starter-parent
              source: output.yml
              version-requirement: '>3.3.0'
        source:
            provider: github
            repo: arsatapathy/spring-boot-jdbc-demo
            directory: /
            commit: 23047f72c407aa92249945fc98f128c23d4e1e96
    credentials:
        - host: github.com
          password: $LOCAL_GITHUB_ACCESS_TOKEN
          type: git_source
          username: x-access-token
output:
    - type: update_dependency_list
      expect:
        data:
            dependencies:
                - name: org.springframework.boot:spring-boot-starter-parent
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: pom
                      requirement: 2.4.5
                      source: null
                  version: 2.4.5
                - name: org.springframework.boot:spring-boot-starter-web
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: jar
                      requirement: null
                      source: null
                  version: null
                - name: org.springframework.boot:spring-boot-starter-test
                  requirements:
                    - file: pom.xml
                      groups:
                        - test
                      metadata:
                        packaging_type: jar
                      requirement: null
                      source: null
                  version: null
                - name: org.springframework.boot:spring-boot-starter-log4j2
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: jar
                      requirement: null
                      source: null
                  version: null
                - name: org.springframework.boot:spring-boot-starter-jdbc
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: jar
                      requirement: null
                      source: null
                  version: null
                - name: com.oracle.database.jdbc:ojdbc8
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: jar
                      requirement: 21.13.0.0
                      source: null
                  version: 21.13.0.0
                - name: org.springframework.boot:spring-boot-maven-plugin
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: jar
                      requirement: null
                      source: null
                  version: null
            dependency_files:
                - /pom.xml
    - type: create_pull_request
      expect:
        data:
            base-commit-sha: 23047f72c407aa92249945fc98f128c23d4e1e96
            dependencies:
                - name: org.springframework.boot:spring-boot-starter-parent
                  previous-requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: pom
                      requirement: 2.4.5
                      source: null
                  previous-version: 2.4.5
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: pom
                      requirement: 3.3.0
                      source:
                        type: maven_repo
                        url: https://repo.maven.apache.org/maven2
                  version: 3.3.0
            updated-dependency-files:
                - content: |
                    <?xml version="1.0" encoding="UTF-8"?>
                    <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
                    	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
                    	<modelVersion>4.0.0</modelVersion>
                    	<parent>
                    		<groupId>org.springframework.boot</groupId>
                    		<artifactId>spring-boot-starter-parent</artifactId>
                    		<version>3.3.0</version>
                    		<relativePath/> <!-- lookup parent from repository -->
                    	</parent>
                    	<groupId>com.arsatapathy</groupId>
                    	<artifactId>spring-boot-jdbc-demo</artifactId>
                    	<version>0.0.1-SNAPSHOT</version>
                    	<name>spring-boot-jdbc-demo</name>
                    	<description>Demo Project for Spring Boot</description>
                    	<properties>
                    		<java.version>16</java.version>
                    	</properties>
                    	<dependencies>
                    		<dependency>
                    			<groupId>org.springframework.boot</groupId>
                    			<artifactId>spring-boot-starter-web</artifactId>
                    		</dependency>

                    		<dependency>
                    			<groupId>org.springframework.boot</groupId>
                    			<artifactId>spring-boot-starter-test</artifactId>
                    			<scope>test</scope>
                    		</dependency>

                    		<dependency>
                    			<groupId>org.springframework.boot</groupId>
                    			<artifactId>spring-boot-starter-log4j2</artifactId>
                    		</dependency>

                    		<dependency>
                    			<groupId>org.springframework.boot</groupId>
                    			<artifactId>spring-boot-starter-jdbc</artifactId>
                    		</dependency>

                    		<dependency>
                    			<groupId>com.oracle.database.jdbc</groupId>
                    			<artifactId>ojdbc8</artifactId>
                    			<version>21.13.0.0</version>
                    		</dependency>
                    	</dependencies>

                    	<build>
                    		<plugins>
                    			<plugin>
                    				<groupId>org.springframework.boot</groupId>
                    				<artifactId>spring-boot-maven-plugin</artifactId>
                    			</plugin>
                    		</plugins>
                    	</build>

                    </project>
                  content_encoding: utf-8
                  deleted: false
                  directory: /
                  name: pom.xml
                  operation: update
                  support_file: false
                  type: file
            pr-title: Bump org.springframework.boot:spring-boot-starter-parent from 2.4.5 to 3.3.0
            pr-body: |
                Bumps [org.springframework.boot:spring-boot-starter-parent](https://github.com/spring-projects/spring-boot) from 2.4.5 to 3.3.0.
                <details>
                <summary>Release notes</summary>
                <p><em>Sourced from <a href="https://github.com/spring-projects/spring-boot/releases">org.springframework.boot:spring-boot-starter-parent's releases</a>.</em></p>
                <blockquote>
                <h2>v3.3.0</h2>
                <h2>:star: New Features</h2>
                <ul>
                <li>Add support for descriptions of record components in configuration metadata generation <a href="https://redirect.github.com/spring-projects/spring-boot/pull/29403">#29403</a></li>
                </ul>
                <h2>:lady_beetle: Bug Fixes</h2>
                <ul>
                <li>gradlew bootBuildImage fails with Podman on macOS Sonoma <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40871">#40871</a></li>
                <li>Pulsar auth parameters don't properly encode JSON values <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40869">#40869</a></li>
                <li>When using JPA and ImportTestcontainers, test context may fail to refresh due to &quot;Mapped port can only be obtained after the container is started&quot; <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40863">#40863</a></li>
                <li>Default MIME mappings are not loaded unless additional mappings are configured <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40860">#40860</a></li>
                <li>Starting from 3.2.x, <code>@SpyBean</code> is not able to initialise MongoRepository bean of the generic type <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40855">#40855</a></li>
                <li>Auto-configuration ordering change breaks DocumentReference (in non-reactive MongoTemplate) when depending on mongodb-driver-reactivestreams <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40851">#40851</a></li>
                <li>Neo4jReactiveDataAutoConfiguration creates incorrectly named bean <a href="https://redirect.github.com/spring-projects/spring-boot/pull/40836">#40836</a></li>
                <li>Image building fails during cleanup when bind mount has read-only content <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40799">#40799</a></li>
                <li>Failure Analysis for InvalidConfigurationPropertyValueException is skipped when the property is not set <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40691">#40691</a></li>
                <li>IllegalArgumentException can be thrown when running an uber jar on a shared drive <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40643">#40643</a></li>
                <li>setReadTimeout can't be set via Reflective factory on JettyClientHttpRequestFactory <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40638">#40638</a></li>
                <li>URISyntaxException is raised if the spring boot application is started in a location that contains invalid URI characters <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40616">#40616</a></li>
                <li>resolveMainClassName fails when building with Gradle using Java 22 <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40613">#40613</a></li>
                <li>AnsiOutput.detectIfAnsiCapable broken on JDK22 <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40609">#40609</a></li>
                <li>Help information for spring init's build option has the wrong default <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40606">#40606</a></li>
                <li>JarUrlConnection.getPermission() can throw NullPointerException if jarFileConnection is null <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40599">#40599</a></li>
                <li>Whitespace is not correctly trimmed when generating configuration properties metadata from records <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40593">#40593</a></li>
                <li>In some situations, the failure when the AOT-generated initializer cannot be loaded is less helpful than before <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40584">#40584</a></li>
                <li>Properties binding eagerly creates superfluous maps <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40561">#40561</a></li>
                <li>Configuring SSL bundle reload for non-file resource types causes errors that are difficult to diagnose <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40560">#40560</a></li>
                <li>spring-boot-dependencies cannot be used with repositories that ban com.oracle.database.jdbc:ojdbc-bom <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40535">#40535</a></li>
                <li>Buildpacks do not support Docker with containerd image store <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40526">#40526</a></li>
                <li>SpringBootMockMvcBuilderCustomizer can crash cryptically while collecting data that it would have discarded anyway <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40517">#40517</a></li>
                <li>Containers not shut down between tests when using .withReuse(true) but env. does not support reuse (e.g. CI builds) <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40509">#40509</a></li>
                <li>CookieSameSiteSupplier influences session cookie <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40501">#40501</a></li>
                <li><code>&lt;springProperty&gt;</code> and <code>&lt;springProfile&gt;</code> do not work in <code>&lt;include&gt;</code> after Logback upgrade <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40491">#40491</a></li>
                <li>Runtime hint registration for property binding should not fail when parameter information is unavailable <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40486">#40486</a></li>
                <li>ServiceLevelObjectiveBoundary properties cannot be bound in a native image application <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40483">#40483</a></li>
                <li>server.error.include-binding-errors does not recognize MethodValidationResult exceptions <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40474">#40474</a></li>
                <li>spring.data.redis.cluster.nodes and spring.data.redis.sentinel.nodes do not handle IPv6 addresses correctly <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40467">#40467</a></li>
                <li>Using relative paths to describe the classpath in the error message from ResolveMainClassName hinders problem diagnosis <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40465">#40465</a></li>
                <li>Jartools extract command doesn't extract all files from META-INF <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40456">#40456</a></li>
                <li>Native image doesn't start and doesn't log anything if an environment post processor throws an exception <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40451">#40451</a></li>
                <li>Unlike DataSourceAutoConfiguration, DevToolsDataSourceAutoConfiguration assumes that javax.sql.DataSource will always be available <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40441">#40441</a></li>
                </ul>
                <h2>:notebook_with_decorative_cover: Documentation</h2>
                <ul>
                <li>Improve graceful shutdown documentation to remove ambiguity <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40846">#40846</a></li>
                <li>Document ways to opt out from immutable <code>@ConfigurationProperties</code> binding with single constructor <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40844">#40844</a></li>
                <li>Document that a custom HttpMessageConverters bean can be used to reorder json message converters when needed <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40839">#40839</a></li>
                <li>Address ambiguity now that Testcontainers has two classes named KafkaContainer <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40756">#40756</a></li>
                <li>Publish API documentation for Spring Boot's Kotlin APIs <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40692">#40692</a></li>
                <li>Fix typo in features doc <a href="https://redirect.github.com/spring-projects/spring-boot/pull/40631">#40631</a></li>
                </ul>
                <!-- raw HTML omitted -->
                </blockquote>
                <p>... (truncated)</p>
                </details>
                <details>
                <summary>Commits</summary>
                <ul>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/a25e1ebe41bc02c5e7341ed1464d61c496cffe7c"><code>a25e1eb</code></a> Release v3.3.0</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/ed0a3fd90845ebfa6a851c7c5d712a0ba0dcaa69"><code>ed0a3fd</code></a> Update publish-to-sdkman job to make new candidates the default</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/42d6f2c7a85690a444c1555fea2d72f3576f6d0b"><code>42d6f2c</code></a> Merge branch '3.2.x'</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/234e0fd1f395ed284cd8b4726c9b73d695c28b27"><code>234e0fd</code></a> Stop mark 3.2.x as the default SDKman release</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/226b900babb25112e0ef0dcb02e2c06ce18564dd"><code>226b900</code></a> Merge branch '3.2.x'</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/c857eb62d483865bc260ea1becab4bb456468772"><code>c857eb6</code></a> Fix SDKman &quot;make default&quot; step</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/13e13f91c09f5012eb3bc61d39455ae5d4b43eff"><code>13e13f9</code></a> Merge branch '3.2.x'</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/a5ee37c5262270a8d6a0e898a441f35677310d59"><code>a5ee37c</code></a> Next development version (v3.2.7-SNAPSHOT)</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/dffdd6d67ca0f1b46cf2645439a3552fa6c5f5d2"><code>dffdd6d</code></a> Explicitly set SDKman's make-default to false</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/86c206a849b746127be234ec3febd5eac5fc357e"><code>86c206a</code></a> Merge branch '3.2.x'</li>
                <li>Additional commits viewable in <a href="https://github.com/spring-projects/spring-boot/compare/v2.4.5...v3.3.0">compare view</a></li>
                </ul>
                </details>
                <br />
            commit-message: |-
                Bump org.springframework.boot:spring-boot-starter-parent

                Bumps [org.springframework.boot:spring-boot-starter-parent](https://github.com/spring-projects/spring-boot) from 2.4.5 to 3.3.0.
                - [Release notes](https://github.com/spring-projects/spring-boot/releases)
                - [Commits](https://github.com/spring-projects/spring-boot/compare/v2.4.5...v3.3.0)
    - type: mark_as_processed
      expect:
        data:
            base-commit-sha: 23047f72c407aa92249945fc98f128c23d4e1e96

```

## Scan and update a dependencies to a specific version  

### job.yaml
```yaml
job:
  package-manager: maven
  allowed-updates:
    - dependency-name: "org.springframework.boot:spring-boot-starter-parent"
      update-type: "all"  # Ensures all types of updates are allowed for this dependency
  ignore-conditions:
    - dependency-name: "org.springframework.boot:spring-boot-starter-parent"
      version-requirement: "!= 3.2.6" # Ensures that any versions other than 3.2.6 are ignored
  source:
    provider: github
    repo: arsatapathy/spring-boot-jdbc-demo
    directory: "/"
```

### output.yaml
```yaml
input:
    job:
        package-manager: maven
        allowed-updates:
            - dependency-name: org.springframework.boot:spring-boot-starter-parent
              update-type: all
        ignore-conditions:
            - dependency-name: org.springframework.boot:spring-boot-starter-parent
              version-requirement: '!= 3.2.6'
        source:
            provider: github
            repo: arsatapathy/spring-boot-jdbc-demo
            directory: /
            commit: 23047f72c407aa92249945fc98f128c23d4e1e96
    credentials:
        - host: github.com
          password: $LOCAL_GITHUB_ACCESS_TOKEN
          type: git_source
          username: x-access-token
output:
    - type: update_dependency_list
      expect:
        data:
            dependencies:
                - name: org.springframework.boot:spring-boot-starter-parent
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: pom
                      requirement: 2.4.5
                      source: null
                  version: 2.4.5
                - name: org.springframework.boot:spring-boot-starter-web
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: jar
                      requirement: null
                      source: null
                  version: null
                - name: org.springframework.boot:spring-boot-starter-test
                  requirements:
                    - file: pom.xml
                      groups:
                        - test
                      metadata:
                        packaging_type: jar
                      requirement: null
                      source: null
                  version: null
                - name: org.springframework.boot:spring-boot-starter-log4j2
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: jar
                      requirement: null
                      source: null
                  version: null
                - name: org.springframework.boot:spring-boot-starter-jdbc
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: jar
                      requirement: null
                      source: null
                  version: null
                - name: com.oracle.database.jdbc:ojdbc8
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: jar
                      requirement: 21.13.0.0
                      source: null
                  version: 21.13.0.0
                - name: org.springframework.boot:spring-boot-maven-plugin
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: jar
                      requirement: null
                      source: null
                  version: null
            dependency_files:
                - /pom.xml
    - type: create_pull_request
      expect:
        data:
            base-commit-sha: 23047f72c407aa92249945fc98f128c23d4e1e96
            dependencies:
                - name: org.springframework.boot:spring-boot-starter-parent
                  previous-requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: pom
                      requirement: 2.4.5
                      source: null
                  previous-version: 2.4.5
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: pom
                      requirement: 3.2.6
                      source:
                        type: maven_repo
                        url: https://repo.maven.apache.org/maven2
                  version: 3.2.6
            updated-dependency-files:
                - content: |
                    <?xml version="1.0" encoding="UTF-8"?>
                    <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
                    	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
                    	<modelVersion>4.0.0</modelVersion>
                    	<parent>
                    		<groupId>org.springframework.boot</groupId>
                    		<artifactId>spring-boot-starter-parent</artifactId>
                    		<version>3.2.6</version>
                    		<relativePath/> <!-- lookup parent from repository -->
                    	</parent>
                    	<groupId>com.arsatapathy</groupId>
                    	<artifactId>spring-boot-jdbc-demo</artifactId>
                    	<version>0.0.1-SNAPSHOT</version>
                    	<name>spring-boot-jdbc-demo</name>
                    	<description>Demo Project for Spring Boot</description>
                    	<properties>
                    		<java.version>16</java.version>
                    	</properties>
                    	<dependencies>
                    		<dependency>
                    			<groupId>org.springframework.boot</groupId>
                    			<artifactId>spring-boot-starter-web</artifactId>
                    		</dependency>

                    		<dependency>
                    			<groupId>org.springframework.boot</groupId>
                    			<artifactId>spring-boot-starter-test</artifactId>
                    			<scope>test</scope>
                    		</dependency>

                    		<dependency>
                    			<groupId>org.springframework.boot</groupId>
                    			<artifactId>spring-boot-starter-log4j2</artifactId>
                    		</dependency>

                    		<dependency>
                    			<groupId>org.springframework.boot</groupId>
                    			<artifactId>spring-boot-starter-jdbc</artifactId>
                    		</dependency>

                    		<dependency>
                    			<groupId>com.oracle.database.jdbc</groupId>
                    			<artifactId>ojdbc8</artifactId>
                    			<version>21.13.0.0</version>
                    		</dependency>
                    	</dependencies>

                    	<build>
                    		<plugins>
                    			<plugin>
                    				<groupId>org.springframework.boot</groupId>
                    				<artifactId>spring-boot-maven-plugin</artifactId>
                    			</plugin>
                    		</plugins>
                    	</build>

                    </project>
                  content_encoding: utf-8
                  deleted: false
                  directory: /
                  name: pom.xml
                  operation: update
                  support_file: false
                  type: file
            pr-title: Bump org.springframework.boot:spring-boot-starter-parent from 2.4.5 to 3.2.6
            pr-body: |
                Bumps [org.springframework.boot:spring-boot-starter-parent](https://github.com/spring-projects/spring-boot) from 2.4.5 to 3.2.6.
                <details>
                <summary>Release notes</summary>
                <p><em>Sourced from <a href="https://github.com/spring-projects/spring-boot/releases">org.springframework.boot:spring-boot-starter-parent's releases</a>.</em></p>
                <blockquote>
                <h2>v3.2.6</h2>
                <h2>:lady_beetle: Bug Fixes</h2>
                <ul>
                <li>Image building fails during cleanup when bind mount has read-only content <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40760">#40760</a></li>
                <li>Failure Analysis for InvalidConfigurationPropertyValueException is skipped when the property is not set <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40690">#40690</a></li>
                <li>setReadTimeout can't be set via Reflective factory on JettyClientHttpRequestFactory <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40635">#40635</a></li>
                <li>URISyntaxException is raised if the spring boot application is started in a location that contains invalid URI characters <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40615">#40615</a></li>
                <li>Help information for spring init's build option has the wrong default <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40605">#40605</a></li>
                <li>When using JPA and ImportTestcontainers, test context may fail to refresh due to &quot;Mapped port can only be obtained after the container is started&quot; <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40585">#40585</a></li>
                <li>IllegalArgumentException can be thrown when running an uber jar on a shared drive <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40549">#40549</a></li>
                <li>spring-boot-dependencies cannot be used with repositories that ban com.oracle.database.jdbc:ojdbc-bom <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40534">#40534</a></li>
                <li>SpringBootMockMvcBuilderCustomizer can crash cryptically while collecting data that it would have discarded anyway <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40516">#40516</a></li>
                <li>Containers not shut down between tests when using .withReuse(true) but env. does not support reuse (e.g. CI builds) <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40508">#40508</a></li>
                <li>Pulsar auth parameters don't properly encode JSON values <a href="https://redirect.github.com/spring-projects/spring-boot/pull/40493">#40493</a></li>
                <li>Runtime hint registration for property binding should not fail when parameter information is unavailable <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40485">#40485</a></li>
                <li>ServiceLevelObjectiveBoundary properties cannot be bound in a native image application <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40482">#40482</a></li>
                <li>spring.data.redis.cluster.nodes and spring.data.redis.sentinel.nodes do not handle IPv6 addresses correctly <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40466">#40466</a></li>
                <li>Using relative paths to describe the classpath in the error message from ResolveMainClassName hinders problem diagnosis <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40464">#40464</a></li>
                <li>Native image doesn't start and doesn't log anything if an environment post processor throws an exception <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40450">#40450</a></li>
                <li>Unlike DataSourceAutoConfiguration, DevToolsDataSourceAutoConfiguration assumes that javax.sql.DataSource will always be available <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40440">#40440</a></li>
                <li>Starting from 3.2.x, <code>@SpyBean</code> is not able to initialise MongoRepository bean of the generic type <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40234">#40234</a></li>
                <li>AnsiOutput.detectIfAnsiCapable broken on JDK22 <a href="https://redirect.github.com/spring-projects/spring-boot/pull/40172">#40172</a></li>
                <li>Buildpacks do not support Docker with containerd image store <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40100">#40100</a></li>
                <li>resolveMainClassName fails when building with Gradle using Java 22 <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40074">#40074</a></li>
                <li>server.error.include-binding-errors does not recognize MethodValidationResult exceptions <a href="https://redirect.github.com/spring-projects/spring-boot/pull/39865">#39865</a></li>
                <li>JarUrlConnection.getPermission() can throw NullPointerException if jarFileConnection is null <a href="https://redirect.github.com/spring-projects/spring-boot/pull/39856">#39856</a></li>
                <li>gradlew bootBuildImage fails with Podman on macOS Sonoma <a href="https://redirect.github.com/spring-projects/spring-boot/issues/39830">#39830</a></li>
                <li>CookieSameSiteSupplier influences session cookie <a href="https://redirect.github.com/spring-projects/spring-boot/issues/39766">#39766</a></li>
                <li>Auto-configuration ordering change breaks DocumentReference (in non-reactive MongoTemplate) when depending on mongodb-driver-reactivestreams <a href="https://redirect.github.com/spring-projects/spring-boot/issues/39405">#39405</a></li>
                <li>Properties binding eagerly creates superfluous maps <a href="https://redirect.github.com/spring-projects/spring-boot/issues/39375">#39375</a></li>
                <li>Configuring SSL bundle reload for non-file resource types causes errors that are difficult to diagnose <a href="https://redirect.github.com/spring-projects/spring-boot/issues/38903">#38903</a></li>
                <li>In some situations, the failure when the AOT-generated initializer cannot be loaded is less helpful than before <a href="https://redirect.github.com/spring-projects/spring-boot/issues/38645">#38645</a></li>
                </ul>
                <h2>:notebook_with_decorative_cover: Documentation</h2>
                <ul>
                <li>Improve graceful shutdown documentation to remove ambiguity <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40845">#40845</a></li>
                <li>Document ways to opt out from immutable <code>@ConfigurationProperties</code> binding with single constructor <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40843">#40843</a></li>
                <li>Document that a custom HttpMessageConverters bean can be used to reorder json message converters when needed <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40838">#40838</a></li>
                <li>Address ambiguity now that Testcontainers has two classes named KafkaContainer <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40699">#40699</a></li>
                <li>Clarify devtools restart class loader <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40607">#40607</a></li>
                <li>Note that spring-boot-docker-compose is excluded by default from packaged jars <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40564">#40564</a></li>
                <li>Clarify docs around spring.jpa.generate-ddl <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40522">#40522</a></li>
                <li>Clarify the directory that's used by default to find Docker Compose compose.yaml <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40514">#40514</a></li>
                <li>Clarify that all named properties must match for <code>@ConditionalOnProperty</code> to match <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40470">#40470</a></li>
                <li>Links to Spring Batch javadoc for EnableBatchProcessing and DefaultBatchConfiguration are broken <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40468">#40468</a></li>
                <li>Suggest testAndDevelopmentOnly configuration when using Docker Compose support in tests <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40171">#40171</a></li>
                </ul>
                <h2>:hammer: Dependency Upgrades</h2>
                <ul>
                <li>Upgrade to Byte Buddy 1.14.16 <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40877">#40877</a></li>
                </ul>
                <!-- raw HTML omitted -->
                </blockquote>
                <p>... (truncated)</p>
                </details>
                <details>
                <summary>Commits</summary>
                <ul>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/106ae499ca2ac2150bf5e4e72b0dfa3bff359c97"><code>106ae49</code></a> Release v3.2.6</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/f9c10f31154c69b402d2be4202421a0433c0fb2c"><code>f9c10f3</code></a> Merge branch '3.1.x' into 3.2.x</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/6b0f8756d5fc3dd3203abcb3707ad9e160a17e96"><code>6b0f875</code></a> Next development version (v3.1.13-SNAPSHOT)</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/e77ffd819a73cd423969ef7b4620a8f57e930b02"><code>e77ffd8</code></a> Upgrade to Spring Framework 6.1.8</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/477cdcae21f2e5f973059924aaef7791c7380df7"><code>477cdca</code></a> Upgrade to Spring Batch 5.1.2</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/6ca3db067d46be93a7a826e23643e72cc49a8908"><code>6ca3db0</code></a> Upgrade to Netty 4.1.110.Final</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/0ffd7e6910a5113564264d98bb0e1773b121d457"><code>0ffd7e6</code></a> Upgrade to Byte Buddy 1.14.16</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/9437ab96f415c05623e0450b7aca0ea585099b24"><code>9437ab9</code></a> Merge branch '3.1.x' into 3.2.x</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/5620994bf1087175724f64d8df902d000c5a1c33"><code>5620994</code></a> Upgrade to Spring Framework 6.0.21</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/29dbc047aea5677b24667143af9fdc823c5f0d1a"><code>29dbc04</code></a> Upgrade to Netty 4.1.110.Final</li>
                <li>Additional commits viewable in <a href="https://github.com/spring-projects/spring-boot/compare/v2.4.5...v3.2.6">compare view</a></li>
                </ul>
                </details>
                <br />
            commit-message: |-
                Bump org.springframework.boot:spring-boot-starter-parent

                Bumps [org.springframework.boot:spring-boot-starter-parent](https://github.com/spring-projects/spring-boot) from 2.4.5 to 3.2.6.
                - [Release notes](https://github.com/spring-projects/spring-boot/releases)
                - [Commits](https://github.com/spring-projects/spring-boot/compare/v2.4.5...v3.2.6)
    - type: mark_as_processed
      expect:
        data:
            base-commit-sha: 23047f72c407aa92249945fc98f128c23d4e1e96
```

## Scan and update a project with breaking change 

### job.yaml
```yaml
job:
  package-manager: maven
  allowed-updates:
    - dependency-name: "org.springframework.boot:spring-boot-starter-parent"
      update-type: "all"  # Ensures all types of updates are allowed for this dependency
  source:
    provider: github
    repo: arsatapathy/spring-boot-security-jwt-demo
    directory: "/"
```

### output.yaml
```yaml
input:
    job:
        package-manager: maven
        allowed-updates:
            - dependency-name: org.springframework.boot:spring-boot-starter-parent
              update-type: all
        ignore-conditions:
            - dependency-name: org.springframework.boot:spring-boot-starter-parent
              source: output.yaml
              version-requirement: '>3.3.0'
        source:
            provider: github
            repo: arsatapathy/spring-boot-security-jwt-demo
            directory: /
            commit: 874c3fc600c21195c6b2217b1f515014f52d843a
    credentials:
        - host: github.com
          password: $LOCAL_GITHUB_ACCESS_TOKEN
          type: git_source
          username: x-access-token
output:
    - type: update_dependency_list
      expect:
        data:
            dependencies:
                - name: org.springframework.boot:spring-boot-starter-parent
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: pom
                      requirement: 2.2.4.RELEASE
                      source: null
                  version: 2.2.4.RELEASE
                - name: org.springframework.boot:spring-boot-starter-security
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: jar
                      requirement: null
                      source: null
                  version: null
                - name: org.springframework.boot:spring-boot-starter-web
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: jar
                      requirement: null
                      source: null
                  version: null
                - name: io.jsonwebtoken:jjwt
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: jar
                      requirement: 0.9.1
                      source: null
                  version: 0.9.1
                - name: javax.xml.bind:jaxb-api
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: jar
                      requirement: 2.3.0
                      source: null
                  version: 2.3.0
                - name: org.springframework.boot:spring-boot-starter-test
                  requirements:
                    - file: pom.xml
                      groups:
                        - test
                      metadata:
                        packaging_type: jar
                      requirement: null
                      source: null
                  version: null
                - name: org.springframework.security:spring-security-test
                  requirements:
                    - file: pom.xml
                      groups:
                        - test
                      metadata:
                        packaging_type: jar
                      requirement: null
                      source: null
                  version: null
                - name: org.apache.logging.log4j:log4j-api
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: jar
                      requirement: 2.14.1
                      source: null
                  version: 2.14.1
                - name: org.springframework.boot:spring-boot-maven-plugin
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: jar
                      requirement: null
                      source: null
                  version: null
            dependency_files:
                - /pom.xml
    - type: create_pull_request
      expect:
        data:
            base-commit-sha: 874c3fc600c21195c6b2217b1f515014f52d843a
            dependencies:
                - name: org.springframework.boot:spring-boot-starter-parent
                  previous-requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: pom
                      requirement: 2.2.4.RELEASE
                      source: null
                  previous-version: 2.2.4.RELEASE
                  requirements:
                    - file: pom.xml
                      groups: []
                      metadata:
                        packaging_type: pom
                      requirement: 3.3.0
                      source:
                        type: maven_repo
                        url: https://repo.maven.apache.org/maven2
                  version: 3.3.0
            updated-dependency-files:
                - content: |
                    <?xml version="1.0" encoding="UTF-8"?>
                    <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
                    	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
                    	<modelVersion>4.0.0</modelVersion>
                    	<parent>
                    		<groupId>org.springframework.boot</groupId>
                    		<artifactId>spring-boot-starter-parent</artifactId>
                    		<version>3.3.0</version>
                    		<relativePath/> <!-- lookup parent from repository -->
                    	</parent>
                    	<groupId>com.arsatapathy</groupId>
                    	<artifactId>spring-boot-security-jwt-demo</artifactId>
                    	<version>0.0.1-SNAPSHOT</version>
                    	<name>spring-boot-security-jwt-demo</name>
                    	<description>Demo project for Spring Security using Spring Boot JWT</description>
                    	<properties>
                    		<java.version>11</java.version>
                    	</properties>
                    	<dependencies>
                    		<dependency>
                    			<groupId>org.springframework.boot</groupId>
                    			<artifactId>spring-boot-starter-security</artifactId>
                    		</dependency>
                    		<dependency>
                    			<groupId>org.springframework.boot</groupId>
                    			<artifactId>spring-boot-starter-web</artifactId>
                    		</dependency>
                    		<dependency>
                    			<groupId>io.jsonwebtoken</groupId>
                    			<artifactId>jjwt</artifactId>
                    			<version>0.9.1</version>
                    		</dependency>
                    		<dependency>
                    			<groupId>javax.xml.bind</groupId>
                    			<artifactId>jaxb-api</artifactId>
                    			<version>2.3.0</version>
                    		</dependency>

                    		<dependency>
                    			<groupId>org.springframework.boot</groupId>
                    			<artifactId>spring-boot-starter-test</artifactId>
                    			<scope>test</scope>
                    		</dependency>
                    		<dependency>
                    			<groupId>org.springframework.security</groupId>
                    			<artifactId>spring-security-test</artifactId>
                    			<scope>test</scope>
                    		</dependency>
                    	        <dependency>
                    	            <groupId>org.apache.logging.log4j</groupId>
                    	            <artifactId>log4j-api</artifactId>
                    	            <version>2.14.1</version>
                    	        </dependency>
                    	</dependencies>

                    	<build>
                    		<plugins>
                    			<plugin>
                    				<groupId>org.springframework.boot</groupId>
                    				<artifactId>spring-boot-maven-plugin</artifactId>
                    			</plugin>
                    		</plugins>
                    	</build>

                    </project>
                  content_encoding: utf-8
                  deleted: false
                  directory: /
                  name: pom.xml
                  operation: update
                  support_file: false
                  type: file
            pr-title: Bump org.springframework.boot:spring-boot-starter-parent from 2.2.4.RELEASE to 3.3.0
            pr-body: |
                Bumps [org.springframework.boot:spring-boot-starter-parent](https://github.com/spring-projects/spring-boot) from 2.2.4.RELEASE to 3.3.0.
                <details>
                <summary>Release notes</summary>
                <p><em>Sourced from <a href="https://github.com/spring-projects/spring-boot/releases">org.springframework.boot:spring-boot-starter-parent's releases</a>.</em></p>
                <blockquote>
                <h2>v3.3.0</h2>
                <h2>:star: New Features</h2>
                <ul>
                <li>Add support for descriptions of record components in configuration metadata generation <a href="https://redirect.github.com/spring-projects/spring-boot/pull/29403">#29403</a></li>
                </ul>
                <h2>:lady_beetle: Bug Fixes</h2>
                <ul>
                <li>gradlew bootBuildImage fails with Podman on macOS Sonoma <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40871">#40871</a></li>
                <li>Pulsar auth parameters don't properly encode JSON values <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40869">#40869</a></li>
                <li>When using JPA and ImportTestcontainers, test context may fail to refresh due to &quot;Mapped port can only be obtained after the container is started&quot; <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40863">#40863</a></li>
                <li>Default MIME mappings are not loaded unless additional mappings are configured <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40860">#40860</a></li>
                <li>Starting from 3.2.x, <code>@SpyBean</code> is not able to initialise MongoRepository bean of the generic type <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40855">#40855</a></li>
                <li>Auto-configuration ordering change breaks DocumentReference (in non-reactive MongoTemplate) when depending on mongodb-driver-reactivestreams <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40851">#40851</a></li>
                <li>Neo4jReactiveDataAutoConfiguration creates incorrectly named bean <a href="https://redirect.github.com/spring-projects/spring-boot/pull/40836">#40836</a></li>
                <li>Image building fails during cleanup when bind mount has read-only content <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40799">#40799</a></li>
                <li>Failure Analysis for InvalidConfigurationPropertyValueException is skipped when the property is not set <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40691">#40691</a></li>
                <li>IllegalArgumentException can be thrown when running an uber jar on a shared drive <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40643">#40643</a></li>
                <li>setReadTimeout can't be set via Reflective factory on JettyClientHttpRequestFactory <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40638">#40638</a></li>
                <li>URISyntaxException is raised if the spring boot application is started in a location that contains invalid URI characters <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40616">#40616</a></li>
                <li>resolveMainClassName fails when building with Gradle using Java 22 <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40613">#40613</a></li>
                <li>AnsiOutput.detectIfAnsiCapable broken on JDK22 <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40609">#40609</a></li>
                <li>Help information for spring init's build option has the wrong default <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40606">#40606</a></li>
                <li>JarUrlConnection.getPermission() can throw NullPointerException if jarFileConnection is null <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40599">#40599</a></li>
                <li>Whitespace is not correctly trimmed when generating configuration properties metadata from records <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40593">#40593</a></li>
                <li>In some situations, the failure when the AOT-generated initializer cannot be loaded is less helpful than before <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40584">#40584</a></li>
                <li>Properties binding eagerly creates superfluous maps <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40561">#40561</a></li>
                <li>Configuring SSL bundle reload for non-file resource types causes errors that are difficult to diagnose <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40560">#40560</a></li>
                <li>spring-boot-dependencies cannot be used with repositories that ban com.oracle.database.jdbc:ojdbc-bom <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40535">#40535</a></li>
                <li>Buildpacks do not support Docker with containerd image store <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40526">#40526</a></li>
                <li>SpringBootMockMvcBuilderCustomizer can crash cryptically while collecting data that it would have discarded anyway <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40517">#40517</a></li>
                <li>Containers not shut down between tests when using .withReuse(true) but env. does not support reuse (e.g. CI builds) <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40509">#40509</a></li>
                <li>CookieSameSiteSupplier influences session cookie <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40501">#40501</a></li>
                <li><code>&lt;springProperty&gt;</code> and <code>&lt;springProfile&gt;</code> do not work in <code>&lt;include&gt;</code> after Logback upgrade <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40491">#40491</a></li>
                <li>Runtime hint registration for property binding should not fail when parameter information is unavailable <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40486">#40486</a></li>
                <li>ServiceLevelObjectiveBoundary properties cannot be bound in a native image application <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40483">#40483</a></li>
                <li>server.error.include-binding-errors does not recognize MethodValidationResult exceptions <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40474">#40474</a></li>
                <li>spring.data.redis.cluster.nodes and spring.data.redis.sentinel.nodes do not handle IPv6 addresses correctly <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40467">#40467</a></li>
                <li>Using relative paths to describe the classpath in the error message from ResolveMainClassName hinders problem diagnosis <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40465">#40465</a></li>
                <li>Jartools extract command doesn't extract all files from META-INF <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40456">#40456</a></li>
                <li>Native image doesn't start and doesn't log anything if an environment post processor throws an exception <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40451">#40451</a></li>
                <li>Unlike DataSourceAutoConfiguration, DevToolsDataSourceAutoConfiguration assumes that javax.sql.DataSource will always be available <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40441">#40441</a></li>
                </ul>
                <h2>:notebook_with_decorative_cover: Documentation</h2>
                <ul>
                <li>Improve graceful shutdown documentation to remove ambiguity <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40846">#40846</a></li>
                <li>Document ways to opt out from immutable <code>@ConfigurationProperties</code> binding with single constructor <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40844">#40844</a></li>
                <li>Document that a custom HttpMessageConverters bean can be used to reorder json message converters when needed <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40839">#40839</a></li>
                <li>Address ambiguity now that Testcontainers has two classes named KafkaContainer <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40756">#40756</a></li>
                <li>Publish API documentation for Spring Boot's Kotlin APIs <a href="https://redirect.github.com/spring-projects/spring-boot/issues/40692">#40692</a></li>
                <li>Fix typo in features doc <a href="https://redirect.github.com/spring-projects/spring-boot/pull/40631">#40631</a></li>
                </ul>
                <!-- raw HTML omitted -->
                </blockquote>
                <p>... (truncated)</p>
                </details>
                <details>
                <summary>Commits</summary>
                <ul>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/a25e1ebe41bc02c5e7341ed1464d61c496cffe7c"><code>a25e1eb</code></a> Release v3.3.0</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/ed0a3fd90845ebfa6a851c7c5d712a0ba0dcaa69"><code>ed0a3fd</code></a> Update publish-to-sdkman job to make new candidates the default</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/42d6f2c7a85690a444c1555fea2d72f3576f6d0b"><code>42d6f2c</code></a> Merge branch '3.2.x'</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/234e0fd1f395ed284cd8b4726c9b73d695c28b27"><code>234e0fd</code></a> Stop mark 3.2.x as the default SDKman release</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/226b900babb25112e0ef0dcb02e2c06ce18564dd"><code>226b900</code></a> Merge branch '3.2.x'</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/c857eb62d483865bc260ea1becab4bb456468772"><code>c857eb6</code></a> Fix SDKman &quot;make default&quot; step</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/13e13f91c09f5012eb3bc61d39455ae5d4b43eff"><code>13e13f9</code></a> Merge branch '3.2.x'</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/a5ee37c5262270a8d6a0e898a441f35677310d59"><code>a5ee37c</code></a> Next development version (v3.2.7-SNAPSHOT)</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/dffdd6d67ca0f1b46cf2645439a3552fa6c5f5d2"><code>dffdd6d</code></a> Explicitly set SDKman's make-default to false</li>
                <li><a href="https://github.com/spring-projects/spring-boot/commit/86c206a849b746127be234ec3febd5eac5fc357e"><code>86c206a</code></a> Merge branch '3.2.x'</li>
                <li>Additional commits viewable in <a href="https://github.com/spring-projects/spring-boot/compare/v2.2.4.RELEASE...v3.3.0">compare view</a></li>
                </ul>
                </details>
                <br />
            commit-message: |-
                Bump org.springframework.boot:spring-boot-starter-parent

                Bumps [org.springframework.boot:spring-boot-starter-parent](https://github.com/spring-projects/spring-boot) from 2.2.4.RELEASE to 3.3.0.
                - [Release notes](https://github.com/spring-projects/spring-boot/releases)
                - [Commits](https://github.com/spring-projects/spring-boot/compare/v2.2.4.RELEASE...v3.3.0)
    - type: mark_as_processed
      expect:
        data:
            base-commit-sha: 874c3fc600c21195c6b2217b1f515014f52d843a
```

### PR
[# Bump org.springframework.boot:spring-boot-starter-parent from 2.2.4.RELEASE to 3.3.0 #1](https://github.com/arsatapathy/spring-boot-security-jwt-demo/pull/1)

### Preloading images 
`go/bin/dependabot update -f code/depupgrade/input.yaml -o code/depupgrade/test-output.yaml --proxy-image ghcr.io/github/dependabot-update-job-proxy/dependabot-update-job-proxy:v2.0.20240419172112`

- If the image is preloaded then the cli won't download it 

### Intercepting dependabot proxy 
```
start container
===============
docker run --rm -it --add-host host.docker.internal:host-gateway -p 8080:8080 -p 8081:8081 mitmproxy/mitmproxy mitmweb --web-host 0.0.0.0


copy certificates from proxy container 
======================================
docker cp <container-id>:/home/mitmproxy/.mitmproxy/mitmproxy-ca-cert.pem /home/ec2-user/dependabot/mitmproxy-ca-cert.pem

proxy image
===========
# Use the Dependabot proxy base image
FROM ghcr.io/github/dependabot-update-job-proxy/dependabot-update-job-proxy:latest 

# Set proxy environment variables to point to your existing mitmproxy instance
ENV http_proxy=http://host.docker.internal:8080
ENV https_proxy=http://host.docker.internal:8080

# Certificates
RUN mkdir -p /usr/local/share/ca-certificates
COPY mitmproxy-ca-cert.pem /usr/local/share/ca-certificates/mitmproxy-ca-cert.crt
RUN update-ca-certificates

docker build 
============
docker build -f proxy.Dockerfile -t dependabot-proxy-with-mitm .

dependabot update
=================
dependabot update -f input.yaml -o output.yaml --proxy-image dependabot-proxy-with-mitm:latest
```


![[mitmproxy.png]]