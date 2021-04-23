Если у вас есть любые вопросы, не бойтесь задавать их мне или Азату в телеграме: @peltorator и @ismagilovcode. И даже тупые вопросы. В этом нет ничего плохого.

[Таблица результатов](https://docs.google.com/spreadsheets/d/1A8Fnmksnk_1XNDi7NWF6d9PUVuEA60NJl1NgLANrb1k/edit?usp=sharing)

# Setup

Все это легко гуглится, так что если что-то не получается, можно поискать в интернете решения.

Ресурсы:

[Консольные команды linux и macos (пока вам будет достаточно первых 5 пунктов)](https://omgubuntu.ru/basic-linux-commands-for-beginners/)

[Документация git](https://git-scm.com/book/ru/v2)

[Упражнения для знакомства с git](https://gitexercises.fracz.com/)

[Найти фунцию в Haskell по ее типу](https://hoogle.haskell.org/)

[Преобразование функций в бесточечный вид](http://pointfree.io/)

## Windows

Я плохо знаком с `windows`. Знаю, что надо установить [Haskell Platform](https://www.haskell.org/platform/).

## Онлайн решение

Есть [online haskell ide](https://rextester.com/l/haskell_online_compiler). Им можно пользоваться. Но там нет интерактивного режима. Запускать рекомендую следующим образом: пишете все нужные вам функции, после чего пишете функцию `main`, в которой вызываете нужную функцию от нужных параметров и выводите результат. Вот так:

```
main = print $ ...
```

К примеру:

```
adder x y = x + y

main = print $ adder 2 2
```

## Как установить stack (решение для linux и macos)

`linux`:

```
curl -sSL https://get.haskellstack.org/ | sh
```

`macos`:

Сначала необходимо установить утилиту `homebrew` (если у вас ее еще нет) следующей командой в терминале:

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

Затем нужно установить `stack` через `homebrew`:

```
brew install haskell-stack
```

Если у вас компьютер mac с чипом M1, то рекомендую запускать это через розетту (наверное, вы сами понимаете, что надо делать в таком случае, но вообще, нужно создать копию терминала, который будет запускаться под розеттой, и там настраивать свой `homebrew`).

Установка и дальнейшая настройка может длиться очень долго, не волнуйтесь по этому поводу.

## Как настроить stack

Напишите в консоль следующие команды, чтобы скачать необходимые библиотеки:

```
stack update
stack install HUnit
stack install hspec
stack install tasty
stack install tasty-hspec
stack install tasty-hunit
```

## Как получить себе репозиторий

Если вы знакомы с гитом, то вы и так все знаете, можете клонировать себе репозиторий.

Если же вы не знакомы с гитом, то просто нажмите на большую зеленую кнопку `Code` в верху страницы, после чего вам предложат вариант `Download ZIP`.

Когда вы разархивировали репозиторий, вам необходимо проинициализировать `stack` внутри него.
Напишите в консоль команду

```
stack init
```

# Выполнение заданий

В папке `src` находится файл `Tasks.hs`.
В нем есть несколько функций. Вам необходимо заменить `undefined` на корректное тело фунции.

Тесты находятся в папке `test/Test/`. Вы можете дописывать свои тесты по аналогии с уже существующими.

## Как запускать код и проверять его на тестах

Запустить консоль, перейти в папку с проектом.

Запустить интерпретатор `ghci`:

```
ghci
```

Если такая команда не работает, попробуйте `stack ghci`.

NB: чтобы выйти из `ghci`, пропишите команду `:q`.
Если у вас завис какой-то процесс в интерпретаторе, и вы хотите его завершить, то надо нажать какую-то из следующих комбинаций клавиш:
`<ctrl> + d`, `<ctrl> + c`, `<ctrl> + z`.

Запустить интерпретатор `ghci`, загрузив в него код из вашего файла:

```
ghci src/Task1.hs
```

Собрать проект (скорее всего вам не понадобится):

```
stack build
```

Запустить проект на тестах:

```
stack test
```


## Как сдавать задания

Задания сдаются в `ejudge`, как и все другие контесты. Но в системе не будет тестов, потому что все равно самое главное -- это проверка кодстайла. Любое решение сразу получает статус `pending review`. Ничего менять в вашем решении не надо, просто сдаете файл `Task1.hs`, `Task2.hs` или `Task3.hs` в соответствующую задачу в `ejudge`.
