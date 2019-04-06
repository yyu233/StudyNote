
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

 
