import	androidx.appcompat.app.AppCompatActivity;
import	android.os.Bundle;
import	android.view.View;
import	android.widget.Button;
import	android.widget.EditText;
import	android.widget.TextView;
public class MainActivity extends AppCompatActivity
{
    @Override
    protected	void	onCreate(Bundle	savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        EditText editTextKisaKenar = findViewById(R.id.editTextKisaKenar);
        EditText editTextUzunKenar = findViewById(R.id.editTextUzunKenar);
        Button buttonKareAlani	= findViewById(R.id.buttonKareAlani);
        Button buttonDikdortgenAlani = findViewById(R.id.buttonDikdortgenAlani);
        TextView textViewAlan = findViewById(R.id.textViewAlan);
        buttonKareAlani.setOnClickListener(new View.OnClickListener()
        {
            @Override
            public void onClick(View view)
            {
                Integer	kenar;
                Integer	alan;
                kenar=Integer.parseInt(editTextKisaKenar.getText().toString());
                Dortgen kare = new	Dortgen(kenar);
                alan = kare.alanBul();
                textViewAlan.setText(alan.toString());
            }
        });
        buttonDikdortgenAlani.setOnClickListener(new View.OnClickListener()
        {
            @Override
            public void onClick(View view)
            {
                Integer	kisaKenar;
                Integer	uzunKenar;
                Integer	alan;

                kisaKenar = Integer.parseInt(editTextKisaKenar.getText().toString());
                uzunKenar = Integer.parseInt(editTextUzunKenar.getText().toString());

                Dortgen	dikdortgen = new Dortgen(kisaKenar,uzunKenar);
                textViewAlan.setText(dikdortgen.toString());
            }
        });
    }
}








public class Dortgen
{

    public	Integer	kisaKenar;
    public	Integer	uzunKenar;

    public	Integer	alanBul()
    {
        Integer	alan;
        alan = kisaKenar * uzunKenar;
        return	alan;
    }
}






<LinearLayout
        android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:orientation="vertical"
    app:layout_constraintBottom_toBottomOf="parent"
    app:layout_constraintEnd_toEndOf="parent"
    app:layout_constraintStart_toStartOf="parent"
    app:layout_constraintTop_toTopOf="parent">

    <EditText
        android:id="@+id/editTextKisaKenar"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:hint="Kısa	Kenar"
        android:inputType="number"
        tools:layout_editor_absoluteX="40dp"
        tools:layout_editor_absoluteY="258dp" />

    <EditText
        android:id="@+id/editTextUzunKenar"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:hint="Uzun	Kenar"
        android:inputType="number"
        tools:layout_editor_absoluteX="40dp"
        tools:layout_editor_absoluteY="180dp" />

        <Button
            android:id="@+id/buttonKareAlani"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Kare	Alanı"	/>
        <Button
            android:id="@+id/buttonDikdortgenAlani"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Dikdörtgen	Alanı"/>
        <TextView
            android:id="@+id/textViewAlan"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Alan"/>
    </LinearLayout>
