Putting multiple jobs in the background is a good way of using the multiple cores of a single machine. parallel however, allows you to spread jobs across multiple servers of your network. From man parallel:

GNU parallel is a shell tool for executing jobs in parallel using one or more computers. The typical input is a list of files, a list of hosts, a list of users, a list of URLs, or a list of tables.

Even when running on a single computer, parallel gives you far greater control over how your jobs are parallelized. Take this example from the manpage:

   To convert *.wav to *.mp3 using LAME running one process per CPU core
   run:

   parallel lame {} -o {.}.mp3 ::: *.wav
OK, you could do the same with

   for i in *wav; do lame "$i" -o "${i%.wav}.mp3" & done
However, that is longer and more cumbersome and, more importantly, will launch as many jobs as there are .wav files. If you run this on a few thousand files, it is likely to bring a normal laptop to its knees. parallel on the other hand, will launch one job per CPU core and keep everything nice and tidy.

Basically, parallel offers you the ability to fine tune how your jobs are run and how much of available resources they should use. If you really want to see the power of this tool, go through its manual or, at the very least, the examples it offers.

Simple backgrounding really has nowhere near the level of sophistication to be compared to parallel. As for how parallel differs from xargs, the GNU crowd give a nice breakdown here. Some of the more salient points are:

xargs deals badly with special characters (such as space, ' and ").
xargs can run a given number of jobs in parallel, but has no support for running number-of-cpu-cores jobs in parallel.
xargs has no support for grouping the output, therefore output may run together, e.g. the first half of a line is from one process and the last half of the line is from another process.
xargs has no support for keeping the order of the output, therefore if running jobs in parallel using xargs the output of the second job cannot be postponed till the first job is done.
xargs has no support for running jobs on remote computers.
xargs has no support for context replace, so you will have to create the arguments.
