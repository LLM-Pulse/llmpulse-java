

# GetTimeseriesCollectionIdParameter

## oneOf schemas
* [Integer](Integer.md)
* [String](String.md)

## Example
```java
// Import classes:
import ai.llmpulse.sdk.model.GetTimeseriesCollectionIdParameter;
import ai.llmpulse.sdk.model.Integer;
import ai.llmpulse.sdk.model.String;

public class Example {
    public static void main(String[] args) {
        GetTimeseriesCollectionIdParameter exampleGetTimeseriesCollectionIdParameter = new GetTimeseriesCollectionIdParameter();

        // create a new Integer
        Integer exampleInteger = new Integer();
        // set GetTimeseriesCollectionIdParameter to Integer
        exampleGetTimeseriesCollectionIdParameter.setActualInstance(exampleInteger);
        // to get back the Integer set earlier
        Integer testInteger = (Integer) exampleGetTimeseriesCollectionIdParameter.getActualInstance();

        // create a new String
        String exampleString = new String();
        // set GetTimeseriesCollectionIdParameter to String
        exampleGetTimeseriesCollectionIdParameter.setActualInstance(exampleString);
        // to get back the String set earlier
        String testString = (String) exampleGetTimeseriesCollectionIdParameter.getActualInstance();
    }
}
```


