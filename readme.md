![Laravel](https://laravel.com/assets/img/components/logo-laravel.svg)

<h1 align="center">Genealogy Application</h1>

[![Build Status](https://travis-ci.org/nafiesl/silsilah.svg?branch=master)](https://travis-ci.org/nafiesl/silsilah)
[![Coverage Status](https://coveralls.io/repos/github/nafiesl/silsilah/badge.svg?branch=master)](https://coveralls.io/github/nafiesl/silsilah?branch=master)

> **Development in progress**  
> In development progress, any changes of table structure **will be updated** directly to corresponding **migration file**.
>
> [Baca README Bahasa Indonesia](readme.id.md)

## About
Genealogy (Silsilah) application to record our family members.

## Features
This application uses Bahasa Indonesia and English based on `config.locale`.

### Logic Concept
1. A person can have one father
2. A person can have one mother
3. A person can have one parent (couple of mother and father)
4. A person can have 0 to many children
5. A person can have 0 to many spouses (husbands or wife)
6. A couple can have 0 to many children (based on parent_id)

### Family Member Entry
1. Enter Name and Gender
2. Set Father
3. Set Mother
4. Add Spouse
5. Add Child

### Person Attribute
1. Nickname
2. Gender
3. Fullname
4. Date of birth
5. Date of death (or at least year of death)
6. Address
7. Phone Number
8. Email

### Couple Attribute (TODO)
1. Husband
2. Wife
3. Marriage Date
4. Divorce Date
5. Address

## How to Install

### Server Requirements

This application can be installed on local server and online server with these specifications :

1. PHP 7.3 (and meet other [Laravel 8.x server requirements](https://laravel.com/docs/8.x/deployment#server-requirements)),
2. MySQL or MariaDB database,
3. SQlite (for automated testing).

### Installation Steps

1. Clone the repo : `git clone https://github.com/nafiesl/silsilah.git`
2. `cd silsilah`
3. `composer install`
4. `cp .env.example .env`
5. `php artisan key:generate`
6. Create **database on MySQL**
7. **Set database credentials** on `.env` file
8. `php artisan migrate`
9. `php artisan storage:link`
10. `php artisan serve`
11. Register as new user to start using the application.
12. Add the registered email address to the `.env` file:
    ```
    SYSTEM_ADMIN_EMAILS=admin@email.com;other_admin@email.com
    ```

## Testing
This application built with testing (TDD) using in-memory sqlite database.
```bash
$ vendor/bin/phpunit
```

#### Automated Testing
![Automated Testing](public/images/07-automated-testing.jpg "Automated Testing")
