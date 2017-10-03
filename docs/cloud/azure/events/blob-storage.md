---
title: Microsoft Azure - Events - Blob Storage
---
       
Using the Azure Blob storage trigger, your function code is called when a new or updated blob is detected. The blob contents are provided as input to the function.

https://docs.microsoft.com/en-us/azure/azure-functions/functions-bindings-storage-blob

`squeezer.yml`

```yaml
events:
  - type: blob
    x-azure-settings:
      name: item # The name used to identify the trigger data in your code
      path: input/{name} # container to monitor, and optionally a blob name pattern
      connection: AzureWebJobsStorage # property must contain the name of an app setting that contains a storage connection string
```

```javascript
'use strict';

exports.handler = (context, event) => {
  context.log(`Got event: ${event}`);
  context.done();
};
```