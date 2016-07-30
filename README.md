docker-moodle
=============

A Dockerfile that installs and runs Moodle stable 3.1.

## Installation

```
git clone https://github.com/aldonecci/docker-moodle31
cd docker-moodle31
docker build -t moodle .
```

## Usage

To spawn a new instance of Moodle:

```
docker run -d --name DB -p 3306:3306 -e MYSQL_DATABASE=moodle -e MYSQL_USER=moodle -e MYSQL_PASSWORD=moodle centurylink/mysql
docker run -d -P --name moodle --link DB:DB -e MOODLE_URL=http://172.16.239.146:8080 -p 8080:80 moodle
```

You can visit the following URL in a browser to get started:

```
http://172.16.239.146:8080 
```

## Caveats
The following aren't handled, considered, or need work: 
* log handling (stdout?)
* email (does it even send?)

## Credits

This is a reductionist take on [sergiogomez](https://github.com/sergiogomez/)'s docker-moodle Dockerfile.

