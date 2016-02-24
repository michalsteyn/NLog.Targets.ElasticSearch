NLog.Targets.ElasticSearch2
==========================

The Elasticsearch target works best with the BufferingWrapper target applied. By default the target assumes an Elasticsearch node is running on the localhost on port 9200.

See [wiki](https://github.com/ReactiveMarkets/NLog.Targets.ElasticSearch/wiki) for parameters, but note that the extension assembly must be listed as NLog.Targets.ElasticSearch2 instead of NLog.Targets.ElasticSearch.

```xml
<nlog>
  <extensions>
    <add assembly="NLog.Targets.ElasticSearch2"/>
  </extensions>
  <targets>
    <target name="elastic" xsi:type="BufferingWrapper" flushTimeout="5000">
  	  <target xsi:type="ElasticSearch"/>
    </target>
  </targets>
  <rules>
    <logger name="*" minlevel="Info" writeTo="elastic" />
  </rules>
</nlog>
```
