<!--# Heterogeneous-List-View-->
<!--A list view with 2 or more different layouts.-->
<!--CUSTOM ADAPTER-->
package com.example.user.thirdapp;

/**
 * Created by User on 11-02-2016.
 */

import android.content.Context;
import android.view.LayoutInflater;
import android.view.View;
import android.view.View.OnClickListener;
import android.view.ViewGroup;
import android.widget.BaseAdapter;
import android.widget.ImageView;
import android.widget.TextView;
import android.widget.Toast;

public class CustomAdapter extends BaseAdapter {
    String[] result;
    Context context;
    int[] imageId;
    String[] empty;
    private static LayoutInflater inflater = null;
    private View imageImageView, imageTextView;
    private int index = 0;

    public CustomAdapter(MainActivity mainActivity, String[] prgmNameList, int[] prgmImages, String[] array) {
        result = prgmNameList;
        context = mainActivity;
        imageId = prgmImages;
        empty = array;
        inflater = (LayoutInflater) context.getSystemService(Context.LAYOUT_INFLATER_SERVICE);
    }

    @Override
    public int getCount() {
        // TODO Auto-generated method stub
        return result.length;
    }

    @Override
    public Object getItem(int position) {
        // TODO Auto-generated method stub
        return position;
    }

    @Override
    public int getItemViewType(int position) {
        // Define a way to determine which layout to use, here it's just evens and odds.
        return position;
    }

    //    @Override
//    public int getViewTypeCount() {
//        return 2; // Count of different layouts
//    }
    @Override
    public long getItemId(int position) {
        // TODO Auto-generated method stub
        return position;
    }

//    @Override
//    public View getView(int position, View convertView, ViewGroup parent) {
//        return null;
//    }

    public class Holder {
        TextView tv;
        ImageView img;
        ImageView img1;
        ImageView img2;
    }

    @Override
    public View getView(int position, View convertView, ViewGroup parent) {
        // TODO Auto-generated method stub
//        Holder holder=new Holder();
        View rowView;

        Holder holder = null;


        holder = new Holder();
        if (position % 2 == 0) {

            convertView  = inflater.inflate(R.layout.item_listview, null);


            /*holder.img2 = (ImageView) convertView.findViewById(R.id.imageView1);
            holder.img1 = (ImageView) convertView.findViewById(R.id.apple);*/


            // holder.img2.setImageResource(imageId[position]);
//                  holder.img1.setImageResource(imageId[position]);
        } else { // must be INPROCESS_TYPE_INDEX
             convertView  = inflater.inflate(R.layout.item_listview_1, null);

            holder.tv = (TextView) convertView.findViewById(R.id.textView1);
            holder.img = (ImageView) convertView.findViewById(R.id.imageView3);
            //holder.tv.setText(empty[position]);
            holder.tv.setText(result[position/2]);
            // holder.img.setImageResource(imageId[position]);


        }
//                convertView.setTag(holder);

//            thisOrder = (Order) myOrders.getOrderList().get(position);
        // If using different views for each type, use an if statement to test for type, like above

        return convertView;

//        if(position%2==0){
//            rowView = inflater.inflate(R.layout.item_listview, null);
//            holder.img1=(ImageView) rowView.findViewById(R.id.imageView2);
//            holder.img=(ImageView) rowView.findViewById(R.id.imageView1);
//            holder.img.setImageResource(imageId[position]);
//            holder.img1.setImageResource(imageId[position]);
//        }
//
//            rowView = inflater.inflate(R.layout.item_listview_1, null);
//            holder.tv=(TextView) rowView.findViewById(R.id.textView1);
//            holder.img=(ImageView) rowView.findViewById(R.id.imageView3);
//            holder.tv.setText(result[position]);
//            holder.img.setImageResource(imageId[position]);


//        rowView.setOnClickListener(new OnClickListener() {
//            @Override
//            public void onClick(View v) {
//                // TODO Auto-generated method stub
//                Toast.makeText(context, "You Clicked "+result[position], Toast.LENGTH_LONG).show();
//            }
//        });
//        return rowView;
    }

}
