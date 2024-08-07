VAULT
=====

Save backups of the files downloaded by your scripts for the time the
link breaks.

## How to use

When writting a script put the download section as follows:

    ${VAULT} wget -O file.tar.gz.tmp http://example.com/file.tar.gz
    mv -v file.tar.gz.tmp file.tar.gz

Then in your environment set the `VAULT` variable to the path of the
`vault` script.

    export VAULT=/path/to/vault

The files are stored in "$VAULT_SSH_MACHINE:$VAULT_DIRECTORY", with the
.tmp suffix stripped. If one day the link breaks, you can recover the
file from the vault.

Is important to put $VAULT and not vault in the script so that this
feature can be disabled and it is not a hard dependency. Also this
allows other implementations to exist.

## Configuration

You need to set the `VAULT_DIRECTORY` and `VAULT_SSH_MACHINE` environment
variables. Optionally you can set `VAULT_SSH_PORT` to the port of the
ssh server.

    export VAULT_DIRECTORY=/path/to/vault
    export VAULT_SSH_MACHINE=user@machine
    export VAULT_SSH_PORT=22

## Help

vault

    Usage: vault {-V | wget|curl ... }
    
    A downloading wrapper to be used with curl(1) or wget(1) that
    stores the downloaded files in a vault for the time the link
    breaks.
    
    Env.variables: VAULT_DIRECTORY, VAULT_SSH_MACHINE, VAULT_SSH_PORT.

## Collaborating

For making bug reports, feature requests and donations visit
one of the following links:

1. [gemini://harkadev.com/oss/](gemini://harkadev.com/oss/)
2. [https://harkadev.com/oss/](https://harkadev.com/oss/)
