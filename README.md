## Що це?

З деякого часу в нашому проекті https://github.com/DmytroKorniienko/FireLamp_EmbUI з'явився плеєр анімацій.
В зв'язку з невеликою кількістю ресурсів у контролера esp8266, один з співавторів проекту https://github.com/80Stepko08 придумав формат файлів на базі однобайтного кодування кольору 332. Також плеэр пыдтримує двухбайтове кодування 565, а я написав плеєр під ці формати, з підримкою зуму та кропу, приклад коду для 233 тут https://editor.soulmatelights.com/gallery/1684-pgm-player-with-resize, а повну версію коду можна знайти в проекті лампи.
Для активації плеєра в проекті лампи потрібно в файлі user_config.h (зкопіювати user_config.h.default та переіменувавши в user_config.h покласти рядом з оригіналом, в подальшому використовувати саме його для кастомізації налаштувань проекту) внести запис #define RGB_PLAYER. Після збірки та прошивки проекта в контролер, плеєр буде доступним як ефект номер 251. 
Треба мати на увазі, що об'єм ФС в контролері не великий, до того ж ФС використовується ще й для запису конфігураційних файлів ефектів, подій, копій ефектів і т.п. Тому контролюйте свобідний простір ФС в випливаючому меню в webUI лампи, та не добавляйте велику кількість анимацій, займаючи весь доступний простір.
Анімаційні файли, після конвертації будуть мати назву + розширення .565 або 332, в залежності від опції, вибраної під час конвертації.
Файли анімації, до прошивки, поміщати в папку проекту лампы /FireLamp_Embui/DATA/Animations/
Також файлы можна помістити в цю папку і після прошивки, активувавши сервер FTP в лампі (налаштування), та підключившись до лампи за допомогою скажімо WinSCP, або іншого FTP-клієнта, на ваш вибір. Підтримуються всі файлові операції, в тому числі копіювання, переіменування та видалення файлів в ФС лампи.

В цьому репозиторії зберігаються знайдені на просторах інтернету гиф файли, які більш-менш добре виглядають на лампі (краще звичайно панелі). 

Хоча плеєр і підтримує кроп та зум, але краще підготуйте файли відповідно рідному розрішенню LED-матриці вашої лампи\панелі, за допомогою онлайн-редактора (посилання в інструментах) 
