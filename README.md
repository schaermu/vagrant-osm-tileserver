# Standalone OpenStreetMap-Tileserver
This Vagrant Box's target is to provide a completely standalone, off-the-wire running map-server. The following components are being leveraged to provide this functionality:

* [Apache 2](https://httpd.apache.org/) with [mod_tile](https://github.com/openstreetmap/mod_tile) (mod_tile is compiled from latest master on provision)
* [renderd](https://github.com/openstreetmap/mod_tile) (compiled from latest master on provision)
* [Mapnik](https://github.com/mapnik/mapnik) (currently locked on 2.2.x branch due to compat issues)
* [PostgreSQL 9.3](https://www.postgresql.org/)
* [osm2pgsql](https://github.com/openstreetmap/osm2pgsql) (compiled from latest master on provision)

The maps are rendered using [osm-bright](https://github.com/mapbox/osm-bright), GIS data is imported from [Geofabrik](http://download.geofabrik.de/) (using the latest data for [Switzerland](http://download.geofabrik.de/europe/switzerland.html), downloaded on provision).

## Usage
1. Make sure you have the latest versions of both [Vagrant](https://www.vagrantup.com/downloads.html) and [VirtualBox](https://www.virtualbox.org/wiki/Downloads) installed.
2. Clone or download the repository.
3. Open a shell/command line and `cd` to `vagrant`
4. Run `vagrant up`
5. Wait until provisioning is finished (**depending on your internet connection, this can take up to several hours!**).
6. Fire up a browser and open `http://localhost:8080/` to open a Leaflet interface connected to your new tileserver.
