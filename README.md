# home-assistant-helm

Home Assistant

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/brandtkeller/home-assistant-helm/issues/new/choose)**

## Requirements

## Dependencies

## Try it out

## TODO
- support for configuration files in configmap
    - configmap vs persistence 
    - The default execution includes a lot of files that would be better secured via persistence
    - can you name a file with a sub-directory included? ie `test/config.yaml` and have it created via configmap volume mount as expected?
- support for dynamic environment variables