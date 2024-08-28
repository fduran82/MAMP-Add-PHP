# Using a MacBook Pro M1
## homebrew php  
### example: trying to use PHP 8.0.30

- ### Step 1: Locate Homebrew PHP 8.0.30 Path
    1. Run the following command in your terminal to find the path of PHP 8.0.30 installed by Homebrew:
    ```
        brew --prefix php@8.0
    
    ```
    2. This will output the path, typically something like `/opt/homebrew/opt/php@8.0`
       
- ### Step 2: Update MAMP's PHP Configuration
    1. Go to  
      ```
          Applications/MAMP/bin/php/
      ```
    2. Create a new folder named php8.0.30
    3. Inside this folder, create symbolic links to the necessary binaries from your Homebrew installation:
      ```
          ln -s /opt/homebrew/opt/php@8.0/bin/php php
      ```
      ```
           ln -s /opt/homebrew/opt/php@8.0/sbin/php-fpm php-fpm
      ```
      ```
          ln -s /opt/homebrew/opt/php@8.0/lib/httpd/modules modules
      ```
      Make sure to replace the paths with the actual output from the brew --prefix php@8.0 command if it's different.

- ### Step 3: Update MAMP's PHP Preferences
    1. Open MAMP
    2. Go to MAMP Preferences > PHP
    3. Select 8.0.30 from the dropdown. If it doesn't appear, you may need to restart MAMP or manually edit MAMP's configuration files to include this version.

- ### Step 4: Verify and Restart
    1. Restart MAMP
    2. Check the PHP version by creating a phpinfo() file in your MAMP htdocs folder and accessing it via your browser.
           ```
           <?php
              /* Use the following code to show all the information about PHP. */
              phpinfo();
            ?>
           ```
