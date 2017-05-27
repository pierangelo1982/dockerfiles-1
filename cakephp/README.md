# CakePHP
This is a docker image for CakePHP.

## Run
```
sudo docker run --name cakephp -p 80:80 -d shimomo/cakephp
```

## Copy to Host
```
sudo docker cp cakephp:/var/www/html/cakephp /path/to
```

## Copy to Container
```
sudo docker cp /path/to/cakephp cakephp:/var/www/html
```
