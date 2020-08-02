```
This is not like Collections.sort() where the parameter reference gets sorted. In this case you just get a sorted stream that you need to collect and assign to another variable eventually:

List result = list.stream().sorted((o1, o2)->o1.getItem().getValue().
                                   compareTo(o2.getItem().getValue())).
                                   collect(Collectors.toList());

```
