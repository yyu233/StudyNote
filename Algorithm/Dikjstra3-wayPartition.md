## Dirkjstra 3-way Partition ##

Let v be the partitioning item a[lo]
Scan i from left to right: 
  * if (a[i] < v) swap a[lt] with a[i], increment lt and i
  * if (a[i] > v) swap a[gt] with a[i], derement gt
  * if (a[i] = v) increment i
  
