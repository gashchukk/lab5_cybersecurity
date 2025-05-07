# Cybersecurity Web App

## Налаштування Мережі

Спершу портібно налаштувати Kali на NAT Network , а Alpine - Host Only

![image.png](images/image.png)

![image.png](images/image%201.png)

Далі, потрібно налаштувати CHR так, щоб між ними звявився конешн. Для цього необіхдно використати наступні команди:

![image.png](images/image%202.png)

![image.png](images/image%203.png)

Як можете бачити, сетап відбувся успішно, і вони між собою пінгуються

![image.png](images/image%204.png)

Ось я знайшов сторінку, яка є нашою ціллю

![image.png](images/image%205.png)

Далі потрібно підібрати логін та пароль.

Я взяв 6 найтиповіших користувачів, та взяв вибірку паролів з минулих лаб, але відсіяв всі що менші за 8 символів

![image.png](images/image%206.png)

Для підбору я використав знайому вже мені `hydra` ось такою командою:

```jsx
hydra -L ./usernames.txt -P ./passwords0-20000.txt 192.168.56.12 http-post-form '/login.php:username=^USER^&password=^PASS^&wp-submit=Log+In:F=Invalid username'
```

![image.png](images/image%207.png)

![image.png](images/image%208.png)