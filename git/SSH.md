Many git servers use ssh for authentication via public keys.

# Do you have a key already?

Check for keys at `~/.ssh` with `ls ~/.ssh`. There should be a pair of files named (similar to) `id_dsa` or `id_rsa`, with a matching `.pub` extension.

# Do you need to create a key?

If they don't exist, you can generate them with `ssh-keygen`, which is provided with the SSH package on Linux/mac and Git for Windows.

# Using the Public Key

Now that you have a key, it needs to be sent to the repo administrator (if that git server requires public keys). All you need to do is copy the contents of the `.pub` file and send it to that person.
