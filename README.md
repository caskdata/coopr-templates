# Coopr Templates

This repository contains the default set of templates used by [Coopr](http://coopr.io) by Cask and
some helper scripts to work with the templates.

## Templates
Templates fall into one of two categories, templates which define hardware, and templates which define
software. The hardware templates define variables used to provision compute resources on the public or
private cloud and correspond to Provider plugins. The software templates define automation capabilities
and configuration for Automator plugins.

### Hardware
- providers - set of credentials and variables used to connect to provider APIs
- hardwaretypes - abstraction of hardware to provider-specific instance types
- imagetypes - abstraction of image to provider-specific images

### Software
- services - defines how to operate (install, configure, start, stop, etc) a piece of software
- clustertemplates - collection of software, rules, and configuration to define a cluster

## Helpers

### bin/load-templates.sh

This script can be used to upload templates to a Coopr server.

The following variables control the upload.

```bash
COOPR_SERVER_URI=${COOPR_SERVER_URI:-http://localhost:55054}
COOPR_API_USER=${COOPR_API_USER:-admin}
COOPR_API_KEY=${COOPR_API_KEY:-1234567890abcdef}
COOPR_TENANT=${COOPR_TENANT:-superadmin}
TRUST_CERT_PATH=${TRUST_CERT_PATH}
TRUST_CERT_PASSWORD=${TRUST_CERT_PASSWORD}
```

You may modify these on the command line or by exporting them to your environment before running the script.

### bin/jsonlint.sh

This script uses `bin/json.rb` to verify the validity of JSON. It does not currently test the template's validity as a Coopr template.

There is a Rake task setup for running this script. You will need Ruby and the `bundler` gem installed. You can execute it by doing the following:

```
bundle install
bundle exec rake
```

## Contributing to Coopr Templates

Are you interested in making Coopr Templates better? Our development model is a simple
pull-based model with a consensus building phase, similar to the Apache's voting process.
If you want to help make Coopr Templates better, by adding new features, fixing bugs, or
suggesting improvements to something that's already there, here's how you can contribute:

 * Fork caskdata/coopr-templates into your own GitHub repository
 * Create a topic branch with an appropriate name
 * Work on your favorite feature to your content
 * Once you are satisifed, create a pull request by going to the caskdata/coopr-templates project.
 * Address all the review comments
 * Once addressed, the changes will be committed to the caskdata/coopr-templates repository.

Bugs and suggestions should be made by filing a Jira at https://issues.cask.co/browse/COOPR.

## License

   Copyright © 2014-2015 Cask Data, Inc.

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this
software except in compliance with the License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the
License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND,
either express or implied. See the License for the specific language governing permissions
and limitations under the License.
