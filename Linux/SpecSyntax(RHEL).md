
## SPEC ##

To package new software, you need to create a new SPEC file. Instead of writing it manually from scratch, use the rpmdev-newspec utility. It creates an unpopulated SPEC file, and you fill in the necessary directives and fields.

%description

A full description of the software packaged in the RPM. This description can span multiple lines and can be broken into paragraphs.

%prep

Command or series of commands to prepare the software to be built, for example, unpacking the archive in Source0. This directive can contain a shell script.

%build

Command or series of commands for actually building the software into machine code (for compiled languages) or byte code (for some interpreted languages).

%install

Command or series of commands for copying the desired build artifacts from the %builddir (where the build happens) to the %buildroot directory (which contains the directory structure with the files to be packaged). This usually means copying files from ~/rpmbuild/BUILD to ~/rpmbuild/BUILDROOT and creating the necessary directories in ~/rpmbuild/BUILDROOT. This is only run when creating a package, not when the end-user installs the package. See Section 5.1.7, “Working with SPEC files” for details.

%check

Command or series of commands to test the software. This normally includes things such as unit tests.

%files

The list of files that will be installed in the end user’s system.

%changelog

A record of changes that have happened to the package between different Version or Release builds.
  

### Sample Execution Flow ### 
1. Create a tar ball for the source file 
2. Generate build rpm workspace 
3. Put tar ball into source 
4. Unpackage tar ball and put into BUILD 
5. Install rpm into user end system 


### Macro ###
   | macro | definition| 
   |-----------|-------------------------|
  |%trace |             toggle print of debugging information before/after expansion|
  |%dump   |           print the active (i.e. non-covered) macro table|
  |%verbose |           is rpm in verbose mode?|
  |%{echo:...}    |     print ... to stdout|
  |%{warn:...}     |    print ... to stderr|
 | %{error:...}    |    print ... to stderr and raise an error|
  |%define ...       |  define a macro|
  |%undefine ...     |  undefine a macro|
  |%global ...        | define a macro whose body is available in global context|
  |%{load:...}       |  load a macro file (in >= 4.12.0)|
  |%{expand:...}     | like eval, expand ... to <body> and (re-)expand <body>|
  |%{shrink:...}     |  trim leading and trailing whitespace, reduce intermediate whitespace to a single space (in >= 4.14.0)|
  |%{quote:...}      |  quote a parametric macro argument, needed to pass empty strings or strings with whitespace (in >= 4.14.0)|
  |%{lua:...}          |expand with the [embedded Lua interpreter](lua.html)|
  |%{uncompress:...}  | expand ... to <file> and test to see if <file> is compressed. | 
 | %{basename:...}    | basename(1) macro analogue|
  |%{dirname:...}      |dirname(1) macro analogue|
  |%{suffix:...}      | expand to suffix part of a file name|
  |%{url2path:...}     |convert url to a local path|
  |%{getenv:...}       |getenv(3) macro analogue|
  |%{getconfdir:...}   |expand to rpm "home" directory (typically /usr/lib/rpm)|
  |%{S:...}            |expand ... to <source> file name|
  |%{P:...}          |  expand ... to <patch> file name|
  |%{F:...}           | expand ... to <file> file name|


Note that %define and %global differ in more ways than just scope: the body of a %define’d macro is lazily expanded (ie when used), but the body of %global is expanded at definition time. It’s possible to use %%-escaping to force lazy expansion of %global

%setup -a \<source number> : expands sources after entering working directory   
%setup -b \<source number> : expands sources before entering working directory   

To inspect macro values for respective platform: ``` /usr/lib/rpm/platform/*/macros ```  or ``` rpm --eval %{_MACRO} ``` (this only works for macro defined in rpm config file. For specfile, use ``` %{echo: %{your_macro_here}} ```   
 
 
```rpmdev-setuptree ``` set up work space    
```rpmdev-newspec``` create default spec file     
```rpm --showrc``` display rpmrc contents     (root user can run this command)

custom rpm configuration: .rpmmacros 

## BuildRoot ## 
 There are times, however, when even a person with root access will not want RPM to copy new files into the system's directories. As mentioned above, the reasons might be due to the fact that the software being packaged is already in use on the build system. Another reason might be as mundane as not having enough free space available to perform the install into the default directories.

Whatever the reason, RPM provides the ability to direct a given package to install into an alternate root. This alternate root is known as a build root. 

Once the necessary modifications have been made to support a build root, it's necessary for the package builder to keep some issues in mind. The first is that the build root specified in the spec file can be overridden. RPM will set the build root (and therefore, the value of $RPM_BUILD_ROOT) to one of the following values:

The value of buildroot in the spec file.

The value of buildroot in an rpmmacros file.

The value following the --buildroot option on the command line.   

it's not a good idea to define a build root of "/". The %clean section is why: If the build root was set to "/", the %clean section would blow away your root filesystem. 

## Directive for the %files ##
``` %doc ```: RPM keeps track of documentation files in its database, so that a user can easily find information about an installed package. In addition, RPM can create a package-specific documentation directory during installation and copy documentation into it. The default documentation directory is /usr/doc, and can be changed by setting the defaultdocdir rpmrc file entry.       
``` %config ```: RPM performs additional processing for config files when packages are erased, and during installations and upgrades. This is due to the nature of config files: They are often changed by the system administrator, and those changes should not be lost.     
``` %attr ```: The %attr directive permits finer control over three key file attributes:

* The file's permissions, or "mode".

* The file's user ID.

* The file's group ID    
``` %defattr ```: 
* The default permissions, or "mode" for files.

* The default user id.

* The default group id.

* The default permissions, or "mode" for directories.

``` %verify ```: control which of these file attributes are to be checked when an RPM verification is done
for instance, that a package installs device files. Since the owner of a device will change, it doesn't make sense to have RPM verify the device file's owner/group and give out a false alarm, so left out owner and group.     

* Owner (owner)

* Group (group)

* Mode (mode)

* MD5 Checksum (md5)

* Size (size)

* Major Number (maj)

* Minor Number (min)

* Symbolic Link String (symlink)

* Modification Time (mtime)
