# ddo

Drupal DevOps

Please note: this repository is my working dumping ground during the implementation of Drupal development operations in Bash script form. There will be an announcement on Reddit's /r/drupal as well as possibly a few other Drupal related forums when this script is useful.

Just some notes about what to expect if you have found this early:

  - Maintain a list of servers and their roles in configuration files. Does environment detection. Check if PHP and web server is set up for Drupal. Tests if the recommended PECL extensions are enabled. Checks if Drush is available remotely. Attempts to auto resolve any problems in an OS specific manner. Automated key exchange and setup for administration users with permissions to create new sites.
  
  - Create sites by answering questions at command prompt or using a declarative template
  
  - Auto-generate and maintain up to 4 different variations of a site:

      * Local machine development or VM development with shared directories.
      * Development site that is automatically updated on a successful `git push`.
      * Test site. Normally code is pushed from development and database and files from live site.
      * Production website.

    The development and test sites will be assumed to be on a public server by default and will create a site protecting .htaccess for them.

  - Commands for synchronizing code, database, and files between sites or automating the synchronization based on version control events.

  - Configuration sharing - keep your configuration in version control and share it to make it simple to add team members (new members install ddo script into $PATH then run a configuration clone command [TBD]).
  
  - Requires no server installation. The script copies itself during the SSH command and then executes a remote command. The script is not written to the server filesystem.

  - First revs will work best with Cygwin as the developer frontend, a VirtualBox running Ubuntu for local dev, and Ubuntu servers. More platforms will be supported in future, every OS specific command is isolated.

*NOTE* This is a pie-in-the-sky wishlist of features. It is certainly subject to change.
