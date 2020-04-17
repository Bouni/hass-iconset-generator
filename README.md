# hass-iconset-generator

This script converts SVG icons into an HTML file that can be used in Home-Assistant for custom icons.

## Installation

```
# clone git repo
git clone https://github.com/bouni/hass-iconset-generator
cd hass-iconset-generator

# install dependencies 
sudo pip install -r requirements.txt
```

## Usage

```
python hass-iconset-generator.py /path/to/svgs/icons -n myiconset
```

The above example assumes you're already in the hass-iconset-generator folder. 
With the `-n` option you can specify a namespace which is later used in HA to address the iconset. If not set it will be named `hass-iconset`.
Its highly recommended to name the svgs as you want the icons later to be named. For example if the svg is lightbulb.svg you will address it in HA like `myiconset:lightbulb`
Alternatively you can pass the `-e` option which will enumerate all icons (icon-0, icon-1 ...).

The script outputs two html files in the folder where the svg icons are located.

`myiconset.html` contains the iconset itself. Copy this file in your `config` folder into the `www` folder (created it if its not there).
`myiconset-docs.html` is an html file for your reference, open it in the browser to see all icons and their name.

To make the iconset available after you copyed it to config/www, you need to add the following to you configuration.yaml:

```
frontend:
  extra_html_url:
    - /local/myiconset.html

```
 
