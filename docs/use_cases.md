# Розроблення функціональних вимог до системи

## Діаграма прецедентів

![](https://www.plantuml.com/plantuml/png/ZP6zIiDG5CVtFCMXpXridQKYEEaYk0boRIunaDn0xWrISAYjuAY3LEWcla0C3QRQrbVutpVoDBUnT7F89UVZ_piVfwUDI4qMHvxecoIb5gPOsI4gUsz7Tem2kNriaT1qeMLAUr4Ot9ZhA9D_-S-OOM4dMDf9hHcoOhHcrAeZFmxLHZQGKPJSUbwcPLzeIQqrybm6eJOolLHuHSxgqhuupgRw21LXXGzySv4l_YjGOKxuH8wVTP-kk-Eh_LtmQHA4YgdlA5WuTvpYVwZE5dKc_L1GFr56AaDwmBt6J7rp6qA91NBYfyICeNcxvYxh2Bzst22xM-H9aiOK2oK26JEKQLEKpRnOikw9x4Dz1eRpLpMG0y-hpz3EseTkv1spip5zPtOzjtqEtx63Gus34nok9vNFn_y5)

## Діаграма можливостей користувача

**Користувач** може виконувати такі основні дії:

1. **Реєстрація облікового запису** – користувач створює новий акаунт для доступу до системи.
2. **Вхід у систему** – після реєстрації користувач може входити у свій акаунт, використовуючи облікові дані.
3. **Взаємодія з медіа-контентом** – після входу користувач отримує доступ до системи медіа-контенту та може переглядати, завантажувати або взаємодіяти з ним

![](https://www.plantuml.com/plantuml/png/ZT2nIiH040RWVfzYEEiKdhqSs6eZs0aIaoK6SXl8RWgxyomi1JbEiFK5OZ2OqpE-mZzlvEoU8kbibltPdM-6cLaNLwwU5qh5YIihck090o_Gymql-HOj6hwRK6pfpEgAzeeyktANHQsLggrEOgjfubzETPPRfwjpWqSq0dIy2iJY1rcY9mnumGUlyIwt5ZqsX3Sq-FBjTasEBlR7y76PvKRKPxHIkDavxV-ewHzrejCyfgGqJXj7zbfcdOlwu8juXQqehxpcUr58KkSJcYZmdzAq2-U0xQzze5JOI9H6Xs7iSPoEe_oUQPFwHNy3)

## Діаграма можливостей адміністратора

**Адміністратор** має можливість виконувати наступні дії:

1. **Додавання форми** – адміністратор може додавати нові форми для взаємодії користувачів з системою.
2. **Редагування форми** – адміністратор має можливість редагувати існуючі форми, змінюючи їхній вміст або параметри.
3. **Видалення форми** – адміністратор може видаляти форми, які більше не використовуються або стали застарілими.

![](https://www.plantuml.com/plantuml/png/XT8nJiCm50RWtQTuCdDx00PK169ZP6CnpLEfP3ieTWHieR2363emmGsYqagLQ3d3UpV2IL1SMQewH1dy_v_-M1avhmfV6Ys46lky04bljAGDpsdBStxY6LTKyun-kPAW79ncPchXI4ydj_uHjSxlXIWTZfL3a1TvOS0egoPeqFfhIn-quegVQK4rRGFv2lpIMBIXEZphrcngbtqhScS5Ae_DQP2-meX5MrsbKgV4zF-y6rrYnAxkieXz1cGP5dodqtR1hh4NF4UDFVXEwnRysRUkIwUOwAvpa0rEqblO-PnXEKoFuHWaFdYqcPEY7teusiyu71MZy6x-Z3y0)

### Use case 1. registerUser - реєстрація користувача

Користувач заходить в систему вперше, але для того, щоб отримати доступ до інтерфейсу програми їм необхідно зареєструватись. <br>
Основні кроки:

- User відкриває інтерфейс реєстрації
- Вводить необхідну інформацію (ім'я, прізвище, email, пароль)
- Підтверджує пароль за допомогою повторного вводу
- Натискає кнопку реєстрації
- Отримує лист про успішну реєстрацію на пошті та можливість увійти у свій акаунт

![UC_1. Реєстрація користувача - Діаграма прецедентів](https://www.plantuml.com/plantuml/png/ZLNXIXj14FxlKmpwssjp5ueM5S7s2KJeZu9Sucg3bqJkBhIs58oM-ATeAN92gLZh2roZgJ5gV8NPD-gtkzucrKkj4hAxyyqttyxCJkQZs0_ZHZKOYojn8CRexczcjLwBAQgy5xEUI-LwK0zdIu5VNfzRMbWkECG_k2CFP5DkoorEPKicSf-untrik_fuXzimx7Bw7vny81DE-KnnyJMdnBTOTcIBEtoEpmtu4cvh9b5R8QDLRwFrIct33_qg-UMu7Yx6cu4W_ws8wbM3CESqlXI9S9pyYDI29gQcIuMI60RmYL6EU92WeOkRKIogD54I9NTgsj1jGB2_9cXfuSLoWJxOspKYKVOZGUCp9PsZcIUbkTSrFaGIjWQvkalBjWxrsUW1MEiHqyyqsqS4oY5qCiglCa5MUZhJ829iRvHii7-2-4lP9DZkb-VG1bikvFEx6J-tuTtKt0YKWZqPEBiZdAsyOoKFpcsb2Fv69D_gHFJvQd1ja8tKOjKSQveEjsLYRmpkjcsD94_aA9dU7UiHFCx1sEGhw382x-d-hTX1kq_uIabK_KemYE3bynV_bOIyikmHB2cfle3BfO7j48JfFK5d3_yf02Zo87xHD8cf9paDPqwlwNcbLWuQAo8QcDr7pDPVx_8XxcCGRnYG3ocIiv91l260GcHFRTBOZHCUQdQ08tqMYdBirzO2f1nzskKU-cbFxkesGCwwUl3OXiz_dIzVsTTvn1qpjDItt7xOJGexYiHsgExhNtob9uT-ZnSGeokF-clhTSRcZcBBElFRmnbAMA0RYI-6XudcRIkjoCDbnk-PF3qi7MmeltWNOu16VsEA5k6DG7WMuLh4yAmAAsjlObgjrsCHMa_-0caf2fJeURThX1BVgXlY22Q7-3ltzKF6N1Wnzfq1un7_v5C-9MJfc5i4wxN3BOTFiD9rL5DLhVYC-zODwAuYcdIVkiNiHoHJEuyrVl_-0000)

| **Поле**              | **Значення**                                                                                                                                                                                                                                                                                                                     |
| --------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **ID**                | registerUser                                                                                                                                                                                                                                                                                                                     |
| **Назва**             | Реєстрація користувача                                                                                                                                                                                                                                                                                                           |
| **Учасники**          | User, система                                                                                                                                                                                                                                                                                                                    |
| **Передумови**        | - User не має облікового запису <br> - User має доступ до інтерфейсу реєстрації                                                                                                                                                                                                                                                  |
| **Результат**         | ✅ Користувач успішно зареєстрований у системі                                                                                                                                                                                                                                                                                   |
| **Виключні ситуації** | ⚠️ Неповні або некоректні дані <br> ⚠️ Проблеми із сервером <br> ⚠️ Користувач уже зареєстрований                                                                                                                                                                                                                                |
| **Основний сценарій** | 1. User відкриває інтерфейс реєстрації. <br> 2. Вводить необхідну інформацію (ім'я, прізвище, email, пароль). <br> 3. Підтверджує пароль. <br> 4. Приймає умови використання системи. <br> 5. Натискає кнопку реєстрації. <br> 6. Система надсилає підтвердження на email User. <br> 7. User підтверджує реєстрацію через email. |

![UC_1. Реєстрація користувача - Діаграма активності](https://www.plantuml.com/plantuml/png/VLFBRjDG4DtVhnZAWartR00Zr9_W0mgaKAaFb9XT5d7C0wGeaL3bIaY0-8DRmsqT9xP_OUQFE3DsmGMhYyHNCtFEd7DylJU9zyVnc-CZvwPF9wFnr5aXSe-8Fql6lxYK6HUSivSpGg6IEGUPoLiEl9Q4q0ro9edCSVBoNZ8vRz70rC0Nw2mKkRqdgrtY1k2Chz0jv1E7NHeTxnyUQGFm6I0RMHZ1TrsFRRdk0z6bf93G7oFGU4AhHhNcBNu_kPQbBCaAET0rXgksGQ0oJP9s2zJP6ZZpbXe1P97-SMdGGfsn1qKbAvAaAmJC5aRo5U2vLW5G6ZmgqrDAIZjyphwV49Rarm1Px4H8dN_qEFtKX9dZ0FqP82kmcl80fm4wChNizH2vazDuHEF3bwzYkdlm_E3X_GVkyRCdT4U5XSu3dg1N750NcaE5cWLqW-qQ-UMlyqxl1qtdaWC2l-d7E03M7Dtev0Mf7jVbWg0JD3PjBis_hvD3boeUlhq5IE__tUmHzB0gRWRloC2TN1A8sbIlsbtHdniFycysMl0M-DkrDcgQC9Reb7n4DHrSQABrzR_hVmOf0PY3VaqeN_06nz9IH88MBpTg4kecyUdhoEqXLVqyVmC0)

### Use case 2. loginUser - логін користувача

Користувач вже має свій обліковий запис, але для того, щоб увійти повторно після повного виходу з системи, мають ввести особисті дані для входу й пройти перевірку авторизації <br>
Основні кроки:

- User відкриває інтерфейс входу в систему
- Вводить email та пароль
- Натискає кнопку "Увійти"
- Система перевіряє облікові дані - точніше наявність облікового запису по введеній пошті й відповідність паролю
- User отримує доступ до свого облікового запису

![UC_2. Логін користувача - Діаграма прецедентів](https://www.plantuml.com/plantuml/png/ZPNHIXjF5CRlVOf3l7R__-o6eaL5i7q24NfH2BjnjC5DLdOdjBOKagQDDwMK8WfjHQmli4Q3CTNu2cVUgD_CP9E0BaPGPlTyvpVVd7DsN4ka7yj6BPoJLHcAEHhzB6z7TKb9zRrOyLogH64KhmIXNzbTtLmlkmxnBnxofJhYE-813rMJ-wgbFgasTpbL1vpEGE93vAUWDF7tbbFYUonxgiCzliBl7NX7t3KaKTyYwz0y9hlL-fuV-pNoApAAD-H-ACX_AvAePXNsFHKs4n4No4z8BsX-SIae1c9Qm6VMEVUq1IFTs4-agD5y809tSSdYzc3Otn6qkVwYxDA7yUaQYQZuYQ32Sc0gi_nViFgwpkVSXVKROFl4NLAjoIQgRVr0RFo8fMU6zX4RFG9qYYFa3m2lU60ghR6wzfgeckepk3UgHTZq2zfoDRL5kVWurSset0MYPOX8lU2_uAAXsZzXlnIR74reRWvjxF8KDFHGfskdCtFpV7eZxWaoa6LuM0n7mtPl7WZ10O9jNP7fmtksfhOGv3ISLLltvzLw9MniYMGITfy8J-S_Bl6c1P1F95gJJTM2LTWqpEJe1HAiB1OLwTTtGjG0pUdp09NxfWvqkSmOcMEdgeFw7XTo1l7bgt9nNBUU-QfIzBaFr5SDUg8ZEZsFcytDCVGNggtxmJV4zx3K10iRP0Wt3-5beu8CuyDyUcQWht54Cq0OIXEzpMXU7gqqelryU0aHtt6F-5fx0-_Gn43LKOHWFAENREqVTXinD5AyaxX_adoDEuF6cq5JcjQChuIuklD6qdOKIH6FS_axZf3g9keUw079Ee4wu1L23l5l7fgh57t9kLsT2V64__0vdnDgUSeTGlJMuOx3PtPGW6rXVh3YInwEqw3kQz22-xzRokxgpEqQrlZdyWy0)

| **Поле**              | **Значення**                                                                                                                                                                                                                         |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **ID**                | loginUser                                                                                                                                                                                                                            |
| **Назва**             | Логін користувача - вхід у систему                                                                                                                                                                                                   |
| **Учасники**          | User, система                                                                                                                                                                                                                        |
| **Передумови**        | - User має обліковий запис <br> - User знає свої облікові дані (email та пароль)                                                                                                                                                     |
| **Результат**         | ✅ Користувач успішно увійшов у систему                                                                                                                                                                                              |
| **Виключні ситуації** | ⚠️ Неправильні облікові дані <br> ⚠️ Користувач забув пароль <br> ⚠️ Проблеми із сервером <br> ⚠️ Користувач не зареєстрований                                                                                                       |
| **Основний сценарій** | 1. User відкриває інтерфейс входу в систему. <br> 2. Вводить email та пароль. <br> 3. Натискає кнопку "Увійти". <br> 4. Система перевіряє облікові дані. <br> 5. Якщо дані коректні, User отримує доступ до свого облікового запису. |

![UC_2. Логін користувача - Діаграма активності](https://www.plantuml.com/plantuml/png/ZLBTIW916BsVfnZijhjkgetm9Ne0gxK4VqAtEo_KBReHWf0DWfBe1TRDnTLqVONlUwFEcPKYAGYHdJddctFEDz-KEq6b7LmtwiPqJpf-ksiSu9b3AmyQoLGMsfDC4ebrP06iT22fzlH6KfbhtqgYjvBBL4CihVObqpvBPAbXeI89UU037Lg_KQdLBGfYAsjezi1zwD1LFcC_u7bPE3TyLg3Nie1uITvW5S4J9IKFSUNrsqlYBXN6Z8Oz2X7ndXgvJ60GGIidR94aHXFHBlrpm9c5IsfbeY4uB1ByKYxfZYeene0ovYJacMOhy6sxTd4Ps9tgMVLWRzySdHwpWNIxNAE_8nI77h61DzkI-OzBAVWdoG6uJf6GSxZR99wvqbH7v7Y8B2Ze54V716dkhYZZ-6OSKGeSFJfsQVpckML7PZC3njCHK-ORqxNRR3M2_pj1f41evWkzhqS4fHUNAUCx-5KDEPp6FuKxGUlACsM4TO_r4m00)

### Use case 3. editUserProfile - редагування особистих даних користувача

Користувач вже має свій обліковий запис та увійшов у нього. Перейшовши на сторінку свого особистого кабінету, хоче змінити щось із введених параметрів під час реєстрації <br>
Основні кроки:

- User відкриває сторінку профілю
- Змінює необхідні дані (email або пароль, імʼя або прізвище, комбінації пунктів) + можливо, встановлює аватар
- Натискає кнопку збереження
- Система перевіряє дані та зберігає зміни, якщо такі було внесено

![UC_3. Редагування особистих даних - Діаграма прецедентів](https://www.plantuml.com/plantuml/png/ZLJHJjjA47tdAqRX6T-BNLLG0KAY_GA4r8TAaMqM6k7OoDwefLKb0ZIyeBP2A4XL4QNyG0YrI249lp3xHvsTh6sQng9vi2UpPy_CdZFUvKIwiMpKWobPau6O0lDRs8X22KdjdLXqRF2Z88eNlS3rjvRMLggE1VWTK_o97RnM-zYbzm07wZFWK3LnY5VOKqsrHy-FmAY13l-174zKcqbtwTd73k0zXQbgSRMKQkmHeCjC8bo7KTFyDzcgXTjkxDR1zMKKhygTG83xHYHHtI0u3vMrHCGLS1FG0KpFpNkpddW8m0lJVgfROEZgJY957QOzuTbpyoEwRMhOtHImjlAywi3x_7IDHFXk8g2ouB5O2_zvIw_2SS6qEcDogROHIxMvgDxC_Odvfyp-WGfFA63DcXB7gaq4jwHOZ-arAPNOfVI0qlki9YKEA76dFkL5ghEJUMt3Uufzfc3MlCTIDhk4BU_p75FjAdPLE--LoJgaJ8_8ZZG_It84bEfcxeyDr8EIPKTmyYDScQBNet8tsPaA4eVbDOg0rR2ME8PdjT0F6kiYAPRjHvQB_GoU074OKC0B26FCmCsC49pYSUK4EyQvMFZI3JS3EZ4UatItsWbroFQeffQMfgsZMgJcQQLaHb-yh6R6d64wxWEzVu4wq6E4VJssm0DxH-BTKjITP8bcB2jbPpD0V4p4NraFYE-6McQJo6zUxMTiTXbRPkz9Df83J0jlKvtBE8oxVtj4QoI_U2lfGad-n3WvmduKuUI8XzzgNDjyBM4ZYgI8yvtuXPhhQ0tvZZmqAkEzLfbIj6G1ViCXJptPK78DMWNZ6Vx0Ixm4_8hdsD9gzYriMNZ1FcdQfZfYnwvnc6yZT4yJpTZ_sq_oIzLqkqnnenxy1W00)

| **Поле**              | **Значення**                                                                                                                                                                                                       |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **ID**                | editUserProfile                                                                                                                                                                                                    |
| **Назва**             | Редагування особистих даних                                                                                                                                                                                        |
| **Учасники**          | User, система                                                                                                                                                                                                      |
| **Передумови**        | - User має обліковий запис <br> - User увійшов у свій акаунт <br> - User знаходиться на сторінці профілю                                                                                                           |
| **Результат**         | ✅ Особисті дані користувача успішно оновлені                                                                                                                                                                      |
| **Виключні ситуації** | ⚠️ Неправильний формат облікових даних <br> ⚠️ Проблеми із сервером <br> ⚠️ Дані не змінені                                                                                                                        |
| **Основний сценарій** | 1. User відкриває сторінку профілю. <br> 2. Змінює необхідні дані (email або пароль, імʼя або прізвище, комбінації пунктів). <br> 3. Натискає кнопку збереження. <br> 4. Система перевіряє дані та зберігає зміни. |

![UC_3. Редагування особистих даних - Діаграма активності](https://www.plantuml.com/plantuml/png/FL9BhjD04DpFALfX0KXXnGOmGha41mZWGAHyK69sMUIJI215iOGYiuA86pZ9yujVdZE-GlUDNdNRiYnvPhfhQgfgfZEDkfFent3WtEpZD9pCd1K2zuxujoHynrUPSyudJcLFif0bUvcZSKDZHLoYwsMDmgFiRDSVBhGjE-21ojZpKJPAXM9265ARl0Y7tVwW3GfGWmG4spO1LpoNc00wiZT-b2uuFvTVdBsq8_vYnnA51LzD5eOR24gJr8A28sUWpFYii5O0R_nVyLXcN70wKvP33Jf9WaFYIgxNPICoSADn5DAa__LRHCzwdtjlNxznxpzzK0cPUKzLcKhd6yO7ahNcmuKg9BMENW9ztXniQcQTLZm7W0rbmd9IiuZPf9tixxceeFiwE2wLhRw87RwbR64jfbU48iZqRz4JN-moCDMTBXnz8JMaxkkGq3rRXWqq3vgd0DW_iEF-qLifgDHx1Bz9WvTxPGPtNBy40coXAFbP2V1Lfl3N09i4SD0q6d_7q84oUuFk2G00)

### Use case 4. createForm - Створення форми

Адміністратор має можливість створити нову форму для користувачів. Він відкриває інтерфейс для створення форми та додає необхідні поля й налаштування.
Основні кроки:

- Admin відкриває інтерфейс для створення нової форми.
- Вводить назву форми, опис.
- Додає необхідні поля (текстові поля, радіо-кнопки, прапорці тощо).
- Налаштовує валідацію полів і зовнішній вигляд форми (стилі, кольори).
- Зберігає форму

![UC_4. Створення форми - Діаграма прецедентів](https://www.plantuml.com/plantuml/png/ZLFDQjj04BxlKmpkjJ7KFvSIJ4ffU-cj57ee524lgQYb5EqA-aCXZjiqfnHAi4-b1Fe0YcpLIbpRhp3xHfrPPs45RPoBf9dvlczcPp_jAHsaEei7Ghs9ahT16iIW8psGZmyI_Ipw8A7L4JO1pn--wZG1pyqH5hWoXrZY4fVc6z1hPLCJC9zjvGzMBnCyCsFCSKfnJfaSSCqaSqp46PFD4G4A8O9G7wJGUD2FewG1WOA0lrmQpx4oGsfQieYjg_TAorY8JCamK98mjnpAiiDK1fhEbyQUm7SQPOPN1Aj8gW8AbzpJ71Axn4ip1AelIDWCRz-BTtRFxqAeqWfKJCfnZeKPUQIxG4fhFh2Zjppw6HLdc3jwIU65-M8dNven47758pfgswF-e6OBefxGqaTOE962qon0YMCpDgV0EdC-3akQ4txY9GChdB8uplvnnexNQO8NMDhbJ6qFXpOZX-vww5_NKZbtTSJVl5bAcP4Pudep1guiNMLXA9M2Eq-Z_TVwIIfb8WHl6PhDddUrS1zsTwCa76HzsUinehKLqTwAw6n5T6z6U0N6kTFKGSBw7tPsUjO_zR1L3zlri5CFksBpgt3i-rwaCjH1iZ_OcBB2AxhQK_FLseXsNh5BhYqnQS170U1RgSIrSmYmTVZ3tiwZ5pIkZ_r9EF89BgX3LRjYz_CuNglE8n2PctWby_btdFDWJ2xuoRgEsXR4hM_MJa9hbU-qJFgAwkvkRA__LjfUvPFOetSM3_u2)

| Поле              | Значення                                                                                                                                                                                                                                                                                                |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ID                | createForm                                                                                                                                                                                                                                                                                                  |
| Назва             | Створення форми                                                                                                                                                                                                                                                                                             |
| Учасники          | Admin, система                                                                                                                                                                                                                                                                                              |
| Передумови        | - Admin має обліковий запис <br> - Admin має доступ до інтерфейсу для створення форм                                                                                                                                                                                                                        |
| Результат         | ✅ Нова форма створена та збережена у системі                                                                                                                                                                                                                                                               |
| Виключні ситуації | ⚠️ Помилки збереження <br> ⚠️ Неповні дані <br> ⚠️ Проблеми із сервером                                                                                                                                                                                                                                     |
| Основний сценарій | 1. Admin створює форми для User. <br> 2. Відкриває інтерфейс для створення нової форми. <br> 3. Вводить назву форми, опис. <br> 4. Додає необхідні поля (текстові поля, радіо-кнопки, прапорці тощо). <br> 5. Налаштовує валідацію полів і зовнішній вигляд форми (стилі, кольори). <br> 6. Зберігає форму. |

![UC_4. Створення форми - Діаграма активності](http://www.plantuml.com/plantuml/png/hLFDojfG4DtVfxZGJGjsAzYKOZU-HulI2bMBJNTP6Atz0QbG96xQYcyGqqHJVv9Nc7cZdiD5JA2BRo5yV8bppypvcTps1__LsFyuU6U2bzr1VnWO5dpFFBFoGoD9vQWJoIMHM5SMXOjE9TE9Vf9C_cfeWJZfqcg8UY85m9bSv88I7eMmjBP0y-GikHlCCXfpdUg2k5WEakYiWcjO84eWGi-OGBPy8pFEue0pDfAH2sqHr2mX3aCJ558Aq8Z2OhvuPZZoUtRSV_FMjuywdMQhsJBFNx-myXCKUpavTspFvGWpt_KB9S6IKE0CpZ-3PEcQVc5yIMCr4jCRTYrvA6rxZGAZLYw6gZcTqP9Bc_2L51pZe1b-x7JEv1q1kHZmOxgN8rFWlCfHms9gB2bwYgTmGBuIJsPOyaXA4jE4PRD-a-B9mrDr8n0Ek1RKX1QkpLd7XFcT4zwWwKmwUh1oa9qJ9VlhftLB-xx4O47wQCieW5_xWL2o9_nFORLDhvqs0FzmWPKLM_w5jtmrgY_zD-Xvhm1r8MFXG3gQz6OLH-IrW8L4wLVKi_-cKhjbkCQZzvvfGoqkzpy0)

### Use case 5. editForm - Редагування існуючої форми

Адміністратор має створену форму, яка потребує змін. Обравши форму для редагування, адміністратор хоче внести зміни <br>
Основні кроки:

- Admin відкриває список своїх існуючих форм.
- Обирає форму для редагування.
- Вносить необхідні зміни (додає/видаляє поля, змінює форматування або стилі).
- Зберігає оновлену форму.

![UC_5. Редагування існуючої форми - Діаграма прецедентів](https://www.plantuml.com/plantuml/png/bPJDYXD14CVl_HJ5UdK39l4YIrWHruit4Jm8CaoQTJ2Po7G7_43ORDRrfY0o0Gz-l44sQzmnCSahLBsH_-uXxGoAYuSmtLNr_rLrLP5zOwFC3lizPPuawTCeY_fa4zlJ1uFKtajUQ6gsbJVG_LkFhZU8l_2Sl_6KpsNCCtnNl99t9BcCS1ZBMtd3QvcGdE1pn3-vU9Zo1ycT0lSfB5FY3OvpEVMeENJ729Wf5SLsaD7EpMu_INSeCXIvqzRCNxcGaHn30OZtc-V6whvIGwFZo6Z4_7TvdgExYJqOPFqAwBta02qGL21bGG1iN7vUywBEA-Hru7aQEdMjGlh4P-xbZXBYP4oWBrrfHt-hUCjfLYk2QouZp-4BC78O2iTPrz_ZbQsASi9dKBf4vwLw3UKQsPQ---DAMLjvkoOFkIu2wJj-W5ojQEjSdCeP3UDO6qDNxYQ7Z-sTJEjKATSYQZGweVDqW_RsaZJk3Rkwqt7-vYN-rYN-zh_ymOoOK64zHFdbeztTZXze_TgiNrlrQrkLY-dlORTKfcCRfOUzSfW5BtZf5sWbETRBxPcCiIUdsAx93hrKHBzdyD7rLawWo7bH3d7c9Y4Z67xuHjz-W2ghci_GO2CmZOMBtxYD9kIRokYFIOQb0wMfWAbroA7H7ltCwhHhu0tzTU4Lpokbzd5mVoY_0000)

| **Поле**              | **Значення**                                                                                                                                                                                               |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **ID**                | editForm                                                                                                                                                                                                   |
| **Назва**             | Редагування існуючої форми                                                                                                                                                                                 |
| **Учасники**          | Admin, система                                                                                                                                                                                             |
| **Передумови**        | Створена форма, що потребує змін                                                                                                                                                                           |
| **Результат**         | ✅ Зміни збережено, форма оновлена                                                                                                                                                                         |
| **Виключні ситуації** | ⚠️ Конфлікти версій <br> ⚠️ Помилки під час збереження                                                                                                                                                     |
| **Основний сценарій** | 1. Admin відкриває список своїх існуючих форм. <br> 2. Обирає форму для редагування. <br> 3. Вносить необхідні зміни (додає/видаляє поля, змінює форматування або стилі). <br> 4. Зберігає оновлену форму. |

![UC_5. Редагування існуючої форми - Діаграма активності](https://www.plantuml.com/plantuml/png/hLFDhj9G4DwVfpZ1ZIOcxaYmnc2Cl829UvIgJQ0rfRfY0Qq_BWmanjIDOdm3AFJI53YymimRtMzEBqrpaxkuoLr0XkattyzCwOwZVXXz70sLcZmRZ3n_ecp7KOyr_UIKjbJob0hAQCM_DC_eH0M-3PMQKnH7JdZEtz3yelap6O0FTdX9QpIdCbO_u4I3SCyBZLyvoXLjE15kEe9fuS05_HS1Zl7yGAk9KFqJEM1sd80Cy8BMmYpYj-2k4qeqD0tF81Np3qqxpATe5Ve-9Wq-iFr8bAGKLX4-aP7oOOtdUICSHkAce4Qn9gDjc0A3wGExcBy2b8oIIMXByGBo4X5Qz1j3kOsm4LZhnfrKe0nNc5RsCl3aeCsXdZOoESeF8bU7thltaRxNwxKxxOvwylgffZ_GlQ1zTTvgiIMCoZsFQ5pj9u7Dhv1PsA7dWVzswBs9NhdXs0jyvVe3BVmAhixceRkfiXcRBOD6VkrQT-lgPV-J-o8CWx3Xft7k9GRaBOQkFQIys1o3MfQuXLf-lja93QC1cmcAlyjEiSlwA3KKTnb7mGT7TQ4eVw1B)

### Use case 6. publishForm - Публікація форми

Адміністратор має створену повністю готову форму та хоче її опублікувати <br>
Основні кроки:

- Admin відкриває форму для публікації.
- Обирає параметри публікації (посилання, вбудовування на вебсайті).
- Керує доступом (хто може заповнювати форму).
- Публікує форму.

![UC_6. Публікація форми - Діаграма прецедентів](https://www.plantuml.com/plantuml/png/XLDTQnD157sVNp7KvmRS11-aX8fONtmJmGT1ritGBkvkoiui-87G9jA-Y8981455y0TiOm9BsYH_uSu_yimDkyvQQ1wIpBttd3DpxptProRCJP4cGh-Ci-Cm3rDfOfEeWs5c7iTlb0nwGd16Fhd__4v7qayxfWkwj1DQK6dFxCH-alOzhUm9NL7rBAClA9Nq1t69J2bfZUFSdj6SPlWixGY0gH1XP8QvtBatIEDiHuPQXkvKf-aNLVRKZi202DVrQsrKAaIXLHHg1SpDRs7ISV4YYVNHmJ1FFU9dK6Qq0Ax25LL3icE9_2LaQ7rD-oiBOWotFQKVTE4wTIhWuB1fUsv7Jln6cS2J-GR62Q3JMcf6AzS-KcjQqLNDwVfN--8Drs-cPlKyrcykyc9MlW0Y2D0I1QYKxHSWsmm6I9uRr_ZISxVGpOgAA59QorkFuiCZyp1NAXF2JKnsEdr_5_AktDkBioWf1ghVTv1WEwIx7TBR0l4hG3OFRgC4Mr7kxlPvtUqmQ8VTTjWJ6vjox9jFv2eoONQOiF-eeWN6-T6Uqz9Ef3sbYiVPMEIjaFBVqhxJlBKFSFZy0Kpd79hoz-P_yk0fdWnss-t0Z-t8O_g2MttFge60x7yJvDimFlNAg6oW0QYtm0olyaxiuxT8axy0)

| **Поле**              | **Значення**                                                                                                                                                                                     |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **ID**                | publishForm                                                                                                                                                                                      |
| **Назва**             | Публікація форми                                                                                                                                                                                 |
| **Учасники**          | Admin, система                                                                                                                                                                                   |
| **Передумови**        | Форма створена та готова для публікації                                                                                                                                                          |
| **Результат**         | ✅ Форма опублікована та доступна для користувачів                                                                                                                                               |
| **Виключні ситуації** | ⚠️ Недоступність сервера <br> ⚠️ Відсутність доступу для публікації                                                                                                                              |
| **Основний сценарій** | 1. Admin відкриває форму для публікації. <br> 2. Обирає параметри публікації (посилання, вбудовування на вебсайті). <br> 3. Керує доступом (хто може заповнювати форму). <br> 4. Публікує форму. |

![UC_6. Публікація форми - Діаграма активності](https://www.plantuml.com/plantuml/png/hLFFYjDW4Bz_J_6nNbRmlB1MPFUoHn741qXtWnl8ffAaFVNGDcezI08YAOXQVOCsD1gJD7s5cJVoDr-CjL1ldhxCd_dzPdupkGX2om-7TwvIuykREySRA-FfgOUQtdDA6ofvGWLbjE8FcbzH0xFcI2DISQ9fnn6jgK9gYPGtdFB257-1jq0kof241vzKKyupmJjQfq-HsF0KT1MIjxJbv846zPeZq3MKuSswYCQpacYE-1JUdu1ExnloZ-2PS2JK6q54919iglKfl-OPDPfgcDyfr_G3jHBBW1eBFkB5NwEsa9zRFvZATgOI_0qAIuXnGilzE1nr82Szo4hVf0fc3ihLMB2MqXxiZ5EqcGXQsqr5XJXDm-_-eQqt26tjEozkGttlwkhi_EnSFUe_rlHfZs1qmKU9sfZdHYYHrSZG0YMcw9djZsp_kMUDBCUr-gwjREz62uD2duT37QpVIFAL6hDawPKNl3WK6-fm_ETCIgbiXVYjpnomsVyTvydWwR3lEi7jvVMr7GJxORhZDeVPNg1COKvJZXpRoSnEDd8ItNtju6WqqgQInM_XZOuj9SQQWt3migSkm2W_qoy0)

### Use case 7. analizForm - Аналіз форми

Адміністратор має створену форму та хоче проаналізувати результати опитування <br>
Основні кроки:

- Admin відкриває інтерфейс для перегляду результатів форм.
- Обирає форму, результати якої потрібно переглянути.
- Аналізує отримані дані (завантажує звіт, фільтрує результати).
- Може експортувати дані у форматі CSV або Excel.

![UC 7. Аналіз форми - Діаграма прецедентів](http://www.plantuml.com/plantuml/png/TLFTQXD15BwVfpYaDmfwaJIKu8Mq-SaB1CKx6NQ74he_ihl1nYAOLF56K4HpgVW6szYOsBIRLpZpHdupEv5kIM-McUyxv_lEcNFsCCraaet2GAGdm-YLJ6H8qilYP92D0qNojKhZKDqbwKmGjQLtSfp4eyZln06mlNw_t-fsY0mN9xvA7Dvjj9iju4JWtWfHIXpvuJ1ovnh_ufMUw2al-9hp6icK1kCqKo7j7NMxhTu12J5AbITJHSywBsKaW_4RrO-J4A58_yaB_Gx9ltcjF_CbGIadplc6So0pNfAbb_eSrq-6rLF0SzBlkG1rpQlQRODwAViLCPTyXO0LSbQ4wmqEy4BUWl_g2O679V6cMe4-lyUnOjCeRNxm1OBpqi8L185xfIiQ-wN6bsslrdBkr22He-GPFU0bJe1D0_Z-SHq1dkkPdZw2CN9jgUZklyB3YbUpzFgE9vdmnXIAw1rkfdlNHzatTGRF2UG55zGxzLHG4udoCXaT1ygEhp0Zu3LVOVfd98YshhqNss5yS-9eT06dGa-i-QPq_EWUQKbsG1yC2j0cRC0Ky5w3DvCsgze-wDJjDhezU_pqpc89kw0xyCeLYML4dPxGCFA2aQzI8IpWcCPjnjuTiLybS7T4SoTXNWA4EirKvAVY45_pt_u3)

![](http://www.plantuml.com/plantuml/png/bLBDJi904BxlKspYHHFF98Wn69KNC7elqYX9AGQgyS01Yee78yPWlPdu1b2fB3zjNs7sZVncfS64W_6syyrytynyEyMcPpMygveZH6k_KgkwBM4GiIFfHGSqffbkawAGXdeW0SJQfqYtzIr5DDKTYOgvxajA6GNsoI6DTLUQSAAx01wr3xuFUYZ1J91Q5BZ5Eur88MBnB07gVqMDrZF5D0GUS1vwKFFDx0l0iGwWkdniqWIla2FMe2zJ3p3KWVQtCGb4q83v9hNUbTIMQVeAVpgKykIeHksg2wRDLc86a8FZKudaY19vT7DcEmMOJXymeCEcSbcBDT-uXXkQ_NkPQi9bc24rmL_saYe8j-xPib4zl_3aHgcKo-VoOhUyXuybHJFmddIFFPFOGB4qHExXGDzK7LgUTU9QrrRLiSgEZRa6cOynHR_dCI2aef-HfBcGEqO16aAAJ8ATvcPB9Mot8dcurT7nBMJVPHPcJ_a_k14up8mXrb-AmLts7IqUW2kQhXsBP5DWz-egO7VJgr-A8jhpnNy3)

### Use case 8. fillForm - Заповнення форми

Користувач вже має свій обліковий запис та увійшов у нього. Форма опублікована та доступна за посиланням, користувач бажає її заповнити. <br>
Основні кроки:

- User відкриває посилання на форму.
- Заповнює поля форми згідно з інструкціями.
- Натискає кнопку "Надіслати".
- Дані форми зберігаються в системі, і користувач отримує підтвердження.

![UC 8. Заповнення форми - Діаграма прецедентів](http://www.plantuml.com/plantuml/png/XL9DRzD05BplhtWAXvuQYPG3GbLK2L4klLMLE21L9bcALTkfx3NYGqWqeUM2G49HUk80ly2O1AoQ97_XxJzYrbl7jWBXO7dtxSpixBot5oadLB7lYUZK3SwSqF59kSgJ-uD07Rgl97NkYA90H_UFxxQ9hpZX9IyuvJdFyCtr9zBlUA7Vyc_E7WSyrXD0Vc2Ve98GBx6SwKkWfuQXXm2aGZWzDGYfTHJ9i4LEH34MPP6_SgRFzH1uI1J7qSj8ILy8m7fE987PxAGWFNKzRtyG-YNBNaUSmiAKhu7CG4_qc8oIFiSsXwhLmYzP2UfH8JWuay616vp-tOR-UAF4-J-ykDBhHpNo5rm-D6_bQsF3tedr71fB61pHbi7mL4-0oIrwomOIF_5TrNmTZurxFQdTJVoBl_FCz81_uZEdd1BKLWdhYJK8gKFdkUpJhGFtv9bw64eP254-cThjxYfGkaUxksxGy-A-x7P5zRPDgChnVxLAJEMf2J9F3cbxkzleYArKPgfQBImxI1NIr4GeUye9JZoJuMVEq84SpNnlipHH3VK8uL-Y3LSjUYs8wZsS5JEUSCePU1_CF18sgHtvSfocfZUGkYZIVl3e-FQwJ3dEwDhwT9UyJeFt3SszC4Plx1PU5kXv3Xu6e6Jj2D0QuHeBo5M-K390MEkddOsdExNJDs8F_zZt_W00)

![](http://www.plantuml.com/plantuml/png/hLDDRjD05DxFAPxAbdMbOeIwwWqu08W8aA15YTbvOSUKWbGH2LLbGq5mWi6r6ol6pXM-ToE-nvELoEiktCwClf_lVJCvNgJFvkdxjsz2zdGncsVX_puy4dpLQzJOQ8uM5Q9U2ROOjE2sGqIFNbV2Vr7q0mR2_cgP6F4ReY5H4V55dOQEu167Lh36hUcJFt0ZNFTQw59pBUdvKQzrPK0Jn0tTbsXflR4SRierkTWINSg1OL2JLQ1pz44IGePVHkEseLZCJEmd6isvhmZETQMMZmSHbGscb-XDXKakXKSLaJM_dZhdmcNqPH9EpzAPp5-_V9NAWvEJmwF3e_3u-HF1TmouG-UbYQaoQSSYBhmhzaVn4j67TD8DccaADFl-tlREVuzcJJjylIj-f8JPwGkngC5lvezDpx9lhKZNuxnxDtFFW_sctxbP4CM_tlN061qQivlcYvQGWsp9kz1IhnwAViQmIugrpq3K7JyU9M5ykbJuOKy8hRr5lrc-CLsYCWfgKiOgFOWGLXXAFrbdK_LfwxHQf6VlmZ5JyoVp3m00)


### Use case 9. deleteForm - Видалення форми

Адміністатор відкриває список форм, обирає форму зі списку та видаляє її. <br>
Основні кроки:

- Admin відкриває список форм.
- Вибирає форму для видалення.
- Підтверджує видалення.
- Система видаляє форму та всі пов'язані дані. Система забезпечує перевірку на відсутність конфліктів з іншими процесами, які можуть використовувати дані цієї форми.

![UC 9. Видалення форми - Діаграма прецедентів](http://www.plantuml.com/plantuml/png/XLDDYnD14BtthoZYUGDEFCaILlpmuaq43u8CasOTpCpAT0VyG329h1v4GPRnfWZ-W34cC2Jkv2zK_IDVzp1BRrZYQQQwtgjw_QhwoDYui9DihCppD7yH5t56DhLZVUyajm_JrvgY6yeVqAFRJ-_eiRP85LcV-2lNlEIADxpYSpwNBoJlkP5t_9Vh9pcVIOda7yGLJYhYBNvNSWhqqZ5a1i12gJYn9mNrResoDEzHR2XsVzqn_-HQfZ830qLythmoLcTAJOnEOgE1sQV4KqONkaEMb62j0QjHloQPyjOruuRN5mKy7JU_7X2_ysztAq_gS38d5DkWDIzsrNGreg363zTSPW2lG5-s4lPm1m7tLziIde9KaIC0MkwmfMpTcYI9DeQkFKYFdzdxXTQvKkv2rEyF0sFe9XqUfdaodepqSEWGqNyHW_s8805SfsG7fFouwU1Ww6s-74QNmu5gP-_YSAQgq8cDy-DnjmnhJEApVF2koDIPAtCCx5HA-TQZDueec0GtRazu0rRjp6nawl5RcNi7xpw6BAAh_FUEhttORcd32vdB6VYV46CFIsZu210wj2-WSIy0cYftrDMF51hisENQmYlzqkfyPAxCHq7-hJh2rptaVm00)

![](http://www.plantuml.com/plantuml/png/hLFDIiD04BxlKonuyD9peLQaNleUIeiMR2irtd986sahY04fyI8MmGT8IrD3cfzNc7aZlzdOO4l1YvUmE_DzytqpEsdSMHS3wxvxevHztkfsUhOo4NMYwOLzMb7C3aMqf81dceUKKuHlHh7c1ygGI-e62ym2AKTmPOfTZGeRzZGAH3W6jA6GKahPCxIvIF08sP0TvDViWdu8h6pw46c0Gqeei0rTQBWlsMU7FPvLD4yeAlKfA6h5vbgmCw0XmYD-mjtJx4DW2b028kN0PJn6tI7q4QghNjzgwq7dwjhIHyrcjLQjgTFBCqrlABM6HGodr46lpt2G8e024KHS36GCUrv1-YoDyIE5VxfJxLvBYm6r7R8P2tkxGmPH783XemKfSimUVG6QIcHL7FwvbJb8611eCJ0GoQ0lg9pTNT-lq5zG24Cv1ZkH1YlIV_RxeQI7qkhU2i1xkPzIy1qwifL9iIxv_XPjr-RdFJLWGq7n5F7mu7vXxVktIZLWtFmDtm00)
