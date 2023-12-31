### Що таке Cross-Origin Resource Sharing (CORS)? Як усунути проблеми з CORS?

**CORS (Cross-Origin Resource Sharing)** - це набір правил, які забороняють поширення інформації між різними джерелами.

Якщо сайт *jeans.com* намагається отримати інформацію від сервера за адресою *infoaboutjeans.com*, то *CORS* блокує такий запит. Щоб уникнути цієї проблеми, ресурс *infoaboutjeans.com* повинен в хедерах відповіді додати атрибут *Cross-Origin-Resource-Sharing* зі значенням *(\*)* - це означає, що всі ресурси можуть отримувати інформацію з цього сервера. Або можна вказати значення *jeans.com* - це означає, що лише *jeans.com* може отримувати інформацію з цього сервера.

> Як *CORS* визначає, що запит прийшов з іншого домену?
> Кожен запит має параметр *Origin* в своєму хедері. Якщо запит приходить від *jeans.com*, то параметр *Origin* буде містити *jeans.com*. CORS порівнює значення параметра *Origin* запиту зі своїм хостом.
