# emporous-fuse-go

Mount an Emporous collection to a directory with FUSE.

Usage:

    ./emporous-fuse-go mount <collection> <mountpoint>
    ./emporous-fuse-go mount localhost:5001/test:latest ./mount-dir/

    # Read Emporous attributes of files:
    getfattr -d ./mount-dir/index.json

Considerations / TODO:

* Use GRPC to fetch file?
* Use file permission attributes?
* Cache data better?
  * Cache will use disk or memory
  * Cache invalidation will be important
* Support fetch with range?
  * Signatures won't be able to be validated unless the full file is cached
    * If the full file is cached, there is no need to fetch with a range
  * Probably requires custom client
* Periodic collection refresh
* Add tests
* Remove dead code
