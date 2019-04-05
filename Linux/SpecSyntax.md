## Spec File Syntax ## 

2 main parts: package information tags, build sections.   

### Package Information Tags ###

```
Name
Version
Release
Vendor
URL
Copyright
Distribution
Packager
Group
Icon
Summary

%description 
# longer description section starts here

```

### Build Settings ###

```
BuildPreReq: # any prerequisites for building
Buildroot: # temporary directory in which to build the package
```

### Dependency Tags ###

```
Provides: # capability_name
Requires: capability_name >= version_number

```

### Sources Files ###
```
Source0: 
Source1:
Patch0:
Patch1:
```

### Macros 

|Macro|Usage|
|-----|-----|
|%define| define new macro|
|%dump|prints out macro values|
|%{echo:message}|prints message to stderr|
|%{error:message}|prints message to stderr and returns BADSPEC|

