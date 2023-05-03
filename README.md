# SearchView With HashMap Android - Java


### XML View

```
<androidx.appcompat.widget.SearchView
                android:id="@+id/searchView"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:background="@color/white"
                app:queryBackground="@android:color/transparent"
                app:iconifiedByDefault="false"
                android:textSize="14sp"
                android:textColor="@color/black"
                app:queryHint="Search Location"
                android:layout_marginLeft="-20dp"
                />
```


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



## Watch Video

https://web.facebook.com/groups/564163387535104/?multi_permalinks=1267690190515750&ref=share&_rdc=1&_rdr
