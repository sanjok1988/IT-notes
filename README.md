# notes
# 1&1 IONS Server configuration for laravel
1. point web to public folder
   1. domain and ssl section
   2. click on domain
   3. adjust destination
   4. choose root folder/public
2. change public/htaccess
   1. RewriteRule ^ /index.php [L] (put slash before index.php)
3. For terminal composer run
   1. php7.1 composer.phar update
   2. php7.1 artisan config:clear
