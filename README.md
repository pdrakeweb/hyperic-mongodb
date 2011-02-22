## Hyperic HQ MongoDB plugin

This project is a Hyperic HQ plugin for monitoring [MongoDB](http://www.mongodb.org/)

Source code is available at [github.com/ClarityServices/hyperic-mongodb](https://github.com/ClarityServices/hyperic-mongodb)

### Platform Support

Only supports MongoDB running on Unix, Linux and Mac since it uses a bash shell to invoke the mongo shell.

Also made it work on Windows? Please fork and submit a pull request. (Or just email me the plugin-xml and I will post the updated file)

### Auto-Discovery

The MongoDB server process (mongod) is auto-discovered. 

### Metrics

All metrics available via the db.serverStatus() command have been made available.

Additionally, all server process (mongod) metrics are also available.

For the complete list of Metrics available, please see the [HyperForge MongoDB documentation](http://support.hyperic.com/display/hypcomm/MongoDB)

### Log File Tracking

Messages are optionally reported from mongodb.log and can be filtered by 
regex include/exclude.

### Config File Tracking

The mongodb config file can be monitored for changes.

### Control Actions

None yet. Submit any ideas as issues on github

### Dependencies

Mongo shell (mongo) and Bash Shell (bash)

### Mongodb Version Support

Tested on Red Hat Enterprise Linux 5 with Mongodb 1.6.5

### Hyperic HQ Version Support

Tested with [Hyperic HQ](http://www.hyperic.com/) version 4.4

### Install

#### Server Installation

* Copy the file _hyperic-mongodb.xml_ into the following folder under the server installation:
    hq-engine/server/default/deploy/hq.ear/hq-plugins
* Output similar to the following should appear in the server logfile (logs/server.log)
<pre>
2011-02-21 13:53:53,972 INFO  [ScannerThread] [org.hyperic.hq.product.server.mbean.ProductPluginDeployer@654] HQ plugin mongodb-plugin.xml undeployed
2011-02-21 13:53:53,995 INFO  [ScannerThread] [org.hyperic.hq.product.server.mbean.ProductPluginDeployer@654] HQ plugin mongodb registered
2011-02-21 13:53:54,001 INFO  [ScannerThread] [org.hyperic.hq.product.server.session.ProductManagerEJBImpl@320] mongodb unknown -- registering
2011-02-21 13:53:54,217 INFO  [ScannerThread] [org.hyperic.hq.product.server.mbean.ProductPluginDeployer@654] HQ plugin mongodb deployed
</pre>
* If the out above does not appear in the log file ensure that the file is in the directory
along with several other files ending with _-plugin.xml_ and _-plugin.jar_
* It is not necessary to restart the server, it automatically picks up new plugins. 

#### Client Installation

* Copy the file _hyperic-mongodb.xml_ into the plugins folder under the client installation. The path should be similar to:
    agent/bundles/agent-4.4.0-1509/pdk/plugins/
* Restart the agent to pull in the new plugin file

### Developers

To generate updated documentation for the HyperForge Wiki, run the following command:

    java -jar bundles/agent-4.4.0-1509/pdk/lib/hq-product.jar -Dplugins.exclude=vsphere -m generate -a metrics-wiki

Then update the page on [HyperForge](http://support.hyperic.com/display/hypcomm/MongoDB)

### Meta

* Code: `git clone git://github.com/ClarityServices/hyperic-mongodb.git`
* Home: <https://github.com/ClarityServices/hyperic-mongodb>
* Bugs: <https://github.com/ClarityServices/hyperic-mongodb/issues>

### Author

Reid Morrison :: rubywmq@gmail.com :: @reidmorrison

### License

Copyright 2011 Clarity Services, Inc.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
