# Spring_tutorial_day0318

## Consuming a RESTful Web Service
Fetching a REST Resource
{
   type: "success",
   value: {
      id: 10,
      quote: "Really loving Spring Boot, makes stand alone Spring apps easy."
   }
}

What I need is value in JSON above(eg: type, value{id, quote[0213.txt](https://github.com/SyngyeonTak/Spring_tutorial_day0318/files/6163742/0213.txt)
}).


### @JsonIgnoreProperties
This annotation is from the Jackson JSON processing library to indicate that any properties not bound in this type should be ignored.

@JsonIgnoreProperties(ignoreUnknown = true)
This is applicable at deserialization of JSON to Java object ( POJO ) only

### @RestTemplate



### Codes
Quote{                              
  type;value;
  constructor; getter; setter; toString;
}

Value{
  id; quote;
  constructor; getter; setter; toString;
}

@SpringBootApplication
ConsumingRestApplication{
  logger
  
  main{SpringApplication.run(ConsumingRestApplication.class, args)};
  
  @Bean
  public RestTemplate restTemplate(RestTemplateBuilder builder){return builder.build()}
  
  @Bean
  public CommandLineRunner run(RestTemplate restTemplate) throws Exception{
    returns args ->{
      Quote quote = restTemplate.getForObject(
        url, Quote.class
      );
      log.info(quote.toString());
    };
  }
}


