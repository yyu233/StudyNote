```
Package order for installing a single package for the first time:

%pretrans of new package
%pre of new package
package install
%post of new package
%posttrans of new package
Package order for removing a single package:

%preun of old package
removal of old package
%postun of old package
```
