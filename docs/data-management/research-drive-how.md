# Welcome to MkDocs

For full documentation visit [mkdocs.org](https://www.mkdocs.org).

## Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.



### TROEP

  

Securing data

- Client-side encryption with Cryptomator (secure vault with password encrypted and saved keys) – currently supported
- Secure vault with password encrypted and saved keys
- Downside: when sharing data you need to provide the password to the person with whom you are sharing

 

Mounting Research Drive

- Research Drive can be mounted in any OS using tools that support WebDAV. In Windows, Linux or MacOS mount it as network or remote storage
- On LISA or Cartesius, use a tool like RClone
- Required: WebDAV password generated in RD web interface
- Config: rclone config

storage type: webdav, provide the remote WebDAV URL of your instance, choose “owncloud” as vendor, name it “RD” or more specific

- List files: rclone ls RD
- Copy files: rclone copy RD:/file.txt file.txt