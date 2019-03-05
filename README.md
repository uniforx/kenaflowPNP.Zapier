# kenaflowPNP.Zapier

[Link to zapier](https://www.zapier.com)

[Link to documentation of kenaflow](https://doc.kenaflow.com)

[Video tutorial at Youtube](https://www.youtube.com/watch?v=7ioDbB1Ue4w)

# How to request an Zapier WebHook

**kenaflow** has now limits, but instead of connecting to many services you can use a middleware provider like **zapier** to connect **kenaflow** to more than 1000+ services.

A WebHook of **zapier** looks like this "https://hooks.zapier.com/hooks/catch/123/abc/"

You can send an JSON-String which will be converted to an object or build an new object. In **zapier** you can use the defined key-valuer-pairs.

```PowerShell
  try {
    $Body = ConvertFrom-KFJson -JSON $item["Body"]
  } catch {
    $Body = @{"Body"=$item["Body"]}
  }
  Invoke-WebRequest -Uri $item['To'] -Body $Body
```
