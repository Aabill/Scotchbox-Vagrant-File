# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

    # /*=====================================
    # =            FREE VERSION!            =
    # =====================================*/
    # This is the free (still awesome) version of Scotch Box.
    # Please go Pro to support the project and get more features.
    # Check out https://box.scotch.io to learn more. Thanks

    config.vm.box = "scotch/box"
    config.vm.network "private_network", ip: "192.168.33.10"
    config.vm.hostname = "scotchbox"
    #config.vm.synced_folder ".", "/var/www", :mount_options => ["dmode=777", "fmode=666"]

    config.hostsupdater.aliases = [
        "aaron.local",
        "suzettelyn.local",
        "wordpress.local",
        "media.local",
    ]

    config.vm.provision "file", 
    source: "provisioning/vhost/aaron-local.conf", 
    destination: "/tmp/aaron.local"

    config.vm.provision "shell",
    inline: "mv /tmp/aaron.local /etc/apache2/sites-enabled/aaron-local.conf"

    config.vm.provision "file", 
    source: "provisioning/vhost/suzettelyn-local.conf", 
    destination: "/tmp/suzettelyn.local"

    config.vm.provision "shell",
    inline: "mv /tmp/suzettelyn.local /etc/apache2/sites-enabled/suzettelyn-local.conf"

    config.vm.provision "file", 
    source: "provisioning/vhost/wordpress-local.conf", 
    destination: "/tmp/wordpress.local"

    config.vm.provision "shell",
    inline: "mv /tmp/wordpress.local /etc/apache2/sites-enabled/wordpress-local.conf"

    config.vm.provision "file", 
    source: "provisioning/vhost/media-local.conf", 
    destination: "/tmp/media.local"

    config.vm.provision "shell",
    inline: "mv /tmp/media.local /etc/apache2/sites-enabled/media-local.conf"

    config.vm.synced_folder "./public/",  "/var/www/public/", id: "public" , :nfs => { :mount_options => ["dmode=777","fmode=666"] }
    config.vm.synced_folder "./projects/",  "/var/www/", id: "assortment" , :nfs => { :mount_options => ["dmode=777","fmode=666"] }
end
