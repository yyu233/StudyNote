1. ``` sleep() ``` does not release lock. Can only be interrupted not waken up.
2. ``` wait() ``` releases lock. Can be waken up by ``` notify() ```  or ``` notifyAll```

