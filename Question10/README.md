
# Intro

*Important:* For this item, you should ssh to the node `exam-4` and complete all tasks on this node. Ensure that you return to the base node (hostname: `node-1` ) when you have completed this item.

# Question

Ensuring users have the access and configuration they need to do their jobs is an important responsibility for an Engineer. On the development server `exam-4` , Java developers require their `JAVA_HOME` environment variable set to `/usr/local/java1.8` in their environment when connecting via `ssh` . Please complete this task by:

Implementing this with `PAM` on the `exam-4` server using a configuration file for the appropriate `PAM` module located at `/etc/pam_vars.conf`
Using the same mechanism, set the `WHOAMI` environment variable to be the name of the user logging in via `ssh` , followed by an `@` symbol, followed by the hostname of the remote `host/IP` address from which you are connecting, example: `remoteuser@remotehost` or `remoteuser@10.1.2.3` (depending on hostname resolution configuration).
If this information is not available, a default value of `nobody@localhost` should be used for the value of `WHOAMI` .
A test user has been set up on `exam-4` for your convenience, with the following credentials:

Username: `testuser`
Password: `Passw0rd123`
Return to the base node upon completion.

# Question Weight

4%

# did it??

Couldn't do it...

