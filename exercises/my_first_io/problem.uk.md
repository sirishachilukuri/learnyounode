Напишіть програму, яка **синхронно** читає файл та виводить кількість рядків (\n), котрі містяться у файлі, точно так само, як би це зробила команда `cat file | wc -l`.

Повний шлях до файлу буде переданий у якості першого аргументу командного рядка. Вам не варто створювати тестовий файл самостійно.

----------------------------------------------------------------------
## ІНФОРМАЦІЯ

Щоб прочитати файл Вам знадобиться модуль `fs` із вбудованої бібліотеки Node. Щоб завантажити цей, або будь-який інший "глобальний модуль", скористайтесь наступною командою:

```js
var fs = require('fs')
```

Таким чином весь модуль `fs` буде доступний через змінну `fs`.

Всі синхронні (або блокуючі) методи файлової системи в модулі `fs` закінчуються на 'Sync'. Щоб прочитати файл, Вам знадобиться `fs.readFileSync('/path/to/file')`. Цей метод *поверне* об’єкт типу `Buffer`, котрий міститиме весь контент файлу.

Документація до модуля `fs` ви зможете знайти, перейшовши у вашому браузері сюди:
  {rootdir:/node_apidoc/fs.html}

Об’єкти типу `Buffer` використовуються Node.js для ефективного представлення масивів данних, будь то ascii, бінарний або будь-який інший формат. Об’єкти `Buffer` можуть бути конвертованими в рядок шляхом виклику методу `toString()` над ними, наприклад, `var str = buf.toString()`.

Документацію для `Buffer` Ви можете знайти, набравши у браузері:
  {rootdir:/node_apidoc/buffer.html}

Якщо Ви шукаєте простий спосіб порахувати кількість рядків у файлі, то Ви можете скористатись `.split()` з роздільником '\n' для розбиття цього рядка на масив підрядків. Зауважте, що текстовий файл містить символ ('\n') в кінці останнього рядка, таким чином Ви отримаєте масив, котрий містить на один елемент більше, ніж число рядків у файлі.

----------------------------------------------------------------------
