# api_final
 =======
 ### О чем проект:
 Социальная сеть реализованная на API
 Позволяет быстро и удобно создавать информационные посты о ЛЮБЫХ вещях (и даже можно прикрутить картиночку....ВОУ!)
 Можно вступать в группы по интересам и !КОММЕНТИРОВАТЬ! понравившиеся посты
 В последнем обновлении была добавлена ПОДПИСКА!....Да-да, вы не ослышались! Можно подписаться на определенного автора и следить за его постами!
 Вы ещё не зарегистрированы?! Тогда быстрее присоединяйтесь! Нас уже.....кхе.....много :)

 ### Как запустить проект:

 Клонировать репозиторий и перейти в него в командной строке:
 ```
 git clone https://github.com/Ghibliliker/api_final_yatube.git
 cd api_final_yatube
 ```
 Cоздать и активировать виртуальное окружение:
 ```
 python3 -m venv venv
 source venv/bin/activate
 ```
 Установить зависимости из файла requirements.txt:
 ```
 python3 -m pip install --upgrade pip
 pip install -r requirements.txt
 ```
 Выполнить миграции:
 ```
 python3 manage.py migrate
 ```
 Запустить проект:
 ```
 python3 manage.py runserver
 ```
 ### Пример запросов к API:

 * GET     /api/v1/posts/                                  Получение публикаций  
 * POST    /api/v1/posts/                                  Создание публикации
 ```        
 {
 "text": "string",
 "image": "string",
 "group": 0
 }
 ```
 * GET     /api/v1/posts/{id}/                             Получение публикации по id
 * PUT     /api/v1/posts/{id}/                             Обновление публикации по id
 * PATCH   /api/v1/posts/{id}/                             Частичное обновление публикации по id
 * DEL     /api/v1/posts/{id}/                             Удаление публикации по id
 * GET     /api/v1/posts/{post_id}/comments/               Получение всех комментариев к публикации
 * POST    /api/v1/posts/{post_id}/comments/               Добавление нового комментария к публикации
 ```
 {
 "text": "string"
 }
 ```
 * GET     /api/v1/posts/{post_id}/comments/{id}/          Получение комментария к публикации по id
 * PUT     /api/v1/posts/{post_id}/comments/{id}/          Обновление комментария к публикации по id
 * PATCH   /api/v1/posts/{post_id}/comments/{id}/          Частичное обновление комментария к публикации по id
 * DEL     /api/v1/posts/{post_id}/comments/{id}/          Удаление комментария к публикации по id
 * GET     /api/v1/groups/                                 Получение списка доступных сообществ
 * GET     /api/v1/groups/{id}/                            Получение информации о сообществе по id
 * GET     /api/v1/follow/                                 Возвращает все подписки пользователя, сделавшего запрос
 * POST     /api/v1/follow/                                Подписка пользователя от имени которого сделан запрос на пользователя переданного в теле запроса
 ```
 {
 "following": "string"
 }
 ```
 * POST    /api/v1/jwt/create/                             Получение JWT-токена
 * POST    /api/v1/jwt/refresh/                            Обновление JWT-токена
 * POST    /api/v1/jwt/verify/                             Проверка JWT-токена
