What is an objection mechanism in UVM?      

Objection mechanism is a UVM strategy used to decide the end of test. There are number of zero time consuming phases before and after the run_phase. The run_phase is the only time consuming phase which is run in parallel for all the components. With that being said, run_phases  of different components complete at different time and there comes a need to track the end of run phases of different components to finally end the test. This need of tracking the end of run_phases of different components. And this is done using the uvm_objections.      

A point here to note is that, objections can be raised by components as well as objects. For example a sequence before starting can raise an objection and drop the objection after completion. Objection raising/dropping is not only limited to the run phase of components.
