# Web Engineering 2021-2022 / Lab2 RPC over HTTP

Please, go to the [Wiki](https://github.com/UNIZAR-30246-WebEngineering/lab2-rpc-over-http/wiki) in order to get the instructions for this assignment.

## Solution

To run the server, it's needed to obtain the generated classes TranslationRequest and TranslationResponse.

To generate those classes from the translator.xsd file, we have to apply the command on the Server:
```
.\gradlew genJaxb
```

Once the classes are genereated we can run the Server:
```
.\gradlew bootRun
```

Note that manually applying the genJaxb task is not necessary as the bootRun task has been programmed to run the genJaxb task itself.

The server will publish the classes on a .wdsl file. So the client will need to download that wdsl to be able to generate those clases.

For that purpose, while the Server is runnin, apply the genJaxb task on the client.
```
.\gradlew genJaxb
```

And then just run the client as well
```
.\gradlew bootRun
```


As additional notes, it was necessary to change the jvm used by default to a java 11 and used gradle 7.1 instead of 7.2

The server has also been completed to return a fixed message when the translate function is called.

