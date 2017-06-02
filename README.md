[![Run Status](https://rcapi.shippable.com/projects/58ae7d8317e88c050022f159/badge?branch=master)](https://rcapp.shippable.com/bitbucket/shiptest-rc-ow/coretest_singlebuildnod)

# coretest_singlebuildNod
A SampleNod project to test basic cases for a single build.


This project is enabled in `shiptest-rc-ow` account in shippable.


## Run CI for this repo on Shippable

Test Cases that are covered in CI build triggering manually:


1. Valid languages and version.
   - Triggers a single build with lang `node_js` having  version `0.10`
2. User specified environment variables in global tag.
   - Envs (eg: TEST=FOO) is specified in env tag.
3. Secure environment variables in global tag.
   - Encrypted from shippable UI and specified in env tag.
4. User specified environment variables in matrix tag.
5. Make sure whether pre_ci envs carrying over to pre_ci_boot section
   - IMAGE_TAG envs specified in pre_ci should be fetched in pre_ci_boot.

6. Include(only) tags for master branch.
7. Exclude(except) tag for non master.
8. Using wildcard in branches tag(only) in integrations.
9. Private submodules are enabled.
    - verify the gitsync step in console to verify the submodules are enabled.

10. Docker build and push(private image)
11. GCR build and push
12. Quay.io build and push
13. ECR build and push
14. Build status(waiting,proccessing,success).
15. Custom build( specify envs from UI(custom: foo)  and verify its taken to the build).
16. Rerun the custom build.It should run with the custom envs from the original build.

Test Cases that are covered on triggering a webhook build:

17. Enable the commit button
18. Project should sync when we trigger a webhook build.
19. Turning off the submodules.
    ```
git:
     submodules: false
``` 
   