# home-assistant-helm

Home Assistant

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/brandtkeller/home-assistant-helm/issues/new/choose)**

## Requirements
Home Assistant and zwave-js-ui do not allow declarative management as I have yet to find. When deploying a vanilla configuration there are some manual setup tasks currently.

- If you are deploying this behind a reverse proxy - you will need to add some configuration to your `/config/configuration.yaml`
```
http:
  use_x_forwarded_for: true
  trusted_proxies:
    - x.x.x.x
```
    - The trusted proxy address being the address of the reverse proxy traffic origination.

- If you are using the `zwave-js-ui` additions you will need to access the UI and `Settings` -> `zwave` -> and click save. This adds the zwave controller as couldn't be done via automation.

## Dependencies

## Try it out

```
git clone https://github.com/brandtkeller/home-assistant-helm.git

cd home-assistant-helm

helm upgrade -i home-assistant -n ha --create-namespace ./chart/
```

## TODO
- support for configuration files in configmap
    - configmap vs persistence 
    - The default execution includes a lot of files that would be better secured via persistence
    - can you name a file with a sub-directory included? ie `test/config.yaml` and have it created via configmap volume mount as expected?
- support for dynamic environment variables