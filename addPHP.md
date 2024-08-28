# Using a MacBook Pro M1
## homebrew php  
### example: trying to use PHP 8.0.30

- ### Step 1: Locate Homebrew PHP 8.0.30 Path
    - Run the following command in your terminal to find the path of PHP 8.0.30 installed by Homebrew:
    ```
    brew --prefix php@8.0
    
    ```
    - This will output the path, typically something like `/opt/homebrew/opt/php@8.0`
- ### Step 2: Update MAMP's PHP Configuration
    - Go to
      ```
      Applications/MAMP/bin/php/
      
      ```
    - Create a new folder named php8.0.30
    - Inside this folder, create symbolic links to the necessary binaries from your Homebrew installation:
      ```
          ln -s /opt/homebrew/opt/php@8.0/bin/php php
          ln -s /opt/homebrew/opt/php@8.0/sbin/php-fpm php-fpm
          ln -s /opt/homebrew/opt/php@8.0/lib/httpd/modules modules
      
      ```
      Make sure to replace the paths with the actual output from the brew --prefix php@8.0 command if it's different.
