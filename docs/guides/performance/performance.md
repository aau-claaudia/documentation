# Computational Performance in Strato

Instances in Strato are virtual machines in an OpenStack environment
which runs on a cluster of various different servers. The
computational performance you experience from an instance in Strato,
e.g. how long it takes to run a given computation, is influenced by
several different factors.

First and foremost, it is important whether the software you run in
your instance can utilise as many CPU cores as the instance
provides. If for example your software can only utilise 4 CPU cores in
total, it will not improve performance to use a flavor with more than
4 VCPUs.

Additional factors that influence computational performance:

- **CPU architecture**
  
  Your software may be optimised to run faster on an Intel CPU than an
  AMD CPU, or vice versa.
  
  The Strato platform consists of servers with Intel CPUs as well as
  with AMD CPUs. Users cannot configure which CPU architecture to use
  and your instance will end up on an arbitrary server depending on
  what is available at the moment when you start your instance.
  
  You can run the command ``lscpu`` in your instance to determine
  which type of CPU(s) your instance is running on.

- **VCPUs are virtual CPUs**
  
  One VCPU in Strato does not necessarily correspond to one physical
  CPU core in a server.
  
  One VCPU may correspond to one "hardware thread" in the CPU and not
  one physical CPU core. Hardware threads are for example the parallel
  instruction pipelines in Intel's HyperThreading technology.

- **VCPUs are over-provisioned**
  
  In addition to the above, VCPUs in Strato may be over-provisioned to
  some degree. This means that the computation time of a VCPU may be
  "time-shared" with other virtual machines in the same server. You
  may thus experience that a VCPU in your Strato instance is
  effectively only doing work for you down to 50% of the time.
  
  This time-sharing is not directly visible to you as a user of an
  instance, but you may be able to measure it by computations being up
  to twice as slow as you would normally expect from the underlying
  physical CPU.

- **Storage in Strato is network storage on rotating hard drives**
  
  The file storage available to Strato instances is provided through a
  network file system (Ceph) using rotating hard drives. Both the
  network and the hard drive technology impacts the file I/O
  performance you experience in Strato.
  
  In practice this means that file I/O in Strato may be several times
  slower than your own laptop computer with fast NVMe solid state
  storage. If your computational work depends highly on file I/O, you
  are likely to experience lower performance in Strato than you would
  on your own laptop, even if the Strato instance has more VCPUs and
  more RAM available.
