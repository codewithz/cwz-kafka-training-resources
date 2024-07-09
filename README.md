
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
