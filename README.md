# Linux Error

###Error1:
-> If you are getting the error "cannot open shared object file: No such file or directory"
  ```shell
  $>./app_name
  $>error while loading shared libraries: app_lib.so.11: cannot open shared object file: No such file or directory
  ```

###Solution1:
->Search app_lib.so.11 file in the computer 

    ```
    $>find / |grep "app_lib.so.11"
    $>/usr/local/lib/app_lib.so.11
    ```
->Check the existence of the path (in my case "/usr/local/lib/") present in the dynamic library path environnement 
```
  $> echo $LD_LIBRARY_PATH
 ```
 -> If not set, then set the path 
 ```
  $>LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/lib
  $>export LD_LIBRARY_PATH
  ```
-> Run the application
```
  $> ./app_name
```
