# blackduck-pkgscanner
A custom action for dependency package scanning using Blackduck for SCA.

## Inputs
### `BLACKDUCK_URL`
  Required
### `BLACKDUCK_API_TOKEN`
  Required
### `BLACKDUCK_PROJECT_NAME`
  Required
### `BLACKDUCK_PROJECT_VERSION`
  Required
### `DETECTOR_SEARCH_DEPTH`
  Optional 
  Default: 4
### `DETECT_SOURCE_PATH`
  Optional
  Default: '.' 
### `DETECT_PROJECT_VERSION_DISTR`
  Optional - EXTERNAL,INTERNAL,OPENSOURCE,SAAS
  Default: SAAS
### `DETECT_LOGGING_LEVEL`
  Optional - OFF,ERROR,WARN,INFO,DEBUG,TRACE
  Default: INFO
### `DETECT_TIMEOUT`
  Optional
  Default: 300 (seconds)
### `DETECT_POLICY_CHECK_FAIL_ON_SEVERITIES`
  Optional - ALL,NONE,BLOCKER,CRITICAL,MAJOR,MINOR,TRIVIAL,UNSPECIFIED
  Default: ALL
### `ADDITIONAL_OPTS`
  Optional
  Default: ' '                         

## Usage 
### Minimum configuration in action workflow

```yaml
uses: sukot1/blackduck-pkgscanner@v0.01
  with:
    BLACKDUCK_URL: <<your_server_url>>
    BLACKDUCK_API_TOKEN: <<your_access_token>>
    BLACKDUCK_PROJECT_NAME: <<your_project_name>>
    BLACKDUCK_PROJECT_VERSION: <<your_project_version>>
```
### Using additional options and policy checks

```yaml
uses: sukot1/blackduck-pkgscanner@v0.01
  with:
    BLACKDUCK_URL: <<your_server_url>>
    BLACKDUCK_API_TOKEN: <<your_access_token>>
    BLACKDUCK_PROJECT_NAME: <<your_project_name>>
    BLACKDUCK_PROJECT_VERSION: <<your_project_version>>
    DETECT_POLICY_CHECK_FAIL_ON_SEVERITIES: 'BLOCKER'
```

> Please refer to Synopsys official [documentation](https://community.synopsys.com/s/document-item?bundleId=integrations-detect&topicId=properties%2Fall-properties.html&_LANG=enus) for a full list of configurable Detect properties for package scanning.
