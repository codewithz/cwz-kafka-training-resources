
Task 1
  1.  Create a topic called as your_company_orders [the topic contains 3 partitions and 2 RF]
  2.  Listed below is the list of states in USA, you need to generate 25000 records of orders where key is the state and value is order value between [$200 -- $2000] (choose randomly)
     <code>
       String stateString =
				"AK,AL,AZ,AR,CA,CO,CT,DE,FL,GA," +
						"HI,ID,IL,IN,IA,KS,KY,LA,ME,MD," +
						"MA,MI,MN,MS,MO,MT,NE,NV,NH,NJ," +
						"NM,NY,NC,ND,OH,OK,OR,PA,RI,SC," +
						"SD,TN,TX,UT,VT,VA,WA,WV,WI,WY";
      
		String[] stateArray = stateString.split(",");
	</code>
  4.  Execute the producer and check the written records in the consumer 

<hr>

Wikimedia Base URL: 
URL to check the Wikimedia changes : https://stream.wikimedia.org/v2/stream/recentchange

<a href="https://esjewett.github.io/wm-eventsource-demo/"> Graphical </a>

<a href="https://codepen.io/Krinkle/pen/BwEKgW?editors=1010"> Dashboard </a>


https://link.excalidraw.com/l/3AzfHZfUtYK/7u9rgl6ckAx

<hr>

For Compiling the avsc files to Java Generated files, download the jar in avro jar directory in the repo and use the following command

<code>
java -jar avro-tools-1.9.1.jar compile schema schema/User.avsc .
</code>

<hr>

<code>
  private static User extractKey(Event event) {
        return User.newBuilder()
                .setUserId(event.getInternalUser().getUserId().toString())
                .setUsername(event.getInternalUser().getUsername())
                .setDateOfBirth((int)event.getInternalUser().getDateOfBirth().toInstant().atZone(ZoneId.systemDefault()).getLong(ChronoField.EPOCH_DAY))
                .build();
    }

    private static Product extractValue(Event event) {
        return Product.newBuilder()
                .setProductType(ProductType.valueOf(event.getInternalProduct().getProductType().name()))
                .setColor(Color.valueOf(event.getInternalProduct().getColor().name()))
                .setDesignType(DesignType.valueOf(event.getInternalProduct().getDesignType().name()))
                .build();
    }
</code>
<hr>
<code>
networks:
  kafka-network:
    driver: bridge
	</code>

  <hr>
  Word Count Kafka Stream Steps 

  Word Count Streams App  

Kafka Kafka Streams --> Kafka - 2 || Streams -1 

1. Stream from Kafka    <null, "Kafka Kafka Streams">
2. MapValues  lowercase  <null,"kafka kafka streams">
3. FlatMapValues split by space <null,"kafka">, <null,"kafka">,<null,"streams">
4. SelectKey apply a key <"kafka","kafka">, <"kafka","kafka">,<"streams","streams">
5. GroupByKey before aggregation (<"kafka","kafka">, <"kafka","kafka">) (<"streams","streams">)
6. Count accurance in each group (<"kafka",2>)(<"streams,1>)
7. To write the data to kafka   --> topic

  <hr>
