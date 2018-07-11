
# Question

Creating customized distribution-specific packages is a requirement for any engineer. Software that is only available as source code should be packaged using the distribution's package building system and installed and managed just as upstream packages would be.

You should use the `pkgbuild` user, present on the system, for this task. The user's home directory has been populated with an appropriate build directory structure. Please complete the following:

- A basic source tarball is available at `/opt/CESD00301/cesd00301-0.0.1.tar.xz` . You should use the distribution's package building system to create an appropriate signed package to install this software.
- The signed package should be copied to the `/opt/CESD00301/outfiles` directory when created, which is already present on the system (some files which may assist you in this process are also located in the `/opt/CESD00301` directory).
- The package version should be `0.0.1` , and the release/revision should be `1` .
- The GPG key required to sign this package is present in the standard GPG home directory location for the `pkgbuild` user. The passphrase for this key is `Passw0rd123` . The key ID is also noted in `/opt/CESD00301/keyid` for your convenience.

# Question Weight

5%

# did it??

Couldn't do it...

