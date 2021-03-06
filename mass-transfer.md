---
layout: default
title: Массовый перевод
---
## Описание формата массового превода средств

Каждая строка состоит из нескольких обязательных параметров, 
разделенных символом табуляции (TAB). Несколько символов 
табуляции распознаются как один. Первые шесть параметров 
являются обязательными для всем платёжных систем. 
Для некоторых платёжных систем требуются дополнительные параметры.

**Возможные значения параметвов:**

[Код платёжной системы] - в зависимости от платёжной системы:

- PP - PayPal
- PX - Paxum
- WM - Webmoney
- EPM - ePayments
- CAP - Capitalist
- ADV - Advanced Cash

[Тип получателя] - тип получателя платежа: wallet / email / phone / ...

[Получатель] - получатель платежа.

[Сумма] - сумма платежа.

[Тип суммы] - S или R , сумма отправления или сумма к получению соответственно.

[Валюта] - валюта платежа, например USD

## Примеры готовых файлов

<pre class='bg-grey-lt-000'>
PP	email	mail1@mail.com	S	100	USD	payer
PP	email	mail2@mail.com	S	100	USD	payee
PP	email	mail3@mail.com	R	100	USD	payer
PX	email	mail4@mail.com	S	120	USD
PX	email	mail5@mail.com	R	120	USD
WM	wallet	Z000000000000	R	130	USD	Affiliate commission payout
WM	wallet	Z000000000001	S	99.99	USD	Payment for traffic
EPM	wallet	000-000000	R	140	USD
EPM	email	mail6@mail.com	R	150	USD
</pre>

## Использование Excel

Очень удобно готовить данные для импорта в таблицах (Excel / Google Docs) и затем копировать их в окно импорта. [Скачать пример файла с заготовкой платежей](/docs/import_sample.xlsx).

## PayPal (код: PP)

[Код платёжной системы] [Тип получателя] [Получатель] [Тип суммы] [Сумма] [Валюта] [Кто оплачивает сборы PayPal]

**Возможные значения индивидуальных параметров:**

[Кто оплачивает сборы PayPal] - обязательный параметр, payer или payee , сборы PayPal оплачивает отправитель или получатель соответственно. **Внимание!** для использования типа получателя payee требуется особое разрешение, которое можно получить через службу поддержки.

**Внимание!** Для PayPal так же доступны Комментарии, но оператор вправе изменить комментарий к платежу по своему усмотрению.

**Пример:**
<pre class='bg-grey-lt-000'>PP	email	mail@mail.com	S	100	USD	payer</pre>

## Paxum (код: PX)

[Код платёжной системы] [Тип получателя] [Получатель] [Тип суммы] [Сумма] [Валюта]

**Пример:**
<pre class='bg-grey-lt-000'>PX	email	mail@mail.com	S	100	USD</pre>

## Webmoney (код: WM)

[Код платёжной системы] [Тип получателя] [Получатель] [Тип суммы] [Сумма] [Валюта] [Примечание к платежу] - обязательный параметр, один из вариантов

**Возможные значения индивидуальных параметров:**

[Примечание к платежу] - обязательный параметр, один из вариантов:
- affiliate commission payout
- payment for advertising services
- payment for design
- payment for it services
- payment for freelance service
- payment for hosting
- payment for promotion
- payment for servers
- payment for traffic

**Пример:**

<pre class='bg-grey-lt-000'>WM	wallet	Z000000000000	S	99.99	USD	payment for traffic</pre>

## ePayments (код: EPM)

[Код платёжной системы] [Тип получателя] [Получатель] [Тип суммы] [Сумма] [Валюта]

**Особенности:**

Можно указывать только сумму к получению (Тип суммы = R). Сумма должна быть целой, без дробной части.

**Примеры:**

<pre class='bg-grey-lt-000'>
EPM	wallet	000-000000	R	100	USD
EPM	email	mail@mail.com	R	100	USD
EPM	phone	+70000000000	R	100	USD
</pre>

## Capitalist (код: CAP)

[Код платёжной системы] [Тип получателя] [Получатель] [Тип суммы] [Сумма] [Валюта] [Примечание к платежу] - обязательный параметр, один из вариантов

**Примеры:**

<pre class='bg-grey-lt-000'>
CAP	wallet	U0000000	R	100	USD
CAP	wallet	U0000000	R	100	USD	Test
</pre>

## Advanced Cash (код: ADV)

[Код платёжной системы] [Тип получателя] [Получатель] [Тип суммы] [Сумма] [Валюта]

**Примеры:**

<pre class='bg-grey-lt-000'>
ADV	wallet	U863070000000	R	210	USD
ADV	email	email@email.com	S	220	USD
</pre>

## Perfect Money (код: PM)

[Код платёжной системы] [Тип получателя] [Получатель] [Тип суммы] [Сумма] [Валюта]

**Примеры:**

<pre class='bg-grey-lt-000'>
PM	wallet	U00000000	R	100	USD
PM	wallet	U00000000	S	150	USD
</pre>

## Украинские банки (код: UAH)

[Код платёжной системы] [Тип получателя] [Получатель] [Тип суммы] [Сумма] [Валюта]

**Примеры:**

<pre class='bg-grey-lt-000'>
UAH	visa	4149439001200000	R	1000	UAH
UAH	mastercard	5168755629600000	R	1100	UAH
UAH	visa	4149439001200000	S	50	USD
UAH	mastercard	4149439001200000	S	60	USD
</pre>

## Российские банки Mastercard/VISA (код: RUB)

[Код платёжной системы] [Тип получателя] [Получатель] [Тип суммы] [Сумма] [Валюта]

**Примеры:**

<pre class='bg-grey-lt-000'>
RUB 	mastercard	5168755629600000	R	10000	RUB
RUB 	visa	4149439001200000	S	150	USD
</pre>

## Российские банки Maestro/MIR (код: RUB2)

[Код платёжной системы] [Тип получателя] [Получатель] [Тип суммы] [Сумма] [Валюта] [ФИО получателя]

**Примеры:**

<pre class='bg-grey-lt-000'>
RUB2	maestro	639002029000000000	S	150	USD	Иванов Иван Иванович
RUB2	mir	2200020200000000	R	10000	RUB	Иванов Иван Иванович
</pre>

## Яндекс Деньги (код: YAD)

[Код платёжной системы] [Тип получателя] [Получатель] [Тип суммы] [Сумма] [Валюта]

**Примеры:**

<pre class='bg-grey-lt-000'>
YAD	wallet	41000000000000	R	10000	RUB
YAD	wallet	41000000000000	S	150	USD
</pre>

## QIWI (код: QIWI)

[Код платёжной системы] [Тип получателя] [Получатель] [Тип суммы] [Сумма] [Валюта]

**Примеры:**

<pre class='bg-grey-lt-000'>
QIWI 	wallet	+00000000000	R	10000	RUB
QIWI 	wallet	+00000000000	S	150	USD
</pre>
