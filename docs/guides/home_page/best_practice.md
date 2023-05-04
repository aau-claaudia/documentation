## Best practices on Strato

There are a multitude of ways to work with virtual machines on Strato, but there is one general process that we require users to follow.

1. All setup should take place on a small flavor.
2. Delete the small instance, rename and and retain the volume.
    - All images create initial volume sizes of 50Gb. 
    - If you need more than 50 Gb of storage for your instance, navigate to the `volumes` pane and extend the volume used in step 1.
3. Launch a new instance from the volume, choosing the flavour of machine necessary for the work you are doing on the instance.
4. When you are finished working on the instance, delete it.
5. When returning to Strato, repeat steps 3 and 4.

