# Add node-red module for Yocto2.7 on WISE710A1

### official nodejs for all arch

#### [v12.13.0 release](https://nodejs.org/en/blog/release/v12.13.0/)

### Use NPM URL

#### node-red-contrib-modbus

```bash
$ devtool add "npm://registry.npmjs.org;name=node-red-contrib-modbus;version=5.13.3;"
```

In ${builddir}/workspace/recipes/node-red-contrib-modbus:

#### node-red-contrib-modbus\_5.13.3.bb

```bash
...
NPMPN= "node-red-contrib-modbus"
...
```

copy node-red-contrib-modbus to your meta layer folder, and then reset it.

```bash
$ devtool reset node-red-contrib-modbus
$ rm -rf ${builddir}/workspace/sources/node-red-contrib-modbus
```

check versions

```bash
$ bitbake -s | vim -
...
node-red                                            :1.1.2-r0
node-red-contrib-modbus                            :5.13.3-r0
...
```

build recipe

```bash
$ bitbake node-red-contrib-modbus
```

