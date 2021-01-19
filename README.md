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
   
   
   # to redirect root to subdirectory in server
```bash
   create .htaccess file and paste below code
   
   RewriteEngine on
   
   RewriteCond %{HTTP_HOST} example\.com [NC]
   
   RewriteCond %{REQUEST_URI} ^/$
   
   RewriteRule ^(.*)$ /blog/$1 [L]
```

# To Renew Jetbrains app with out licence
```bash
REM Delete eval folder with licence key and options.xml which contains a reference to it
for %%I in ("WebStorm", "IntelliJ", "CLion", "Rider", "Pycharm") do (
    for /d %%a in ("%USERPROFILE%\.%%I*") do (
        rd /s /q "%%a/config/eval"
        del /q "%%a\config\options\other.xml"
    )
)REM Delete Permanent User Id and Permanent Device ID
del /q "%APPDATA%\JetBrains\PermanentDeviceId"
del /q "%APPDATA%\JetBrains\PermanentUserId"REM Delete all eval folders and options.xml from appdata
for /f %%f in ('dir /ad /b /r %APPDATA%\JetBrains\') do (
    rd /s /q "%APPDATA%\JetBrains\%%f\eval"
    del "%APPDATA%\JetBrains\%%f\options\other.xml"
)REM delete registry
reg delete "HKEY_CURRENT_USER\Software\JavaSoft" /f
```
