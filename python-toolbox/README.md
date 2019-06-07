[![Build Status](https://travis-ci.org/marvin-ai/marvin-python-toolbox.svg)](https://travis-ci.org/marvin-ai/marvin-python-toolbox) [![codecov](https://codecov.io/gh/marvin-ai/marvin-python-toolbox/branch/master/graph/badge.svg)](https://codecov.io/gh/marvin-ai/marvin-python-toolbox)

# Marvin Toolbox v0.0.5

![](https://github.com/apache/incubator-marvin-website/blob/master/site/assets/themes/apache/img/logo.png?raw=true)

# Quick Start

## Review

**Marvin** is an open-source Artificial Intelligence platform that focuses on helping data scientists deliver meaningful solutions to complex problems. Supported by a standardized large-scale, language-agnostic architecture, Marvin simplifies the process of exploration and modeling.

## Getting Started
* [Installing Marvin (Ubuntu)](https://marvin.apache.org/marvin-platform-book/ch2_toolbox_installation/ubuntu/)
* [Installing Marvin (MacOS)](https://marvin.apache.org/marvin-platform-book/ch2_toolbox_installation/mac/)
* [Installing Marvin (Other OS) Vagrant](https://marvin.apache.org/marvin-platform-book/ch2_toolbox_installation/vagrant/)
* [Creating a new engine](#creating-a-new-engine)
* [Working in an existing engine](#working-in-an-existing-engine)
* [Command line interface](#command-line-interface)
* [Running an example engine](#running-a-example-engine)


### Creating a new engine
1. To create a new engine
```
workon python-toolbox-env
marvin engine-generate
```
Respond to the prompt and wait for the engine environment preparation to complete. Don't forget to start dev box before if you are using vagrant.

2. Test the new engine
```
workon <new_engine_name>-env
marvin test
```

3. For more information
```
marvin --help
```

### Working in an existing engine

1. Set VirtualEnv and get to the engine's path
```
workon <engine_name>-env
```

2. Test your engine
```
marvin test
```

3. Bring up the notebook and access it from your browser
```
marvin notebook
```

### Command line interface
Usage: marvin [OPTIONS] COMMAND [ARGS]

Options:
```
  --debug       #Enable debug mode.
  --version     #Show the version and exit.
  --help        #Show this command line interface and exit.
```

Commands:
```
  engine-generate     #Generate a new marvin engine project.
  engine-generateenv  #Generate a new marvin engine environment.
  engine-grpcserver   #Marvin gRPC engine action server starts.
  engine-httpserver   #Marvin http api server starts.
  hive-dataimport     #Import data samples from a hive databse to the hive running in this toolbox.
  hive-generateconf   #Generate default configuration file.
  hive-resetremote    #Drop all remote tables from informed engine on host.
  notebook            #Start the Jupyter notebook server.
  pkg-bumpversion     #Bump the package version.
  pkg-createtag       #Create git tag using the package version.
  pkg-showchanges     #Show the package changelog.
  pkg-showinfo        #Show information about the package.
  pkg-showversion     #Show the package version.
  pkg-updatedeps      #Update requirements.txt.
  test                #Run tests.
  test-checkpep8      #Check python code style.
  test-tdd            #Watch for changes to run tests automatically.
  test-tox            #Run tests using a new virtualenv.
```

### Running a example engine 

1. Clone the example engine from the repository
```
git clone https://github.com/marvin-ai/engines.git
```

2. Generate a new Marvin engine environment for the Iris species engine
```
workon python-toolbox-env
marvin engine-generateenv ../engines/iris-species-engine/
```

3. Run the Iris species engine
```
workon iris-species-engine-env
marvin engine-dryrun 
```

> Marvin is a project started at B2W Digital offices and released open source on September 2017.
> The project is donated to Apache Software Foundation on August 2018.
