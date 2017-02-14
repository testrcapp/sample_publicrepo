# sampleNod
A SampleNod project to test basic cases for a single build.

This project is enabled in `shiptest-rc-ow` account in shippable.

## Run CI for this repo on Shippable

Test Cases that are covered in CI build triggering manually:


1. Valid languages and version.
2. Valid addons
3. User specified environment variables in global tag.
   - Envs (eg: TEST=FOO) is specified in env tag.
4. Secure environment variables in global tag.
   - Encrypted from shippable UI and specified in env tag.
5. User specified environment variables in matrix tag.
6. Make sure whether pre_ci envs carrying over to pre_ci_boot section
   - IMAGE_TAG envs specified in pre_ci should be fetched in pre_ci_boot.

7. Include(only) tags for master branch.
8. Exclude(except) tag for non master.
9. Using wildcard in branches tag(only) in integrations.
10. Private submodules are enabled.
    - verify the gitsync step in console to verify the submodules are enabled.

11. Docker build and push(private image)
12. GCR build and push
13. Quay.io build and push
13. ECR build and push
14. Build status(waiting,proccessing,success).
15. Verify the status badge in UI

  - projectsettings-> Badges

Test Cases that are covered on triggering a webhook build:

16. Enable the commit button
17. Project should sync when we trigger a webhook build.
18. Turning off the submodules.
    ```
git:
     submodules: false
``` 
     
19. Verify the failed Build status(make the build fail by invalid comments in yml).
20. Custom build( specify envs from UI(custom: foo)  and verify its taken to the build).
21. Rerun the custom build.It should run with the custom envs from the original build.
22. Cancel the build and verify Cancel status.
23. Verify the build consoles are loading propely with all steps.
24. Click on reset button,to verify resetting the project.

  - Make sure webhooks and deployement key associated with project has been resetted.
25. Click delete button.

  - Should clear all history build associated with the project.

26. Enable the project again after deleting project.

   - Should be able to enable the project as new one.

