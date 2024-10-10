<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity"
    android:orientation="vertical"
    android:layout_margin="10dp"
    >

    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Calculadora do perimetro e da área "
        android:textSize="25sp"
         />

<LinearLayout
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:orientation="horizontal"
    >
    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        >
    <TextView
        android:layout_width="184dp"
        android:layout_height="38dp"
        android:text="largura A"
        android:textSize="25sp"
        tools:layout_editor_absoluteX="41dp"
        tools:layout_editor_absoluteY="73dp" />

    <EditText
        android:id="@+id/larguraA"
        android:layout_width="147dp"
        android:layout_height="48dp"
        tools:layout_editor_absoluteX="41dp"
        tools:layout_editor_absoluteY="84dp" />
    </LinearLayout>
    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        >

    <TextView
        android:layout_width="184dp"
        android:layout_height="38dp"
        android:text="largura B"
        android:textSize="25sp"
        tools:layout_editor_absoluteX="233dp"
        tools:layout_editor_absoluteY="73dp" />

    <EditText
        android:id="@+id/larguraB"
        android:layout_width="147dp"
        android:layout_height="48dp"
        tools:layout_editor_absoluteX="233dp"
        tools:layout_editor_absoluteY="84dp" />

    </LinearLayout>
</LinearLayout>
    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        >
        <LinearLayout
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:orientation="vertical"
            >
    <TextView
        android:layout_width="184dp"
        android:layout_height="38dp"
        android:text="Altura A"
        android:textSize="25sp"
        tools:layout_editor_absoluteX="41dp"
        tools:layout_editor_absoluteY="153dp"

        />

    <EditText
        android:id="@+id/AlturaA"
        android:layout_width="147dp"
        android:layout_height="48dp"
        tools:layout_editor_absoluteX="41dp"
        tools:layout_editor_absoluteY="165dp" />
        </LinearLayout>
        <LinearLayout
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:orientation="vertical"
            >
    <TextView
        android:layout_width="184dp"
        android:layout_height="38dp"
        android:text="Altura B"
        android:textSize="25sp"
        tools:layout_editor_absoluteX="233dp"
        tools:layout_editor_absoluteY="153dp" />

        <EditText
            android:id="@+id/AlturaB"
            android:layout_width="147dp"
            android:layout_height="48dp"
            tools:layout_editor_absoluteX="233dp"
            tools:layout_editor_absoluteY="165dp" />

</LinearLayout>
    </LinearLayout>
    <LinearLayout
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        >
        <LinearLayout
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:orientation="vertical"
            >
    <TextView
        android:layout_width="184dp"
        android:layout_height="38dp"
        android:text="Perimetro"
        android:textSize="25sp"
        android:layout_marginBottom="2dp"
        tools:layout_editor_absoluteX="41dp"
        tools:layout_editor_absoluteY="236dp" />


            <TextView
                android:id="@+id/tvPerimetro"
                android:layout_width="160dp"
                android:layout_height="wrap_content" />

        </LinearLayout>
        <LinearLayout
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:orientation="vertical"
            >
        <TextView
        android:layout_width="184dp"
        android:layout_height="38dp"
        android:text="Àrea"
        android:textSize="25sp"
        android:layout_marginBottom="2dp"
        tools:layout_editor_absoluteX="41dp"
        tools:layout_editor_absoluteY="296dp" />

           <TextView
                android:id="@+id/tvArea"
                android:layout_width="160dp"
                android:layout_height="wrap_content" />


        </LinearLayout>
    </LinearLayout>

    <Button
        android:id="@+id/calcular"
        android:layout_width="359dp"
        android:layout_height="106dp"
        android:text="Calcular"
        android:textSize="25dp"></Button>
</LinearLayout>




package com.example.xms;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

import androidx.activity.EdgeToEdge;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.graphics.Insets;
import androidx.core.view.ViewCompat;
import androidx.core.view.WindowInsetsCompat;

public class MainActivity extends AppCompatActivity {

    private TextView Tvarea,TvPerimetro;
    private EditText larguraA,larguraB,alturaA, alturaB;
    private Button calcular;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        EdgeToEdge.enable(this);
        setContentView(R.layout.activity_main);
        ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main), (v, insets) -> {
            Tvarea = findViewById(R.id.tvArea);
            TvPerimetro = findViewById(R.id.tvPerimetro);
            larguraA = findViewById(R.id.larguraA);
            larguraB =  findViewById(R.id.larguraB);
            alturaA = findViewById(R.id.AlturaA);
            alturaB = findViewById(R.id.AlturaB);
            calcular = findViewById(R.id.calcular);

            calcular.setOnClickListener(new View.OnClickListener() {
                           @Override
                         public void onClick(View view) {
                       double largura = (Double.parseDouble(larguraA.getText().toString() ) + Double.parseDouble(larguraB.getText().toString()))

                       double altura = (Double.parseDouble(alturaA.getText().toString() ) + Double.parseDouble(alturaB.getText().toString()))

                               double perimetro =(largura*2) + (altura*2);
                       double area = (largura * altura);

                       TvPerimetro.setText(String.valueOf(perimetro);
                       Tvarea.setText(String.valueOf(area);

                                                           }
                                        });


                    Insets systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars());
            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom);
            return insets;
        });
    }
}
