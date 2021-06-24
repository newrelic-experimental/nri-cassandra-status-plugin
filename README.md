[![New Relic Experimental header](https://github.com/newrelic/opensource-website/raw/master/src/images/categories/Experimental.png)](https://opensource.newrelic.com/oss-category/#new-relic-experimental)

# Cassandra Nodetool Integration [build badges go here when available]

This New Relic Infrastructure integration invokes the cassandra nodetool utility to gather cassandra node status metrics.

## Installation

* Download an archive file for the Cassandra-Status Integration
* Place the executables under `bin` directory and the definition file `cassandra-status-definition.yml` in `/var/db/newrelic-infra/newrelic-integrations`
* Set execution permissions for the binary file `nr-cassandra-status`
* Place the integration configuration file `cassandra-status-config.yml.sample` in `/etc/newrelic-infra/integrations.d`

## Getting Started

In order to use the Cassandra-Status Integration it is required to configure `cassandra-status-config.yml.sample` file. Firstly, rename the file to `cassandra-status-config.yml`. Then, depending on your needs, specify all instances that you want to monitor. Once this is done, restart the Infrastructure agent.

## Usage

You can view your data in Insights by creating your own custom NRQL queries. To
do so use **CassandraStatusSample** event types.

The following attributes are reported always
* Status: 
     0 (not reported) if there is an error executing `nodetool info` or `nodetool status` commands
     1 if the commands execute succesfully and return a status of "Down"
     2 if the commands execute successfully and return a status of "Up"

* State :
     0 (not reported) if there is an error executing `nodetool info` or `nodetool status` commands
     1 if the commands execute successfully and return a state of `N`
     2 if the commands execute successfully and return a state of `L`
     3 if the commands execute successfully and return a state of `J`
     4 if the commands execute successfully and return a state of `M`

If the command execute succesfully, then the following attributes are also parsed, They will not be reported however if the commands fails for any reason,

* address
* load
* tokens
* hostid
* owns
* rack


## Support

New Relic has open-sourced this project. This project is provided AS-IS WITHOUT WARRANTY OR DEDICATED SUPPORT. Issues and contributions should be reported to the project here on GitHub.

>[Choose 1 of the 2 options below for Support details, and remove the other one.]

>[Option 1 - no specific thread in Community]
>We encourage you to bring your experiences and questions to the [Explorers Hub](https://discuss.newrelic.com) where our community members collaborate on solutions and new ideas.

>[Option 2 - thread in Community]
>New Relic hosts and moderates an online forum where customers can interact with New Relic employees as well as other customers to get help and share best practices. Like all official New Relic open source projects, there's a related Community topic in the New Relic Explorers Hub.
>You can find this project's topic/threads here: [URL for Community thread]

## Contributing

We encourage your contributions to improve Cassandra Nodetool Integration! Keep in mind when you submit your pull request, you'll need to sign the CLA via the click-through using CLA-Assistant. You only have to sign the CLA one time per project. If you have any questions, or to execute our corporate CLA, required if your contribution is on behalf of a company, please drop us an email at opensource@newrelic.com.

**A note about vulnerabilities**

As noted in our [security policy](../../security/policy), New Relic is committed to the privacy and security of our customers and their data. We believe that providing coordinated disclosure by security researchers and engaging with the security community are important means to achieve our security goals.

If you believe you have found a security vulnerability in this project or any of New Relic's products or websites, we welcome and greatly appreciate you reporting it to New Relic through [HackerOne](https://hackerone.com/newrelic).

## License

Cassandra Nodetool Integration is licensed under the [Apache 2.0](http://apache.org/licenses/LICENSE-2.0.txt) License.

>[If applicable: Cassandra Nodetool Integration also uses source code from third-party libraries. You can find full details on which libraries are used and the terms under which they are licensed in the third-party notices document.]
