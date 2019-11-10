The important members of the struct kobject are given below.
* char *name: This is the name of the kobject. Folders corresponding to the current kobject are created with this name in sysfs.
* Struct kobject *parent: This is the parent of the current kobject being created. When a folder is created in sysfs, if this field is present, then the current kobject folder is created inside the parent kobject folder.
* Struct kref: This is the reference counting mechanism for kobject. Whenever any kernel module refers to any kobject, its reference count is incremented, and whenever any kobject reference is released by any kernel module, then the reference count is decremented. When the reference count decrements to zero, memory related to the kobject is released.
