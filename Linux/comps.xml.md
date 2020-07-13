comps is used by the installer during software selection. At the installer software selection dialog, the user can choose between a variety of Environments on the left, and Options to those environments on the right.

Each environment consists of a list of groups, and a list of groups that are options for that environment. The list of available options is supplemented by any groups that are marked as 'uservisible' in the comps file.

How comps is used
Installation
comps is used by the installer during package selection. At the Default Packages dialog , the user can choose to Customize Now, displaying the Category Selection dialog.

In the category selection dialog , categories (as defined by the category keyword in comps.xml) are listed down the left-hand side. If a category is selected, any groups in that category with uservisible set are displayed in the right-hand pane. Groups have an icon associated with them. These icons come from the comps-extras package; icons are read from /usr/share/pixmaps/comps/<group-id>.png. If an icon does not exist for a group id, the one for the category that the group is in is used.

Once a group is selected, clicking the Optional Packages button shows the Package Selection dialog.

In any group, there are four levels of packages: optional, default, mandatory, and conditional:

optional are not automatic but can be checked
default are, but can be unchecked in a gui tool
mandatory are always brought in (if group is selected), and not visible in the Package Selection dialog.
conditional are brought in if their requires package is installed
Usually optional is the way, however if you feel that your package deserves a default or required level bring it up for discussion on the development lists. Remember that this has effect on whether or not your package winds up on distribution media such as Live images and spins.

Running System
In dnf, groups are used by dnf groupinstall and dnf groupremove commands, and can be queried with dnf grouplist command.

In PackageKit (Add / Remove Software) the upper left quadrant shows Package collections. When this is clicked, the grouping information is loaded from the configured software repositories, and the complete list of groups, stripped from their categories, are shown in the right hand pane. Selecting a group for installation causes only the default packages within the group to be installed.

Developing comps
git clone ssh://git@pagure.io/fedora-comps.git
When changing the packages, make sure the file is sorted. This helps to make it more maintainable. Use make sort command to fix the sorting.
