
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
