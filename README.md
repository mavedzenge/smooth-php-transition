**PHP EXERCISE - backwards compatible migration from PHP 5.6 to 8.0**

This is a small piece of code that needs to be prepared for this migration. We are **not interested in waiting for full
refactoring**, therefore we need to have a smooth backwards compatible transition period between software releases.
Keeping in mind that we use Symfony (4.4) as a framework for the backend system, ideally, we would like to see full
transformation to it. The decision how-to migrate is solely yours. There are no initial guidelines, however, you can
follow the steps below:

- describe your migration plan
- if there is more than one solution, please recommend the better one and explain the difference between them
- apply necessary changes and best-known practices and/or standards
- make sure each page view remains the same unless there is HTML standard violation
- make sure URL behaviour remains the same
- make sure all the HTTP requests pointing to the same location (public/index.php )
- reuse as much code as you can (e.g. 'Main_finance' class)
- implement Doctrine on existing database but don't change any table or field name
- describe database migration process if there are any necessary changes
- use version control tagging system and create at least 3 releases (we will check each of them)
- make sure you don't rewrite everything in one go. Please rewrite piece by piece and make sure each release is fully
  backwards compatible with PHP 5.6 and we are able to switch between PHP versions without altering the code
- feel free to use your preferable environment e.g. Docker, Vagrant, etc.
- describe bootstrap process for each PHP version (e.g. below)

Project bootstrap example:

```
- Assume that MySQL (works on 'localhost'), PHP5 (as php5) and PHP8 (as php8) is installed and works as native software in your OS
- Create an empty MySQL database and import the "database.sql" file.
- Execute "composer install"
- Run local php5 server "php5 -S 127.0.0.1:8080 -t public"
- Run local php8 server "php8 -S 127.0.0.1:8081 -t public"
- Another step...
    ...
    ...

```

_PLEASE MAKE SURE:_

- Please use Github and set up a git repository
- Please ensure you have at least one commit within the first hour. We want to be able to know how you develop, so we
  will review your commit history
- Send us the Github link to your repository once you are happy
