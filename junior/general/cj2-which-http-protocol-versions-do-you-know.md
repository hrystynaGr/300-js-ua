### Які версії HTTP-протоколу вам відомі?
**HTTP/0.9** - (1991) реалізована комунікація клієнта і сервера.
**HTTP/1.0** - (1996) підтримка заголовків і статусних кодів.
**HTTP/1.1** - (1999) нова "сучасна" версія протоколу.
**HTTP/2.0** - мультиплексування запитів, стискання заголовків, було додано **TCP**, що дозволило каналу зв'язку залишатися відкритим після рукостискання (handshake).
**HTTP/3.0** - **UDP** був доданий як альтернатива **TCP**.
> **UDP (User Datagram Protocol)** швидший і менш безпечний, на відміну від **TCP (Transmission Control Protocol)**, який є повільнішим, але безпечнішим.
> Щоб знайти аналогію в реальному житті для **TCP** і **UDP**, можна уявити наступну ситуацію. Ви в офісі на кухні їсте сендвіч, ваш друг, який сидить за 4 столики від вас, просить вас поділитись сендвічем. **TCP** підхід - ви встаєте, підходите до столика друга, віддаєте йому сендвіч і переконуєтеся, що він його отримав. **UDP** підхід - ви кидаєте сендвіч вашому другу, сподіваючись, що він його зловить, і ви йдете далі, навіть не переконавшись, чи дійшов сендвіч до вашого друга.
> **UDP** краще використовувати для онлайн ігор, відеодзвінків, живого стрімінгу.
> **TCP** краще використовувати для веб-застосунків, обміну файлами, обміну повідомленнями.