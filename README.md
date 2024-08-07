# OVH Akvorado Grafana Plugin
Plugin to display akvorado data

## Goal
This plugin aim to allow user to display [akvorado](https://github.com/akvorado/akvorado) data directly in Grafana.

## Dependencies

This plugin need [Sankey Panel plugin](https://grafana.com/grafana/plugins/netsage-sankey-panel/) to display sankey graph

## Run locally

To run locally the plugin:
~~~
nom install
npm run build
npm run server
~~~

### Use sankey plugin with docker-compose

To display a sankey query you need the sankey plugin. 
You can download the plugin [here](https://grafana.com/grafana/plugins/netsage-sankey-panel/?tab=installation)
Unzip the folder
Add the path to the folder to docker-compose volumes:
`- /path/to/netsage-sankey-panel:/var/lib/grafana/plugins/netsage-sankey-panel`


## Add new data source

In grafana
- Add new data source
- Akvorado
- Add new data source
- Enter the base url; eg: https://demo.akvorado.net/

## Query parameters

- Tye of query:
  - sankey
    - *When using sankey at least two dimension must be used*
  - timeseries
- Unit
  - l3bps
  - pps
- Dimension
  - Multiselect list: values are fetch from the back end
- Limit: number of returned result
  - *The number of return result is in fact limit +1 where +1 is the value "other" showing the aggregation of all other values*
- Filters: expression to filter result
  - *The field is autocomplete and lint based on syntax checker*




