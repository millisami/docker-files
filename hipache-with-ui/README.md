# Hipache with ui Airfield

This image runs a [hipache](https://github.com/dotcloud/hipache) with its web-ui [airfield](https://github.com/emblica/airfield) in a container.

Redis is installed at default localhost.

* Hipache port exposed at 80
* Airfield port exposed at 3000

## Usage

    docker run -d -p 3200:3000  millisami/hipache-with-ui:0.1.0

Now you can access the ui at `http://dockerhost:3200`.

Username: admin
Password: kissa2
