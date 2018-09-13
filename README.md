# PreWork
Android App Gif
package e.jnac.hellojasmine;

import android.annotation.SuppressLint;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.text.TextUtils;
import android.util.Log;
import android.view.View;
import android.widget.EditText;
import android.widget.TextView;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        findViewById(R.id.button).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                ((TextView) findViewById(R.id.textView)).setTextColor(
                        getResources().getColor(R.color.colorPrimaryDark));
            }
        });

        findViewById(R.id.button2).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                findViewById(R.id.rootView).setBackgroundColor(
                        getResources().getColor(R.color.red));
            }
        });

        findViewById(R.id.button3).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                //grab the text the user inputted
               String newText = ((EditText) findViewById(R.id.editText)).getText().toString();

               if (TextUtils.isEmpty(newText)) {
                   ((TextView) findViewById(R.id.textView)).setText("Hello from Jasmine!");
                   } else {
                   ((TextView) findViewById(R.id.textView)).setText(newText);
               }
                //put the text into our view once the 'change text' button is clicked
            }
        });

            findViewById(R.id.rootView).setOnClickListener(new View.OnClickListener() {
                @Override
                public void onClick(View v) {
                    //reset the text color back to black
                    ((TextView) findViewById(R.id.textView)).setTextColor(
                            getResources().getColor(R.color.black));

                    //reset the background color colorAccent
                    findViewById(R.id.rootView).setBackgroundColor(getResources().getColor(R.color.colorAccent));

                    //reset the text back to 'Hello from Jasmine'
                    ((TextView) findViewById(R.id.textView)).setText("Hello from Jasmine!");
                }
            });


    }
}
