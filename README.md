# Adapter
package com.example.pappu.a5_4demo;

import android.content.Intent;
import android.graphics.Color;
import android.net.Uri;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.AdapterView;
import android.widget.ArrayAdapter;
import android.widget.ListView;
import android.widget.TextView;

public abstract class MainActivity extends AppCompatActivity implements AdapterView.OnItemClickListener {

    String students[] = {"A" , "B", "C"};
    String number[] = {"1", "2", "3"};


    ListView listView;
    TextView textView;
    //private Object Friends;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Friends = getResources().getStringArray(R.array.students);
        listView = (ListView) findViewById(R.id.listview);
        textView = (TextView) findViewById(R.id.textView);


        ArrayAdapter<String> adapter = new ArrayAdapter<String>( this,android.R.layout.simple_list_item_1,Friends);

        listView.setAdapter( adapter );
        listView.setOnItemClickListener(this);


        

    }
/*
    @Override
    public void onItemClick(AdapterView<?> parent, View view, int position, long id) {
        textView.setText("User :" +Friends(position));
        textView.setTextColor(Color.BLUE);

        Intent intent = new Intent(Intent.ACTION_DIAL, Uri.parse("tel:"+number[position]));
        startActivity(intent);
    }*/
}

