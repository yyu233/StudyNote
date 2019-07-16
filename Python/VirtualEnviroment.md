## Why Virtual Environment ## 

By default, every project on your system will use these same directories to store and retrieve site packages (third party libraries). At first glance, this may not seem like a big deal, and it isn’t really, for system packages (packages that are part of the standard Python library), but it does matter for site packages.

Consider the following scenario where you have two projects: ProjectA and ProjectB, both of which have a dependency on the same library, ProjectC. The problem becomes apparent when we start requiring different versions of ProjectC. Maybe ProjectA needs v1.0.0, while ProjectB requires the newer v2.0.0, for example.

This is a real problem for Python since it can’t differentiate between versions in the site-packages directory. So both v1.0.0 and v2.0.0 would reside in the same directory with the same name.

Since projects are stored according to just their name, there is no differentiation between versions. Thus, both projects, ProjectA and ProjectB, would be required to use the same version, which is unacceptable in many cases.
