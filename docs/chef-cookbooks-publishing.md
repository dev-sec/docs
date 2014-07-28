# Publishing Cookbooks

## Stove-route

The easy way:

        gem install stove
        stove login --username YOURNAME --key ~/.chef/YOURKEY.pem
        cd chef-os-hardening
        stove

## Chef-route

We will use `chef-ssh-hardening` as an example project.

1. Install chef
        
        gem install chef

2. Since development happens locally, define your ssh key in your chef config

        ~/.chef/knife.rb
        
        client_key "#{ENV['HOME']}/.ssh/id_rsa"
        cookbook_license "apachev2"
        cookbook_copyright "<YOURNAME>"
        cookbook_email "<EMAIL>"

3. Copy to temporary cookbooks location

        mkdir /tmp/cookbooks
        cp -r . /tmp/cookbooks/ssh-hardening

4. Generate `metadata.json`

        knife cookbook metadata ssh-hardening -o /tmp/cookbooks

5. Generate tarball

        knife cookbook site share ssh-hardening "ssh-hardening" -o /tmp/cookbooks
