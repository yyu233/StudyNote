Debugging roles/playbooks

Basically debugging ansible automation over big inventory across large networks is none the other than debugging a distributed network application. It can be very tedious and delicate, and there are not enough user friendly tools.

Thus I believe the also answer to your question is a union of all the answers before mine + small addition. So here:

absolutely mandatory: you have to want to know what's going on, i.e. what you're automating, what you are expecting to happen. e.g. ansible failing to detect service with systemd unit as running or as stopped usually means a bug in service unit file or service module, so you need to 1. identify the bug, 2. Report the bug to vendor/community, 3. Provide your workaround with TODO and link to bug. 4. When bug is fixed - delete your workaround

to make your code easier to debug use modules, as much as you can

give all tasks and variables meaningful names.

use static code analysis tools like ansible-lint. This saves you from really stupid small mistakes.

utilize verbosity flags and log path

use debug module wisely

"Know thy facts" - sometimes it is useful to dump target machine facts into file and pull it to ansible master

use strategy: debugin some cases you can fall into a task debugger at error. You then can eval all the params the task is using, and decide what to do next

the last resort would be using Python debugger, attaching it to local ansible run and/or to remote Python executing the modules. This is usually tricky: you need to allow additional port on machine to be open, and if the code opening the port is the one causing the problem?

Also, sometimes it is useful to "look aside" - connect to your target hosts and increase their debuggability (more verbose logging)

Of course log collection makes it easier to track changes happening as a result of ansible operations.

As you can see, like any other distributed applications and frameworks - debug-ability is still not as we'd wish for.

Filters/plugins

This is basically Python development, debug as any Python app

Modules

Depending on technology, and complicated by the fact you need to see both what happens locally and remotely, you better choose language easy enough to debug remotely.
