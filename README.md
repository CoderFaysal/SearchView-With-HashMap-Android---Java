# SearchView With HashMap Android - Java


### Step 1. Add This Line In Your Adapter

```
 public void setFilteredList(ArrayList<HashMap<String, String>> filteredList) {  
       this.arrayList = filteredList;  
       notifyDataSetChanged();  
     }  
```


### Step 2. Add this method in onQueryTextChange in SearchView

```
private void fileList(String newText) {  
     ArrayList<HashMap<String, String>> arrayList1 = new ArrayList<>();  
     for (HashMap<String, String> detailsItem : arrayList) {  
       if (detailsItem.get("name").toLowerCase().contains(newText.toLowerCase())) {  
         arrayList1.add(detailsItem);  
       }  
     }  
     if (arrayList1.isEmpty()) {  
       Toast.makeText(MainActivity.this, "No Data Found", Toast.LENGTH_SHORT).show();  
     } else {  
       myAdapter.setFilteredList(arrayList1);  
     }  
   }  
```
