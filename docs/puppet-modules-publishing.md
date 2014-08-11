Simple enough: If you have your `Modulefile` and `metadata.json` ready, just run:

    cd puppet-xxx-hardening/
    puppet module build .

Results are in pkg.

The two files may not get merged correctly, so please diff:

    colordiff metadata.json pkg/puppet-*-hardening/metadata.json
