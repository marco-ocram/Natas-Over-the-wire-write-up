### Level 0
#### Simply go to the specified url and login

### Level 0-1 & 1-2
#### Inspect element and you'll find the password in a comment
#### Password for level 1-2
#### gtVrDuiDfck831PqWsLEZy5gyDz1clto

### Level 2-3
#### This level has a bluff. The html has a password which does not work. Diving deeper into the html shows `before` and `after` tags with an image at `/files` route. If we use this route we can see a `users.txt` which has the password
#### natas3:sJIJNW6ucpu6HPZ1ZAchaDtwd7oGrD14

### Level 3-4
#### There are some directories of a website which are prevented by the user to be searched over google and these file. Robots.txt file is the instruction for web crawlers to follow.
> http://natas3.natas.labs.overthewire.org/robots.txt
>User-agent: *
Disallow: /s3cr3t/

>http://natas3.natas.labs.overthewire.org/s3cr3t/
#### `users.txt` file will provide the next password
#### Password - Z9tkRkWmpt9Qr7XrR5jWRkgOU901swEZ
