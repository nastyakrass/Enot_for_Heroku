# Enot_for_Heroku

# Telebot
Асинхронный Телебот: 
**@Enotuskabot (Heroku) 
@Enotyabot (Colab) -- его клон для Колаба**

***

У нас есть асинхронный бот @Enotuskabot / @Enotyabot (файл bot.py), построенный с помощью фреймворка Telebot  и осуществляющий перенос стиля и улучшение фотографий.

У бота также есть дополнительная команда "Узнай у ученого Еноти", благодаря которой пользователь может задать ученому Боту Еноту любой вопрос и получить 3 самые актуальные  ссылки с ответами.

Пока осуществляется перенос стиля, можно читать информацию по этим ссылкам и самообразовываться :))

(Также у бота есть команды "Начать разговор сначала", "Помощь Полоскуна", которые облегчают работу)

Бот может устанавливать размер изоражений и переносить стиль  следующими способами:

1. Перенос одного стиля на изображение

2. Перенос двух стилей с использованием маски -- доступно 4 типа масок (см.папку Masks)

3. Одновременный перенос двух стилей на изображение.

В этой части проекта я использую собственный нейросетевой класс  (см. файл styletransfer.py; базовая сеть -- VGG-19)

Также бот умеет применять к картинкам, которые он предварительно сжимает для более наглядного результата, операцию Супер Резолюции.

Здесь я использовала готовую предобученную сеть на Tensor Flow из проекта https://github.com/idealo/image-super-resolution

(**UPD**: Для более яркого результата лучше отправлять на Супер резолюцию (Forward-ом фото) те картинки (**крайне желательно, размера 256 на 256**), к которым бот уже применил перенос стиля 
-- получается довольно-таки эффектно и быстро)

Модель для NST изначально отлаживалась для работы на CPU: бот обрабатывает картинки размером 256 на 256 в течение 4 мин. (128 на 128 -- за 2 мин); с GPU он работает практически мгновенно.

Бот **@Enotuskabot** запущен на Heroku, но работает там небыстро, в ограниченном режиме (сложно тестировать асинхронность и т.п.); иногда валится; я бы рекомендовала тестировать локально / с использованием  Colab Notebook: https://colab.research.google.com/drive/1C9zF_Mdjlr3C5slqZ77LLNPzSPtKa6cL?usp=sharing

Скрпит на Колабе запустит бота **@Enotyabot** (предварительно открыть в Телеграме)

Проект докеризован и выложен на **DockerHub: nastyakrass/enotyar**. 

Зеленые галочки в левом верхнем углу, которые видны при просмотре файлов на Гитхабе, означают, что проект прошел проверку Докером и успешно собран

(**UPD1**: Все фото надо отравлять именно как фото, а не документ. Документы еноты не едят :-))

Мой телеграм для связи: **@nastya_krass**

