
# Ex.No:7 Develop an android application to display the place name with image using list view in android studio.


## AIM:

To create and develop the application to display the place name with image using list view in android studio

## EQUIPMENTS REQUIRED:

Android Studio(Latest Version)

## ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as “listview″ and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Get contacts details and Display details give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
```
/*
Program to print the list of item.
Developed by:
Registeration Number :
*/
```
```
XML FILE:

<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent"
tools:context=".MainActivity">

<ListView
    android:id="@+id/list"
    android:layout_width="409dp"
    android:layout_height="729dp"
    app:layout_constraintBottom_toBottomOf="parent"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintTop_toTopOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>
```
MyList.xml:

<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
xmlns:app="http://schemas.android.com/apk/res-auto"
xmlns:tools="http://schemas.android.com/tools"
android:layout_width="match_parent"
android:layout_height="match_parent">

<ImageView
    android:id="@+id/icon"
    android:layout_width="60dp"
    android:layout_height="60dp"
    android:padding="5dp"
    app:layout_constraintBottom_toBottomOf="parent"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintHorizontal_bias="0.076"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintTop_toTopOf="parent"
    app:layout_constraintVertical_bias="0.053" />

<LinearLayout
    android:id="@+id/linearLayout"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:orientation="vertical"
    app:layout_constraintBottom_toBottomOf="parent"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintHorizontal_bias="0.382"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintTop_toTopOf="parent"
    app:layout_constraintVertical_bias="0.063">

    <TextView
        android:id="@+id/title"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginLeft="10dp"
        android:layout_marginTop="5dp"
        android:padding="2dp"
        android:text="Medium Text"
        android:textAppearance="?android:attr/textAppearanceMedium"
        android:textColor="#4d4d4d"
        android:textStyle="bold" />

</LinearLayout>
</androidx.constraintlayout.widget.ConstraintLayout>
```
MAIN ACTIVITY.JAVA:

package com.example.place_names;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;
import android.view.View;
import android.widget.AdapterView;
import android.widget.ListView;
import android.widget.TextView;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {
ListView list;
String[] maintitle ={
        "AMERICA","AUSTRALIA",
        "INDIA","GERMANY",
        "RUSSIA","SPAIN",
        "TURKEY","UK"
};
Integer[] imgid= new Integer[]{
        R.drawable.america1, R.drawable.australia1,
        R.drawable.india1, R.drawable.germany1,
        R.drawable.russia1, R.drawable.spain1,
        R.drawable.turkey1, R.drawable.uk1
};
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);

    MyListAdapter adapter=new MyListAdapter(this, maintitle,imgid);
    list= (ListView) findViewById(R.id.list);
    list.setAdapter(adapter);

    list.setOnItemClickListener(new AdapterView.OnItemClickListener() {

        @Override
        public void onItemClick(AdapterView<?> parent, View view, int position, long id) {
            // TODO Auto-generated method stub
            if(position == 0) {
                //code specific to first list item
                Toast.makeText(getApplicationContext(),"Welcome to America",Toast.LENGTH_SHORT).show();
            }
            else if(position == 1) {
                //code specific to 2nd list item
                Toast.makeText(getApplicationContext(),"Welcome to Australia",Toast.LENGTH_SHORT).show();
            }
            else if(position == 2) {

                Toast.makeText(getApplicationContext(),"Welcome to India",Toast.LENGTH_SHORT).show();
            }
            else if(position == 3) {

                Toast.makeText(getApplicationContext(),"Welcome to Germany",Toast.LENGTH_SHORT).show();
            }
            else if(position == 4) {

                Toast.makeText(getApplicationContext(),"Welcome to Russia",Toast.LENGTH_SHORT).show();
            }
            else if(position == 5) {

                Toast.makeText(getApplicationContext(),"Welcome to Spain",Toast.LENGTH_SHORT).show();
            }
            else if(position == 6) {

                Toast.makeText(getApplicationContext(),"Welcome to Turkey",Toast.LENGTH_SHORT).show();
            }
            else if(position == 7) {

                Toast.makeText(getApplicationContext(),"Welcome to UK",Toast.LENGTH_SHORT).show();
            }
        }
    });
}
}
```
MyListAdapter.java:

package com.example.place_names;

import android.app.Activity;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.widget.ArrayAdapter;
import android.widget.ImageView;
import android.widget.TextView;

public class MyListAdapter extends ArrayAdapter<String> {

private final Activity context;
private final String[] maintitle;
private final Integer[] imgid;

public MyListAdapter(Activity context, String[] maintitle, Integer[] imgid) {
    super(context, R.layout.mylist, maintitle);
    // TODO Auto-generated constructor stub
    this.context=context;
    this.maintitle=maintitle;
    this.imgid=imgid;
}
public View getView(int position, View view, ViewGroup parent) {
    LayoutInflater inflater=context.getLayoutInflater();
    View rowView=inflater.inflate(R.layout.mylist, null,true);

    TextView titleText = (TextView) rowView.findViewById(R.id.title);
    ImageView imageView = (ImageView) rowView.findViewById(R.id.icon);

    titleText.setText(maintitle[position]);
    imageView.setImageResource(imgid[position]);
    return rowView;
};
}
```
## OUTPUT
![240933102-da8945d1-3ed5-4d3e-8ca5-2ffe0db827ce](https://github.com/MilitantVlr/Exp7/assets/121683193/969de455-fb2a-4de4-8437-44b13bcfca8d)
![240933181-508ca973-0dda-4e64-ac14-9e5023b5ace6](https://github.com/MilitantVlr/Exp7/assets/121683193/1e61f01b-6455-499e-9d1f-3a226c22a702)
![240933252-c223aae1-83e9-483c-b1de-b20dfd0e5fca](https://github.com/MilitantVlr/Exp7/assets/121683193/a15f0ddb-f9f8-4eee-8f2b-f705a6d11fb7)
![240933296-c387505a-0d4e-4bd6-b1b4-990741446492](https://github.com/MilitantVlr/Exp7/assets/121683193/7e5ba2c9-febf-4102-a985-17abb092be5e)



## RESULT
Thus a Simple Android Application to create and develop the application to display the place name with image using list view in android studio is developed and executed successfully.
