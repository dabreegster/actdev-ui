# ACTDEV 

Active travel provision and potential in planned and proposed development sites.


## Installation

This assumes you're running this on Apache.

```
# Enter your webserver's files area
cd /var/www/

# Clone the repo
sudo git clone https://github.com/cyipt/actdev-ui
cd actdev-ui

# Clone the library within the repo
cd js/lib/
sudo git clone https://github.com/cyclestreets/Mapboxgljs.LayerViewer
cd -

# Add an Apache configuration
sudo cp -pr .apache-vhost.conf.template /etc/apache/sites-available/actdev.conf
sudo a2ensite actdev
sudo service apache2 restart

# Add local host
sudo sh -c "echo '127.0.0.1 actdev' >> /etc/hosts"

# Open your web browser at http://actdev/
```


## Development guidelines

To make changes/additions to layers, amend `/js/actdev.js`, which contains the layer declarations.

The layers can include any of the [https://github.com/cyclestreets/Mapboxgljs.LayerViewer/blob/master/src/layerviewer.js#L218](properties supported by the underlying library).

To add a new layer:

 1. In `/js/actdev.js`, add the new layer and its parameters
 2. In `/index.html`, add in a new menu entry in the menu `<nav>` section
 3. In `/index.html`, add a panel in `<div id="sections">` which provides some explanation


## License

GPL3.
