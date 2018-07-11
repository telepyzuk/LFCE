
# Intro

*Important:* For this item, you may need to ssh to the nodes `auth-client` , `krb5-server` and `ldap-server` in order to complete tasks. Ensure that you return to the base node (hostname: `node-1` ) when you have completed this item.

# Question

As an Engineer, managing authentication is an important part of your job. In this task, you will connect the system `auth-client` to your company's authentication server, which uses `LDAP` and `Kerberos` . A test user has been configured, `testuser@AUTH.EXAMPLE.COM` . This user can currently ssh into both `krb5-server` and `ldap-server` . Once a `Kerberos` ticket has been obtained, this user can ssh freely between these two nodes without re-entering a password. You are required to:

- Configure `auth-client` to participate in the Kerberized single sign-on in an identical way.
- Ensure that new users have their home directories automatically created on first login (do not use autofs for this).
- Feel free to add new user(s) to `LDAP` and create the appropriate `Kerberos` principal(s) to test your work.
- The `LDAP` server is available on node `ldap-server` , the `Kerberos` server is available on node `krb5-server` and the configured `Kerberos` realm is `AUTH.EXAMPLE.COM` . ALL passwords for the various principals is set to `Passw0rd123` . To administer the `LDAP` server, if required, perform the following step on `ldap-server` to authenticate:

```
kinit ldapadm
```

To administer `Kerberos` via `kadmin` , use the `krbadm` principal, as follows:

```
kadmin -p krbadm
```

Return to the base node upon completion.

# Question Weight

5%

# did it??

Couldn't do it...

