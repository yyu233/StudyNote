Split up database by function and results in less read and write traffic database and therefore less replication lag. Write in parallel to increase throughput. Smaller database improves cache locality and results in more cache hit.    