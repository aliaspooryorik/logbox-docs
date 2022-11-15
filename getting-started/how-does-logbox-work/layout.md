# Layout

The layout component defines the format of the message to store in an appender repository. Be default, each appender already has a pre-defined message format. However, if you do not like the format of the message you can easily change it by creating your own layout component and registering it with the appender. You can do this in the configuration object when you add appenders:

> **Note:** Not all appenders use a layout object (e.g. the `DBAppender`).

```javascript
//add a FileAppender with my own formatting
props = { filePath='/logs', fileName='Test' };
config.appender(
    name='Fileapp',
    class="logbox.system.logging.appenders.FileAppender",
    properties=props,
    layout="model.logging.MyFileLayout"
);
```

So to create your very own layout object, you just need to extend the LogBox abstract layout object: `logbox.system.logging.Layout` and implement the `format()` method.
