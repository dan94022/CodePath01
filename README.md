# CodePath01
Dan's Completed Android for Engineers initial code assignment/challenge
Code for "main" (SimpleDisplayActivityActivity) & activity-simple_display.xml are separated by //// & included below;


///////////////// Code from for SimpleDisplayActivity.java

package com.example.danc.mycodepathapp1;

import android.support.v7.app.ActionBarActivity;
import android.os.Bundle;
import android.view.Menu;
import android.view.MenuItem;
import android.view.View;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;


public class SimpleDisplayActivity extends ActionBarActivity {
    // EditText Field declaration
    private EditText etWords; // currently null
    // define  variable for TextView called tvLabel; format private <type> <id>;
    private TextView tvLabel;


    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        // creates the layout in memory

        setContentView(R.layout.activity_simple_display);
        // views have been created in the layout
        // Find references to views in xml using findViewById() & cast(EditText)
        etWords = (EditText)findViewById(R.id.etWords);
        // store value of id in variable tvLabel & cast
        // <id> = (<types>) findviewById(R.id,<id>);
        tvLabel = (TextView) findViewById(R.id.tvLabel);

    }


    @Override
    public boolean onCreateOptionsMenu(Menu menu) {
        // Inflate the menu; this adds items to the action bar if it is present.
        getMenuInflater().inflate(R.menu.menu_simple_display, menu);
        return true;
    }

    @Override
    public boolean onOptionsItemSelected(MenuItem item) {
        // Handle action bar item clicks here. The action bar will
        // automatically handle clicks on the Home/Up button, so long
        // as you specify a parent activity in AndroidManifest.xml.
        int id = item.getItemId();

        //noinspection SimplifiableIfStatement
        if (id == R.id.action_settings) {
            return true;
        }

        return super.onOptionsItemSelected(item);
    }

    // fired when the Submit button is clicked
    public void onSubmit(View view) {
        /* initially show Hello World! message
         using Toast as alert to test method
        Toast.makeText(this,"Hello World", Toast.LENGTH_SHORT).show(); */
        // get the value from the text field (etWords)
        // set the value into the label (tvLabel)
        String fieldValue =etWords.getText().toString();
        //change  "Nothing Yet" to the value of tvLabel value
        // Set the value into the label (tvLabel)
        tvLabel.setText(fieldValue);
        // Display the value with a SHORT alert{i.e., toast}
        Toast.makeText(this,fieldValue, Toast.LENGTH_SHORT).show();
    }
}

///////////////////////////////////////////////////////////// final xml layout code ==> activity-simple_display.xml 

<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools" android:layout_width="match_parent"
    android:layout_height="match_parent" android:paddingLeft="@dimen/activity_horizontal_margin"
    android:paddingRight="@dimen/activity_horizontal_margin"
    android:paddingTop="@dimen/activity_vertical_margin"
    android:paddingBottom="@dimen/activity_vertical_margin"
    tools:context=".SimpleDisplayActivity">

    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="@string/submit_label"
        android:onClick="onSubmit"
        android:id="@+id/btnSubmit"
        android:layout_centerVertical="true"
        android:layout_centerHorizontal="true" />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textAppearance="?android:attr/textAppearanceLarge"
        android:text="@string/nothing_label"
        android:id="@+id/tvLabel"
        android:layout_below="@+id/btnSubmit"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="40dp" />

    <EditText
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+id/etWords"
        android:layout_above="@+id/btnSubmit"
        android:layout_marginBottom="40dp"
        android:layout_centerHorizontal="true"
        android:hint="@string/enter_any_text_label" />

</RelativeLayout>
============= 
