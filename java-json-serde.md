## JSON Serialization and Deserialization using Jackson

It's common to use Jackson and the ObjectMapper. 
But creating ObjectMapper everytime in a method or even class level is a costly affair. It is thread safe and can be utilized as a util.
```java
import com.fasterxml.jackson.databind.DeserializationFeature;
import com.fasterxml.jackson.databind.MapperFeature;
import com.fasterxml.jackson.databind.ObjectMapper;
import lombok.extern.log4j.Log4j;

@Log4j
public class JsonUtils {

    private static final ObjectMapper OBJECT_MAPPER;

    static {
        OBJECT_MAPPER = new ObjectMapper();
        OBJECT_MAPPER.configure(MapperFeature.ACCEPT_CASE_INSENSITIVE_PROPERTIES, true);
        OBJECT_MAPPER.configure(DeserializationFeature.FAIL_ON_UNKNOWN_PROPERTIES, false);
    }

    public static <T> T fromJson(final String json, final Class<T> classe) {
        try {
            return OBJECT_MAPPER.readValue(json, classe);
        } catch (Exception e) {
            log.error(e);
            try {
                return classe.newInstance();
            } catch (InstantiationException | IllegalAccessException ex) {
                return null;
            }
        }
    }
}
```