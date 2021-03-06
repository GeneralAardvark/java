# Reference
<!-- DO NOT EDIT: This document was generated by Puppet Strings -->

## Table of Contents

**Classes**

* [`java::java_6`](#javajava_6): This class installs Java-6.
* [`java::java_7`](#javajava_7): This class installs Java-7.
* [`java::java_7_jdk`](#javajava_7_jdk): This class installs Oracle Java-7.
* [`java::java_8`](#javajava_8): This class installs Java-8.
* [`java::java_8_jdk`](#javajava_8_jdk): This class installs Oracle Java-8.
* [`java::java_9`](#javajava_9): This class installs Java-9.
* [`java::jce_policy_6`](#javajce_policy_6): 
* [`java::jdkfolder`](#javajdkfolder): Creates /opt/jdk folder used to contain Oracle jdk installation.

**Defined types**

* [`java`](#java): This module manages Java.  Declares all other defines in the java module needed for installing Java. Currently, these consists of java::insta
* [`java::install_config`](#javainstall_config): Configures Java. It is intended to be called by java::java.  == Actions:  Sets up the default java according to the parameter <tt>java_defaul

## Classes

### java::java_6

This class installs Java-6.

#### Examples

##### Declaring in manifest

```puppet
include java::java_6
```

##### Hiera data for using java_6

```puppet
classes:
  - java::java_6
```

### java::java_7

This class installs Java-7.

#### Examples

##### Declaring in manifest

```puppet
include java::java_7
```

##### Hiera data for using java_7

```puppet
classes:
  - java::java_7
```

### java::java_7_jdk

This class installs Oracle Java-7.

#### Examples

##### Declaring in manifest

```puppet
include java::java_7_jdk
```

##### Hiera data for using java_7_jdk

```puppet
classes:
  - java::java_7_jdk
```

### java::java_8

This class installs Java-8.

#### Examples

##### Declaring in manifest

```puppet
include java::java_8
```

##### Hiera data for using java_8

```puppet
classes:
  - java::java_8
```

### java::java_8_jdk

This class installs Oracle Java-8.

#### Examples

##### Declaring in manifest

```puppet
include java::java_8_jdk
```

##### Hiera data for using java_8_jdk

```puppet
classes:
  - java::java_8_jdk
```

### java::java_9

This class installs Java-9.

#### Examples

##### Declaring in manifest

```puppet
include java::java_9
```

##### Hiera data for using java_9

```puppet
classes:
  - java::java_9
```

### java::jce_policy_6

The java::jce_policy_6 class.

### java::jdkfolder

Creates /opt/jdk folder used to contain Oracle jdk installation.

## Defined types

### java

This module manages Java.

Declares all other defines in the java module needed for installing Java.
Currently, these consists of java::install, and java::config.
If hiera defines a value for the parameter <tt>java_default_version</tt> on
the target node the command <tt>update-alternatives</tt> is issued to set the
default java accordingly.

#### Examples

##### Declaring in manifest

```puppet
java {'8': }
```

#### Parameters

The following parameters are available in the `java` defined type.

##### `java_version`

Data type: `String`

the java version.
Possible values at this time are
<tt>6</tt>, <tt>7</tt>, <tt>8</tt> and <tt>9</tt>.

Default value: $title

##### `openjdk`

Data type: `Boolean`

use openjdk. Defaults to <tt>true</tt>.
<tt>true</tt> means to install openjdk from distribution packages
<tt>false</tt> means to untar the Oracle archive.

Default value: `true`

##### `java_default_version`

Data type: `Optional[String]`

the java default version.
Possible values at this time are
<tt>6</tt>, <tt>7</tt>, <tt>8</tt> and <tt>9</tt>.
Oracle jdk-6, howewer, is not supported while Oracle jdk-7 and Oracle jdk-8 at the moment are 64 bit versions.
If different than +undef+ it will be used to configure
the alternative system.

Default value: lookup('java::java_default_version', Optional[String], 'first', undef)

### java::install_config

Configures Java.
It is intended to be called by java::java.

== Actions:

Sets up the default java according to the parameter
<tt>java_default_version</tt> if it is not null.

#### Parameters

The following parameters are available in the `java::install_config` defined type.

##### `java_version`

Data type: `String`

the java version.
Possible values at this time are
<tt>6</tt> and <tt>7</tt>.

Default value: $title

##### `openjdk`

Data type: `Boolean`

use openjdk.
<tt>true</tt> means to install openjdk from distribution packages
<tt>false</tt> means to untar the Oracle archive.

##### `java_default_version`

Data type: `Optional[String]`

the java default version.
Possible values at this time are
<tt>6</tt>, <tt>7>/tt> and <tt>8</tt>.
Oracle jdk-6, howewer, is not supported while Oracle jdk-7 and Oracle jdk-8 at the moment are 64 bit versions.
If different than +undef+ it will be used to configure
the alternative system.

