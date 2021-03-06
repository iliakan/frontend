---
layout: default
title: DOM & AJAX
---

{::options auto_ids="false" /}

[ГЛАВНАЯ](/)

# 2 DOM & AJAX
{: id="2"}

**ВНИМАНИЕ! РАЗДЕЛ НАХОДИТСЯ В СТАДИИ РАЗРАБОТКИ.**

Содержание:

2.1. [HTML, CSS](#2.1)

2.1.1 [Полезные ресурсы](#2.1.1)\\
2.1.2 [Смешанное занятие](#2.1.2)\\
2.1.3 [Домашнее задание](#2.1.3)\\
2.1.4 [Техническое задание](#2.1.4)
{:.toc}

2.2. [Работа с DOM, Events](#2.2)

2.2.1 [Полезные ресурсы](#2.2.1)\\
2.2.2 [Смешанное занятие](#2.2.2)\\
2.2.3 [Домашнее задание](#2.2.3)\\
2.2.4 [Техническое задание](#2.2.4)
{:.toc}

## 2.1 HTML, CSS
{: id="2.1"}

### 2.1.1 Полезные ресурсы
{: id="2.1.1"}

### 2.1.2 Смешанное занятие
{: id="2.1.2"}

### 2.1.3 Домашнее задание
{: id="2.1.3"}

### 2.1.4 Техническое задание
{: id="2.1.4"}

## 2.2 Работа с DOM, Events
{: id="2.2"}

### 2.2.1 Полезные ресурсы
{: id="2.2.1"}

1. Mozilla Developer Network. [Document Object Model (DOM)](https://developer.mozilla.org/en/docs/DOM).
2. W3C. [Document Object Model Events](http://www.w3.org/TR/DOM-Level-2-Events/events.html).
3. Илья Кантор. [Современный учебник JavaScript](http://learn.javascript.ru) // 2013.
4. [JSONP](http://www.json-p.org).


### 2.2.2 Смешанное занятие
{: id="2.2.2"}

### 2.2.3 Домашнее задание
{: id="2.2.3"}

1. Реализация игровой механики (на протяжении последующих домашних заданий в этом модуле).
2. Задействовать механизм publish–subscribe и реализовать ViewManager в соответствии с техническим заданием.

### 2.2.4 Техническое задание
{: id="2.2.4"}

1. Модернизировать используемые `View` так, чтобы у каждого представления был свой элемент в DOM. Другими словами, отрисовывать (метод `render()`) представление необходимо всего один раз, а методы`show()` и `hide()` использовать для управления видимостью элемента, который содержит отрисованное представление.
2. Необходимо создать представление `ViewManager` и организовать его работу следующим образом:
    1. Добавить зависимость `ViewManager` в роутер.
    2. Каждый `View` должен бросать событие `show` во время вызова метода `show()`, на которое будет подписываться `ViewManager`.
    3. Роутер должен информировать `ViewManager` об используемых `View`, а `ViewMagaer` подписываться на событие `show` новых представлений.
    4. В роутере для показа `View` необходимо использовать метод `show()` соотвествующего представления.
    5. Роутер не должен управлять скрытием остальных представлений (то есть вызовы метода `hide()` представлений в роутере должны отсутствовать).
    6. Обработка события `show` представлений в `ViewManager` заключается в том, чтобы скрыть все известные ему представления за исключением представления, которое породило это событие.

Таким образом, у нас должен получится гибкий механизм управления экранами. Когда нам необходимо показать какой-нибудь экран, мы просто вызываем метод `show()` у соотвествующего представления, а все остальные представления за нас скроет `ViewManager`.

