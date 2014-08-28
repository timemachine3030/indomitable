> Strength does not come from physical capacity. It comes from an _indomitable will_  
> - [Mahatma Gandhi](http://en.wikipedia.org/wiki/Mahatma_Gandhi)

Indomitable is a module for helping you manage user passwords. The module is based on the [simple password hashing API](https://wiki.php.net/rfc/password_hash) for PHP.

###The Problem
No matter the password hashing algorithm (SHA-256, PBKDF2, bcrypt, scrypt) you use in your application it will soon become out of date and replaced with a more secure variant. 

This is especially painful if you are writing software with a legacy user database that was designed to use an older, now insecure method of storing passwords. You can't _magically_ update all of those old user passwords so you are forced to conform with insecure standards.

Additionally, some algorithms have an optional _cost_ that slows down the ability to generate hashes. This is an excellent feature allowing hash complexity to increase along with CPU speed. We want the hashing function to be slow for attackers with out being so slow that it becomes unusable to legitimate user's login attempts. But how do you update your cost without invalidating all of your currently stored passwords?

###Become `indomitable`
This module aims to provide a method for upgrading old password hashes to new algorithms by checking the hash each time a user is verified and rehashing the password if needed.

####Benefits
 - Legacy databases of users are, over time updated to the state of the art. 
 - You can update and tune the cost of your hashing algorithm without fear of invalidating your users.
