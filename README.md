_Four legendary heroes were fighting for the land of Vindinium_

_Making their way in the dangerous woods_

_Slashing goblins and stealing gold mines_

_And looking for a tavern where to drink their gold_

### Warning

The vindinium dot org website has been discontinued, and the domain now belongs to Internet parasites.

### Requirements

- Java 8
- MongoDB 3.2

### Installation

Feel free to install a local instance for your private tournaments.
You need [sbt](http://www.scala-sbt.org/), Java 8, a MongoDB 3.2 instance running, and a Unix machine (only Linux has been tested, tho).

```sh
git clone git://github.com/ornicar/vindinium
cd vindinium
cd client
./build.sh
cd ..
sbt -sbt-version 0.13.16 compile
sbt -sbt-version 0.13.16 run
```

Vindinium is now running on `http://localhost:9000`.

#### Optional reverse proxy

Here's an exemple of nginx configuration:

```
server {
 listen 80;
 server_name my-domain.org;

  location / {
    proxy_http_version 1.1;
    proxy_read_timeout 24h;
    proxy_set_header Host $host;
    proxy_pass  http://127.0.0.1:9000/;
  }
}
```

### Developing on the Client Side stack

while the Server runs with a `sbt run`, you can go in another terminal in the `client/` folder and:

- Install once the dependencies with `npm install` (This requires nodejs to be installed)
- Be sure to have `grunt` installed with `npm install -g grunt-cli`
- Use `grunt` to compile client sources and watch for client source changes.

### Credits

Kudos to:

- [vjousse](https://github.com/vjousse) for the UI and testing
- [veloce](https://github.com/veloce) for the JavaScript and testing
- [gre](https://github.com/gre) for the shiny new JS playground
