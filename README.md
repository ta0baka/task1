# Лабораторная работа №1. Создание activity и передача параметров между ними
Код приложения написан на языке Java и использует Android SDK.

## Инструкция по использованию приложения
1. Запустите приложение.
2. На первой `activity` нажмите на кнопку `btn1`.
3. На второй `activity` будет отображен переданный параметр в виде текста.
<p align="center">
<img src="https://github.com/user-attachments/assets/92b11613-753c-4403-be3c-d601d635fb03" width="250" height="500"> <img src="https://github.com/user-attachments/assets/7d600af7-6b87-428a-8ebe-3019893b74e3" width="250" height="500">
</p>

## Передача параметра
Передача параметра между двумя `activity` реализована с помощью `Intent` и метода `PutExtra`. На первой `activity` создается `Intent` с параметром, который передается во вторую `activity`.
```java
// Первая activity
public void onClick(View v) {
     Intent intent = new Intent(MainActivity.this, MainActivity2.class);
     intent.putExtra("surname", "Новикова");
     startActivity(intent);
}

// Вторая activity
protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main2);
        String surname = getIntent().getStringExtra("surname");
        TextView textView = findViewById(R.id.textView);
        textView.setText(surname);
    }
