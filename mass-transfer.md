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

## PayPal (код: PP)

[Код платёжной системы] [Тип получателя] [Получатель] [Тип суммы] [Сумма] [Валюта] [Кто оплачивает сборы PayPal]

**Возможные значения индивидуальных параметров:**

[Кто оплачивает сборы PayPal] - обязательный параметр, payer или payee , сборы PayPal оплачивает отправитель или получатель соответственно.

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
- за рекламу
- партнерские отчисления
- оплата за траффик
- платеж за разработку модуля
- за дизайн
- оплата за хостинг
- платеж за сервера
- оплата за продвижение
- Affiliate comission payout
- Payment for traffic
- Payment for advertising services
- Payment for IT services
- Payment for design
- Payment for freelance service
- Payment for server
- Payment for hosting
- Payment for partner

**Пример:**

<pre class='bg-grey-lt-000'>WM	wallet	Z000000000000	S	99.99	USD	за рекламу</pre>

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

## Украинские банки (код: UAH)

[Код платёжной системы] [Тип получателя] [Получатель] [Тип суммы] [Сумма] [Валюта]

**Примеры:**

<pre class='bg-grey-lt-000'>
UAH	visa	4149439001200000	R	1000	UAH
UAH	mastercard	5168755629600000	R	1100	UAH
UAH	visa	4149439001200000	S	50	USD
UAH	mastercard	4149439001200000	S	60	USD
</pre>
