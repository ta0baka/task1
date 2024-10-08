# Лабораторная работа №1. Создание activity и передача параметров между ними
Код приложения написан на языке Java и использует Android SDK.
## Описание приложения
В этом приложении реализована передача параметра между двумя activity. На первой activity есть кнопка, при нажатии на которую на вторую activity передается параметр и открывается вторая activity, на которой текстом отображен переданный параметр.
## Использование приложения
1. Запустите приложение.
2. На первой activity нажмите на кнопку "Передать параметр".
3. На второй activity будет отображен переданный параметр в виде текста.

## Передача параметра
Передача параметра между двумя activity реализована с помощью Intent. На первой activity создается Intent с параметром, который передается во вторую activity.
```java
// Первая activity
public class MainActivity extends AppCompatActivity {
    public void onClickButton(View view) {
        Intent intent = new Intent(this, SecondActivity.class);
        intent.putExtra("parameter", "Значение параметра");
        startActivity(intent);
    }
}
