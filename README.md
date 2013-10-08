Ok, so...

//Travis Stoll
//10-4-2013


-index.php is a blank php file with only contents of <?php.  This is to do the detection of php.

Procfile defines a web boot file of conf/web-boot.sh.  If we wanted worker threads point to a non-www folder, we can define that here

Web-boot.sh defines http config file and apache log dirs

http config file, default.conf defines the www directory of www based off app root.



Heroku boots based off procfile and php discovery



Config:

heroku addons:add scheduler:standard
heroku addons:open scheduler 
heroku config:add LD_LIBRARY_PATH=/app/php/ext:/app/apache/lib
./php/bin/php /app/www/workers/work.php
bin/php /app/www/workers/work.php 