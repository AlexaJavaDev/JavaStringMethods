# Проверка регистра: методы isUpperCase и isLowerCase

В этом примере я показываю, как проверить, весь ли текст написан в верхнем или нижнем регистре,  
используя методы `Character.isUpperCase()` и `Character.isLowerCase()`.

---

## Код

```java
public class CaseCheckMethods {
    public static void main(String[] args) {
        String text1 = "HELLO";
        String text2 = "hello";
        String text3 = "Hello";
        String text4 = "HELLO123";

        System.out.println("Текст: " + text1);
        System.out.println("Весь в верхнем регистре? " + isUpperCase(text1));
        System.out.println("Весь в нижнем регистре? " + isLowerCase(text1));
        System.out.println("---");

        System.out.println("Текст: " + text2);
        System.out.println("Весь в верхнем регистре? " + isUpperCase(text2));
        System.out.println("Весь в нижнем регистре? " + isLowerCase(text2));
        System.out.println("---");

        System.out.println("Текст: " + text3);
        System.out.println("Весь в верхнем регистре? " + isUpperCase(text3));
        System.out.println("Весь в нижнем регистре? " + isLowerCase(text3));
        System.out.println("---");

        System.out.println("Текст: " + text4);
        System.out.println("Весь в верхнем регистре? " + isUpperCase(text4));
        System.out.println("Весь в нижнем регистре? " + isLowerCase(text4));
    }

    public static boolean isUpperCase(String str) {
        for (int i = 0; i < str.length(); i++) {
            char c = str.charAt(i);
            if (Character.isLetter(c) && !Character.isUpperCase(c)) {
                return false;
            }
        }
        return true;
    }

    public static boolean isLowerCase(String str) {
        for (int i = 0; i < str.length(); i++) {
            char c = str.charAt(i);
            if (Character.isLetter(c) && !Character.isLowerCase(c)) {
                return false;
            }
        }
        return true;
    }
}
```

### Вывод в консоли
```
Текст: HELLO
Весь в верхнем регистре? true
Весь в нижнем регистре? false
---
Текст: hello
Весь в верхнем регистре? false
Весь в нижнем регистре? true
---
Текст: Hello
Весь в верхнем регистре? false
Весь в нижнем регистре? false
---
Текст: HELLO123
Весь в верхнем регистре? true
Весь в нижнем регистре? false
```
---

### Как это работает
- `Character.isUpperCase(char c)` — проверяет, является ли символ заглавной буквой
- `Character.isLowerCase(char c)` — проверяет, является ли символ строчной буквой
- `Character.isLetter(char c)` — проверяет, является ли символ буквой (игнорирует цифры и знаки)

### Логика проверки:
1. Проходим по каждому символу строки
2. Если находим букву, которая не соответствует нужному регистру → возвращаем `false`
3. Если все буквы подходят → возвращаем `true`

---

### Важные моменты
1. Методы проверяют только буквы
2. Цифры (123) и пробелы игнорируются
3. Если в строке есть буквы разных регистров → оба метода вернут `false`

### Мои заметки
- `Character.isLetter()` — полезен, чтобы игнорировать цифры и знаки
- `Character.isUpperCase()` и `isLowerCase()` — работают только с буквами
- Этот пример помогает проверять пароли или имена пользователей на регистр

---

⭐ Теперь я умею проверять регистр строк и определять, весь ли текст в верхнем или нижнем регистре.
