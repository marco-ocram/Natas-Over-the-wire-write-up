## Level5-6
#### Relatively easier challenge i feel. Use Burpsuite to intercept the requests and in the cookies we find "loggedin=0". Simply change it to "loggedin=1"
#### Password - aGoY4q2Dc6MgDq4oL4YtoKtyAg9PeHa1

## Level 6-7
#### Yet again an easy challenge. Login to natas6. View source code. We can find "/include/secret.inc". We can use this route. It provides us with a secret key. Now input this to input secret field and it grants us the password.
#### Password - 7z3hEENjQtflzgnT29q7wAvMNfZdh0i9

## Level 7-8
#### Viewing the source code reveals that the password in */etc/natas_webpass/natas8*. This tells us that we have to try different route in the given url. If we try *index.php/etc/natas_webpass/natas* , it throws an error that reveals the present directory of index file, which is */var/www/natas/natas7/index.php*. This is File Inclusion Vulnerability. To change different routes, we have to add route to *page=* path. If we've seen a directory structure of Linux , we know */etc* and */var* are in same directory. Hence, we add the path to *page=* section as 
>> http://natas7.natas.labs.overthewire.org/index.php?page=../../../../etc/natas_webpass/natas8

#### Password = DBfUBfqQG69KvJvJ1iAbMoIpwSNQ9bWe

## Level 8-9
#### On viewing the source code, we can find the *encodesecret* function. Let's fire up an online PHP editor and write the decode function.
>> <?php
>> function decodesec($secret)
>> {
>> return base64_decode(strrev(hex2bin($secret)));
>> }
>> print decodesec("3d3d516343746d4d6d6c315669563362");
>> ?>
#### Password - W0mMhUcRRnG8dcghE4qvk3JA9lGt8nDl

## Level 9-10
#### On viewing the source code,we come across 
>grep -i $key dictionary.txt
#### This tells us that the search field is itself working on commands, hence we can try code injectin using a ";". First, we try find the present directory, use
>blabla;pwd
#### This gives */var/www/natas/natas9*. From previous levels, we know the password is in */etc/natas_webpass/natas10* . Hence we use the following code injection.
>blabla; cat ../../../../etc/natas_webpass/natas10

#### Password - nOpp1igQAkUzaI1GUUjzn1bFVj7xCNzu
