

# 🔄 Интеграция HH.ru → Bitrix24: Автоматизация рекрутинга
**Продакшен-решение для 600+ HR-команд**  
[![Bitrix24 App](https://img.shields.io/badge/Bitrix24_Marketplace-4.9/5⭐-00A2FF?logo=bitrix&logoColor=white)](https://www.bitrix24.ru/apps/app/21ek.integratsiya_s_hh_ru/)

## Архитектура системы
```mermaid
graph TD;
    HHru[HH.ru API] -->|HTTP Webhooks| WebhookService[Webhook Service];
    WebhookService -->|SQL| PostgreSQL[PostgreSQL];
    WebhookService -->|HTTP| BitrixAPI[Bitrix24 API];
    InterfaceService[Interface Service] -->|HTTP| BitrixAPI;
    InterfaceService -->|SQL| PostgreSQL;
    BitrixAPI -->|HTTP| Bitrix24[Bitrix24];
```
- ### HH.ru API
Внешний сервис, который отправляет вебхуки с данными об откликах на вакансии.
- ### Webhook Service
Микросервис, принимающий вебхуки от HH.ru, обрабатывающий данные отклика и отправляющий их в Bitrix24.
- ### Interface Service
Микросервис, предоставляющий интерфейс для приложения внутри Bitrix24, позволяющий загружать пользователей и получать данные о вакансиях.
- ### Bitrix24 API
API для взаимодействия с Bitrix24, через которое создаются отклики и выполняются другие операции.
- ### PostgreSQL
База данных для хранения настроек, привязок вакансий к порталам Bitrix24 и другой информации.

## Описание проекта

Проект заключается в интеграции сервиса **HeadHunter** с платформой **Bitrix24**. Эта интеграция обеспечивает удобную работу с резюме, полученными с портала hh.ru, непосредственно через CMS Bitrix, и наоборот.

### Основные функции интеграции:

1. **Работа с вакансиями:**
   - Назначение ответственного за вакансии.
   - Создание и выбор воронок в Bitrix24.
   - Создание и выбор смарт-процессов для вакансий.

2. **Импорт резюме:**
   - Расширение, позволяющее импортировать резюме из hh.ru в Bitrix24.

3. **Умные поля:**
   - Возможность создавать умные поля в Bitrix24, используя данные из HeadHunter.
   - Импорт полей в комментарии.

4. **Дополнительные функции:**
   - Отображение архивных вакансий с отключенным функционалом.
   - Показ полной информации о пользователях hh.ru и Bitrix24.
   - Авторизация на обоих порталах.
   - Кнопка для включения/выключения импорта резюме.
   - Генерация случайного кода для привязки расширения к HeadHunter.

### Особенности:

- Функционал к смарт-процессам доступен только при определенных тарифах.
- Возможность разлогиниться из системы.

Проект направлен на упрощение процесса работы с вакансиями и резюме, обеспечивая гладкую интеграцию между двумя важными платформами рекрутинга и управления задачами.


## Назначение проекта 🎯

Проект интеграции сервиса **HeadHunter** с платформой **Bitrix24** был создан с целью решения ряда ключевых проблем и удовлетворения конкретных потребностей в области управления человеческими ресурсами.

### Зачем был создан этот проект:

1. **Упрощение процесса рекрутинга** 💼:
   - Облегчение поиска и управления кандидатами, уменьшение времени на обработку резюме.

2. **Централизация рабочего процесса** 🌐:
   - Интеграция двух ключевых платформ обеспечивает единый рабочий интерфейс для HR-специалистов.

3. **Автоматизация рутинных задач** 🤖:
   - Автоматический импорт резюме и синхронизация данных между платформами сокращает время на рутинные операции.

4. **Повышение эффективности взаимодействия с вакансиями** 📈:
   - Легкий доступ к информации о вакансиях, управление кандидатами и воронками отбора в одном месте.

5. **Гибкость и масштабируемость** 🌟:
   - Решение адаптируется под разные бизнес-процессы и может масштабироваться в зависимости от нужд компании.

Проект призван оптимизировать процесс найма, улучшая взаимодействие между HR-отделом и потенциальными сотрудниками, а также обеспечивая более эффективное управление человеческими ресурсами.



## Галерея

![Изображение 1](screen11.png)
![Изображение 1](screen22.png)
![Изображение 1](screen33.png)
![Изображение 1](screen44.png)
![Изображение 1](screen5.png)
![Изображение 1](screen6.png)

...

## Моя роль в проекте
В моей роли в проекте заключалась ответственная задача разработки и планирования всей логики приложения. Мной была проведена тщательная работа по определению необходимого количества endpoint'ов, которые обеспечивали бы полный функционал приложения. Основываясь на этом, я разработал четкую логику и архитектуру backend-части.

Особое внимание в моей работе уделялось проектированию RESTful API, что позволило обеспечить гибкое и эффективное взаимодействие между клиентской и серверной частями приложения. Благодаря применению принципов REST, API стало удобным в использовании и масштабировании, а также обеспечило гарантированную совместимость с различными клиентскими приложениями.

Кроме того, я уделил значительное внимание разработке надежной системы авторизации. Это включало в себя как обеспечение безопасности пользовательских данных, так и разработку механизмов аутентификации и авторизации, согласно последним стандартам безопасности. Эти аспекты играли ключевую роль в обеспечении защищенности и надежности всей системы.

Моя работа над этим проектом включала не только непосредственное программирование, но и постоянное взаимодействие с командой, обеспечивая тем самым эффективное и гармоничное внедрение разработанных мной решений.

## Технологии, используемые в проекте

<img src="https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54" alt="Python" style="vertical-align:top; margin:4px">
<img src="https://img.shields.io/badge/flask-%23000.svg?style=for-the-badge&logo=flask&logoColor=white" alt="Flask" style="vertical-align:top; margin:4px">
<img src="https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white" alt="GitHub" style="vertical-align:top; margin:4px">
<img src="https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white" alt="Docker" style="vertical-align:top; margin:4px">
<img src="https://img.shields.io/badge/nginx-%23009639.svg?style=for-the-badge&logo=nginx&logoColor=white" alt="Nginx" style="vertical-align:top; margin:4px">


## Принципы и инструменты разработки
**Код-стиль и форматирование:** Я использовал Prettier для автоматического форматирования кода, чтобы обеспечить его чистоту и единообразие, что важно для удобства совместной работы над проектом.

**Линтер:** Применял ESLint с настроенными специфическими правилами для поддержания высокого качества кода и соблюдения лучших практик разработки.

**Система контроля версий:** Для управления кодовой базой использовался Git. Применялась стратегия GitFlow или аналогичная, что позволяло эффективно организовать процесс разработки, обеспечивая четкое разделение на стадии разработки, тестирования и релиза.

**Контейнеризация:** Важной частью моей работы было использование Docker, что облегчало процесс развертывания приложений и их изоляцию. Это способствовало более простой и надежной разработке, тестированию и деплою.

**Версионирование и интеграция:** Использовался GitHub как платформа для хранения репозиториев и управления версиями, а также для проведения code review и совместной работы над кодом.

**CI/CD:** Я активно использовал практики непрерывной интеграции (CI) и непрерывной доставки (CD) для автоматизации процессов тестирования и деплоя, что повышало качество и скорость выхода обновлений.

**Прочие инструменты:** Включали в себя такие инструменты, как системы для управления зависимостями, средства мониторинга и логирования, что обеспечивало эффективное и удобное управление проектом.

## Команда
- Общее количество человек: 3
- Роли в команде:
  - Front-end Developer: 1
  - Back-end Developer: 1
  - Team-Lead: 1

## Основные достижения и результаты
В процессе работы над этим проектом в роли Backend-разработчика мной были достигнуты следующие ключевые результаты:

Успешная интеграция: Мной была успешно выполнена интеграция между "HH.ru" и Битрикс24, что позволило эффективно синхронизировать данные между двумя системами на серверной стороне. 🔄

Улучшение производительности системы: Благодаря оптимизации запросов и использованию эффективных алгоритмов обработки данных, производительность серверной части значительно улучшилась. 🚀

Автоматизация процессов: Разработка и внедрение скриптов для автоматизации рутинных задач, таких как проверка авторизации и управление вакансиями, существенно улучшила рабочие процессы. ⚙️

Повышение безопасности: Усиление мер безопасности, включая шифрование данных и улучшенную систему аутентификации, повысило надежность и безопасность платформы. 🛡️

Оптимизация архитектуры: Применение принципов чистой архитектуры и микросервисного подхода способствовало созданию более гибкой и масштабируемой системы. 🛠️

Ускорение времени ответа сервера: Оптимизация запросов к базе данных и использование кэширования значительно сократили время ответа сервера на запросы пользователей. ⏱️

Положительный фидбек от пользователей: Разработанные серверные решения были хорошо приняты пользователями, что отразилось в повышении их удовлетворенности и лояльности к продукту. 👍

Эти достижения стали возможны благодаря тесному сотрудничеству с командой Front-end разработчиков, а также моему личному вкладу в разработку и оптимизацию серверной части проекта.

1. **Сложности с интеграцией:**
   - Первоначально процесс интеграции "HH.ru" и Битрикс24 представлял собой сложную задачу из-за различий в их API.
   - Мы решили эту проблему, тщательно изучив документацию обоих сервисов и применив адаптеры для преобразования данных.

2. **Высокая нагрузка на сервер:**
   - Большое количество одновременных запросов к API могло привести к перегрузке сервера.
   - Мы оптимизировали код, чтобы уменьшить количество запросов и реализовали кеширование для снижения нагрузки.


## Ссылки
- Демо проекта: Полная версия скоро появится на маркетплейс Bitrix24
- Код проекта: На данный момент, из-за ограничений, связанных с неразглашением информации (НДА), код проекта не может быть общедоступным.

Я придерживаюсь политики конфиденциальности и соблюдаю соглашения о неразглашении, поэтому кода проекта нет в общем доступе.
Если у вас есть вопросы относительно кода или функциональности проекта, пожалуйста, свяжитесь со мной напрямую, и я постараюсь предоставить необходимую информацию
