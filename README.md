node-red-contrib-zeromq
=======================

<a href="http://nodered.org" target="new">Node-RED</a> nodes that provide
a pair of publish subscribe nodes for ZeroMQ.

Provides a peer-to-peer publish subscribe capability, not unlike MQTT, but without a broker, and without many of the same semantics. Works nicely using *localhost* to provide local process separation.

Relies on the <a href="https://www.npmjs.com/package/zeromq" target="new">zeromq</a> npm package to provide pre-build binaries to make installing easier... but can take some time to compile if not available.

### Install

Run the following command in your Node-RED user directory - typically `~/.node-red`

    npm install node-red-contrib-zeromq



#### Input

The **server** should be specified as a ZeroMQ connection string.
This is typically of the form `tcp://ip.address.of.server:port`

The **topic** of interest can be specified by a string. The topic matching is purely
on first matching characters - i.e. the topic starts with...

**Note**: this is NOT the same as MQTT - please read up on how ZeroMQ handles topics before raising an issue.

ZeroMQ messages can have multiple parts or **fields** - typically two - by default topic and payload,
but you can name more if required depending upon the application you are trying to integrate,
by using the comma separated field property.

#### Output

The **server** should be specified as a ZeroMQ connection string.
This is typically of the form `tcp://*:port`

By default the node expects to publish two fields - `msg.topic` and `msg.payload`.
However ZeroMQ can support multipart messages and the `msg` properties
to send can be specified by the comma separated **fields** configuration.

The **topic** can be fixed in the configuration if required.
