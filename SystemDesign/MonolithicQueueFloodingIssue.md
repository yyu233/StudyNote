In the monolithic architecture, as all the events were moved into a single queue, some of the events often failed to deliver to the destinations and were retired by the queue after stipulated time intervals.

This made the queue contain both the new as well as the failed events waiting to be retried. This eventually flooded the queue resulting in a delay of the delivery of events to the destinations.
