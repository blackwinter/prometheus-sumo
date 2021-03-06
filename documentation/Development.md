
# Development

## Checking out the source code

The source code of _pandora_ is hosted in a central
{http://subversion.apache.org Subversion} repository at

    http://prometheus-srv.uni-koeln.de/svn/pandora

### ... using Subversion

Checking out a full working copy from the Subversion repository

    svn co http://prometheus-srv.uni-koeln.de/svn/pandora pandora

will create a directory structure like this:

    pandora
    |
    |-- branches
    |   |-- 0.1-stable
    |   |-- 0.2-stable
    |   |-- 0.3-stable
    |   |-- 0.4-stable
    |   |-- 0.5-stable
    |   |-- 0.6-stable
    |   `-- restructuring_models_search_and_everything
    |-- tags
    |   |-- 0.1.0
    |   |-- 0.1.1
    |   |-- 0.1.2
    |   |-- ...
    |   `-- 0.6.5
    `-- trunk
        |-- app
        |-- config
        |-- db
        |-- doc
        |-- index
        |-- ...

### ... using Git

If at a later point in time you want to be able to create new (release) branches
and tags then accordingly, you will have to clone from the top-level of the 
Subversion repository, telling {http://git-scm.com Git} import from a standard
directory layout: 

    git svn clone -s http://prometheus-srv.uni-koeln.de/svn/pandora pandora

The resulting directory structure will look something like this:

    pandora/.git
    |-- hooks
    |-- info
    |-- logs
    |   `-- refs
    |       |-- heads
    |       `-- remotes
    |           `-- tags
    |-- objects
    |-- refs
    |   |-- heads
    |   |-- remotes
    |   |   `-- tags
    |   `-- tags
    `-- svn
        `-- refs
            `-- remotes
                |-- 0.1-stable
                |-- 0.2-stable
                |-- 0.3-stable
                |-- 0.4-stable
                |-- 0.5-stable
                |-- 0.6-stable
                |-- git-svn
                |-- restructuring_models_search_and_everything
                |-- tags
                |   |-- 0.1.0
                |   |-- 0.1.1
                |   |-- 0.1.2
                |   |...
                |   `-- 0.6.5
                `-- trunk

As of git v1.6.1 the creation of branches in the SVN repository is supported via

    git svn branch

with the additional options

<dl>
  <dt>-m, --message</dt>
    <dd>Allows to specify the commit message.</dd>

  <dt>-t, --tag</dt>
    <dd>Create a tag by using the tags_subdir instead of the branches_subdir specified during git svn init.</dd>
</dl>

The options will be required when {file:Deployment deploying a new version of pandora},
where we a) need to create a sub-directory in ``tags`` and b) attach a standardized
commit message:

    git svn branch -t -m "Tagging the pandora 0.6.5 release" 0.6.5

## Installation of a development system

The installation/configuration of a new development system/environment entails
a number of steps:

- Install required system packages
- Install Ruby gems
- Check out working copy of the source code
- Start up pandora

The sections below explain in further detail what needs do be done at each of the
steps along the way. If you are more interesting in learning about
{file:Testing Testing}, please visit the separate page on that topic.

### Required system packages

If you are using the ``prometheus-sumo`` package_ you can run the following
commands, in order to handle the installation of the required packages

    make InstallPackages

#### ... on Debian GNU/Linux

  * ruby``<REQUIRED_VERSION_RUBY>``
  * ruby``<REQUIRED_VERSION_RUBY>``-dev
  * rubygems
  * rdoc
  * ri
  * irb
  * libmysql-ruby``<REQUIRED_VERSION_RUBY>``
  * libtermios-ruby``<REQUIRED_VERSION_RUBY>``
  * libopenssl-ruby``<REQUIRED_VERSION_RUBY>``
  * librmagick-ruby``<REQUIRED_VERSION_RUBY>``
  * mysql-server
  * mysql-client
  * libmysqlclient-dev
  * apache2
  * libapache2-mod-ruby
  * libapache2-mod-proxy-html
  * subversion
  * libxml2-dev
  * libmagic-dev
  * libmagickwand-dev

#### ... on RedHat

  * ruby
  * rubygems
  * rdoc
  * ri
  * irb
  * eruby
  * libxml2-devel
  * mysql-server
  * mysql-client
  * mysql-devel
  * apache2
  * postfix
  * subversion
  * subversion-tools
  * libapache2-svn
  * ImageMagick
  * ImageMagick-devel

### Start up pandora

#### Initialize the installation

In order to initialize your pandora installation, run the following from the top-level directory of the {file:Rails Rails application}

    rake pandora:setup

For a list of all available rake tasks type

    rake -T

#### Configuration scripts

Provide the required configuration scripts:

    config
    |-- apache2.conf
    |-- database.yml
    `-- secrets.yml

#### Startup

Start up the server

    ./scripts/server

If everything went fine, you should be getting a status message like this

    ** Signals ready.  TERM => stop.  USR2 => restart.  INT => stop (no restart).
    ** Rails signals registered.  HUP => reload (without restart).  It might not work well.
    ** Mongrel 1.1.5 available at 0.0.0.0:3000
    ** Use CTRL-C to stop.

## Virtual machines

