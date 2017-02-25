# cautions-monda

How do I sorted Map by Value !!!

//create treeMap
TreeMap<String, Integer> treeMap = new TreeMap<String, Integer>();

//sort treeMap in sortedMap
LinkedHashMap<String, Integer> sortedMap = 
				    treeMap.entrySet().stream().
				    sorted(Entry.comparingByValue()).
				    collect(Collectors.toMap(Entry::getKey, Entry::getValue,
				                             (e1, e2) -> e1, LinkedHashMap::new));
//print sortedMap

for(Map.Entry<String, Integer> mapEntry : sortedMap.entrySet()) {
			  System.out.printf("%s -> %d%n", mapEntry.getKey(), mapEntry.getValue());
