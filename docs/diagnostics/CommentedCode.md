#  Закомментированный фрагмент кода

Программные модули не должны иметь закомментированных фрагментов кода, а также фрагментов,
которые каким-либо образом связаны с процессом разработки (отладочный код, служебные отметки, например, !!!_, MRG и т.п.)
и с конкретными разработчиками этого кода.

Например, недопустимо оставлять подобные фрагменты в коде после завершения отладки или рефакторинга:

```bsl
Процедура ПередУдалением(Отказ)
//    Если Истина Тогда
//        Сообщение("Для отладки");
//    КонецЕсли;
КонецПроцедуры
```
также неправильно:
```bsl
Процедура ПередУдалением(Отказ)
    Если Истина Тогда
        // Иванов: доделать 
    КонецЕсли;
КонецПроцедуры
```

Правильно: после завершения отладки или рефакторинга удалить обработчик ПередУдалением из кода.

[Источник](https://its.1c.ru/db/v8std/content/456/hdoc)

**Параметры**:  
 * *commentedCodeThreshold* - порог чуствительности свыше значения которого закомментированный текст считается кодом.
 Указывается в диапазоне от 0 до 1. Значение для каждого закомментированого участка заполняется по налицию ключивых слов в тексте.

**ВНИМАНИЕ**:  
Блок комментарием считается кодом, если хотя бы одна строка внутри блока определяется как код. 