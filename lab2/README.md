# **Лабораторна робота №2**

-----------------------------------
## Необхідні ресурси:
- Встановлений компілятор для Python.

## Інформація про програму:
- Виводить в терміналі "Hello World!".
- Виконує команди: ping, echo, login, list, msg, file, exit.

## Опис Команд:
### 1. Команда `ping <Address: String>`.
#### Ця команда перевіряє зєднання з сервером, сайтом чи будь-яким іншим пристроєм за вказаною IP або DNS адресою. Дані команді передається тільки один параметр - `<Address: String>`
#### Результатом виконання у разі успішного зєднання в першому рядку записується `Ping <Address: String> ...` і в наступному рядку `Ping <Address: String> request success.`.
#### Якщо ж кількість введених параметрів не буде рівна "1", то замість результату виводиться повідомлення з описом помилки в дужках`PING ERROR (Incorect input argument)`

### Приклад виконання команди:
```text
= RESTART: C:\Users\GAIVER74\Documents\GitHub\distributed-systems\lab2\Lab2.py =
Hello World!
========================================
Input Command: ping github.com
Entered command = "ping", parameters = ['github.com']
----------------------------------------

Results:
Ping github.com ...
Ping github.com request success.
========================================
Input Command: ping 192.168.0.0
Entered command = "ping", parameters = ['192.168.0.0']
----------------------------------------

Results:
Ping 192.168.0.0 ...
Ping 192.168.0.0 request success.
========================================
Input Command: ping
Entered command = "ping", parameters = []
----------------------------------------

Results:
PING ERROR (Incorect input argument)
```

### 2. Команда `echo <anyText: String> <anyText: String> ...`.
#### Ця команда виводить на екрані текст з вхідних параметрів - `<anyText: String>`. Ця команда може отримувати будь-яку кількість параметрів. Кожний параметр відображається в новому рядку.

### Приклад виконання команди:
```text
C:\Users\GAIVER74\Documents\GitHub\distributed-systems\lab2\Lab2.py ===========================================
Hello World!
========================================
Input Command: echo period
Entered command = "echo", parameters = ['period']
----------------------------------------

Results:
period
========================================
Input Command: echo period incorrect
Entered command = "echo", parameters = ['period', 'incorrect']
----------------------------------------

Results:
period
incorrect
========================================
Input Command: echo "period incorrect"
Entered command = "echo", parameters = ['period incorrect']
----------------------------------------

Results:
period incorrect
```

### 3. Команда `login <login: String> <password: String>`.
#### Ця команда дозволяє користувачу залогінитися. Дані команді передається два параметри - `<login: String>` і `<password: String>`.
#### Результатом виконання команди буде:
- Якщо логін даного користувача немає в базі даних, то в консолі виводиться `LOGIN ERROR (Incorect input login or password)`.
- Якщо логін даного користувача є в базі даних, але відповідний до нього пароль введений неправильно, то в консолі виводиться `LOGIN ERROR (Incorect input login or password)`.
- Якщо логін даного користувача є в базі даних, і відповідний до нього пароль введений правильно, то в першому рядку консолі виводиться - `LOGIN SUCCESS:`, а в наступному рядку - `Hello, <nameUsers: String>`.
- Якщо кількість введених параметрів не дорівнює 2, то в консолі виводиться `LOGIN ERROR (Incorect input argument)`.

### Приклад виконання команди:
```text
C:\Users\GAIVER74\Documents\GitHub\distributed-systems\lab2\Lab2.py ===========================================
Hello World!
========================================
Input Command: login Burachok_std std204
Entered command = "login", parameters = ['Burachok_std', 'std204']
----------------------------------------

Results:
LOGIN SUCCESS:
 Hello, Burachok
========================================
Input Command: login Sidorov_std i don`t wish to exist
Entered command = "login", parameters = ['Sidorov_std', 'i', 'don`t', 'wish', 'to', 'exist']
----------------------------------------

Results:
LOGIN ERROR (Incorect input argument)
========================================
Input Command: login miamoto
Entered command = "login", parameters = ['miamoto']
----------------------------------------

Results:
LOGIN ERROR (Incorect input argument)
========================================
Input Command: login musashi Options !nco44ect
Entered command = "login", parameters = ['musashi', 'Options', '!nco44ect']
----------------------------------------

Results:
LOGIN ERROR (Incorect input argument)
```

### 4. Команда `list`.
#### Ця команда виводить на екран список назв всіх зареєстрованих користувачів які знаходяться в базі даних. Для цієї команди не потрібно вводити параметри, якщо було введено параметри то вони ігноруються. Назва кожного користувача відображається в новому рядку з його поряковим номером - `<№Users: Int>. <nameUsers: String>` .
#### База даних:
- user_names = ['Bogdan', 'Yuriy', 'Sidorov', 'Burachok']
- user_logins = ['Bogdan_std', 'Yuriy_std', 'Sidorov_std', 'Burachok_std']
- user_passwords = ['std201', 'std202', 'std203', 'std204']

### Приклад виконання команди:
```text
C:\Users\GAIVER74\Documents\GitHub\distributed-systems\lab2\Lab2.py ===========================================
Hello World!
========================================
Input Command: list
Entered command = "list", parameters = []
----------------------------------------

Results:
1. Bogdan
2. Yuriy
3. Sidorov
4. Burachok
========================================
Input Command: list lab
Entered command = "list", parameters = ['lab']
----------------------------------------

Results:
1. Bogdan
2. Yuriy
3. Sidorov
4. Burachok
```

### 5. Команда `msg <destinationUser: String> <text: String>`.
#### Ця команда надсилає текстове повідомлення іншому користувачу. Дані команді передається два параметри - `<destinationUser: String>` і ` <text: String>`.
#### Результатом виконання команди буде:
- Якщо назви даного користувача немає в базі даних, то в консолі виводиться `MESSAGE SENDING ERROR (This user not found)`.
- Якщо назва даного користувача є в базі даних, то в консолі виводиться `MESSAGE SENDING SUCCESS`.
- Якщо кількість введених параметрів не дорівнює 2, то в консолі виводиться `MESSAGE SENDING ERROR (Incorect input argument)`.

### Приклад виконання команди:
```text
C:\Users\GAIVER74\Documents\GitHub\distributed-systems\lab2\Lab2.py ===========================================
Hello World!
========================================
Input Command: msg Bogdan 'lab2 Hello'
Entered command = "msg", parameters = ['Bogdan', 'lab2 Hello']
----------------------------------------

Results:
MESSAGE SENDING SUCCESS
========================================
Input Command: msg Sidorov "No Name"
Entered command = "msg", parameters = ['Sidorov', 'No Name']
----------------------------------------

Results:
MESSAGE SENDING SUCCESS
========================================
Input Command: msg miamoto "No Name"
Entered command = "msg", parameters = ['miamoto', 'No Name']
----------------------------------------

Results:
MESSAGE SENDING ERROR (This user not found)
========================================
Input Command: msg Yuriy
Entered command = "msg", parameters = ['Yuriy']
----------------------------------------

Results:
MESSAGE SENDING ERROR (Incorect input argument)
```

### 6. Команда `file <destinationUser: String> <filename: String>`.
#### Ця команда надсилає файлове повідомлення іншому користувачу. Дані команді передається два параметри - `<destinationUser: String>` і ` <filename: String>`.
#### Результатом виконання команди буде:
- Якщо назви даного користувача немає в базі даних, то в консолі виводиться `FILE SENDING ERROR (User not found)`.
- Якщо назва даного користувача є в базі даних, але даного файлу немає, то в консолі виводиться `FILE SENDING ERROR (File not found)`.
- Якщо назва даного користувача є в базі даних, і цей файл існує, то в консолі виводиться `FILE SENDING SUCCESS`.
- Якщо кількість введених параметрів не дорівнює 2, то в консолі виводиться `FILE SENDING ERROR (Incorect input argument)`.

### Приклад виконання команди:
```text
C:\Users\GAIVER74\Documents\GitHub\distributed-systems\lab2\Lab2.py ===========================================
Hello World!
========================================
Input Command: file Burachok README.md
Entered command = "file", parameters = ['Burachok', 'README.md']
----------------------------------------

Results:
FILE SENDING SUCCESS
========================================
Input Command: file Sidorov laboratorka
Entered command = "file", parameters = ['Sidorov', 'laboratorka']
----------------------------------------

Results:
FILE SENDING ERROR (File not found)
========================================
Input Command: file miamoto lab2.py
Entered command = "file", parameters = ['miamoto', 'lab2.py']
----------------------------------------

Results:
FILE SENDING ERROR (User not found)
========================================
Input Command: file SCHMETERLING!
Entered command = "file", parameters = ['SCHMETERLING!']
----------------------------------------

Results:
FILE SENDING ERROR (Incorect input argument)
```

### 7. Команда `exit`.
#### Ця команда виходить з циклу для опитування введення команд. Для цієї команди не потрібно вводити параметри, якщо було введено параметри то вони ігноруються.
- Результатом виконання команди буде - `Exit from cycle`

### Приклад виконання команди:
```text
C:\Users\GAIVER74\Documents\GitHub\distributed-systems\lab2\Lab2.py ===========================================
Hello World!
========================================
Input Command: list
Entered command = "list", parameters = []
----------------------------------------

Results:
1. Bogdan
2. Yuriy
3. Sidorov
4. Burachok
========================================
Input Command: exit SZMATA
Entered command = "exit", parameters = ['SZMATA']
----------------------------------------

Results:
Exit from cycle
>>> 
============================================ RESTART: C:\Users\GAIVER74\Documents\GitHub\distributed-systems\lab2\Lab2.py ===========================================
Hello World!
========================================
Input Command: list
Entered command = "list", parameters = []
----------------------------------------

Results:
1. Bogdan
2. Yuriy
3. Sidorov
4. Burachok
========================================
Input Command: exit
Entered command = "exit", parameters = []
----------------------------------------

Results:
Exit from cycle
```

### Примітка: щоб ввести текст в якому містяться символ " " потрібно використовувати адинарні або подвійні дужки в кінці і на початку тексту.
### Примітка: Якщо було некоректно введено команду або її не існує, то в консолі виводиться `No Command = "<comand>"`.

### Приклад спроби виконання іншої команди:
```text
C:\Users\GAIVER74\Documents\GitHub\distributed-systems\lab2\Lab2.py ===========================================
Hello World!
========================================
Input Command: KURWA
Entered command = "KURWA", parameters = []
----------------------------------------

Results:
No Command = "KURWA"
========================================
Input Command: I don`t wanna kill myself anymore
Entered command = "I", parameters = ['don`t', 'wanna', 'kill', 'myself', 'anymore']
----------------------------------------

Results:
No Command = "I"
```
