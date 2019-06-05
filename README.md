# Android Style Guide

## 1 Android

### 1.1 Файлы ресурсов

Названия любых Android ресурсов должны соответствовать `lowercase_underscore`, а также соответствующему паттерну.

#### 1.1.1 Layout

Паттерн - `%component%_%feature%_%description%`.

Названия файлов должны соответствовать Android компоненту (Activity, Fragment, Dialog и т.д.). Т.е. если мы создаем layout для `ProfileActivity`, то название должно быть `activity_profile`

Пример:

| Full name      	| Component 	| Feature	| Description	|
|-|-|-|-|
| activity_profile	| activity 		| profile 	| - 			|
| fragment_avatar   | fragment 		| avatar 	| - 			|
| dialog_logout   	| dialog 		| logout    | - 			|
| item_search_user 	| -				| search 	| user    		|
| partial_progress 	| - 			| - 		| progress    	|

<br> `item` - элемент списка RecyclerView или ListView

`partial` используется для layout, которые добавляются в другие файлы layout (например, через тэг `include`)

#### 1.1.2 Drawable

Паттерн - `%feature%_%type%_%sub_type%_%description%_%selector_type%`.

Допускается использование сокращенного `%type%` (ic - icon, bg -background и т.д.).

Пример:

| Full name      				| Feature 	| Type   	| Sub type 	| Description	| Selector type |
|-|-|-|-|-|-|
| ic_arrow     					| - 		| ic 		| - 		| arrow 		| - 			|
| bg_edit_message     			| -			| bg		| edit 		| message 		| - 			|
| search_divider_users 			| search 	| divider	| - 		| users 		| - 			|
| signup_button_login_pressed	| sign_up 	| button   	| -			| login 		| pressed 		|

#### 1.1.3 Menu

Паттерн - `%component%_%feature%_%description%`.

Считается **плохим тоном** включать префикс `menu_` в название файла, т.к. файл уже лежит в папке menu.

Пример:

| Full name      		| Component  	| Feature	| Description 	|
|-|-|-|-|
| activity_profile     	| activity 		| profile 	| - 			|
| fragment_avatar_share	| fragment 		| avatar 	| share 		|

#### 1.1.4 Values

Название файлов ресурсов, которые лежат в папке values, должны быть во множественном числе.

Пример: `styles`, `strings`, `dimens`, `colors` и т.д.

### 1.2 Правила для XML

#### 1.2.1 ID в XML

ID элементов верстки должны соответствовать `lowercase_underscore` и паттерну - `%type%_%description%`.

`type` - сокращенное название соответствующего элемента. Пример: image - ImageView, text - TextView, edit - EditText и т.д.

Пример:

| Full name      	| Type   	| Description  	|
|-|-|-|
| image_avatar     	| image 	| avatar 		|
| text_description	| text 		| description 	|
| recycler_users	| recycler  | users  		|

<br> При использовании `kotlin-android-extensions` допускается использование `lowerCamelCase` вместо `lowercase_underscore`

ID элементов меню должны соответствовать паттерну - `menu_%description%`. Пример: `menu_done`, `menu_settings` и т.д.

#### 1.2.2 Строковые ресурсы

Названия строковых ресурсов должны соответствовать `lowercase_underscore` и паттерну - `%feature%_%type%_%description%`.

`%feature%` может быть опущен, если строковые ресурсы не относятся к конкретной фиче. Например, типовые строки (*OK*, *Cancel* и т.д.).

`%type%` - обобщенная информация о строковом ресурсе. Пример: `error`, `info`, `title`, `action` и т.д. `%type%` тоже может быть опущен.

Пример:

| Full name      			| Feature		| Type  	| Description 	|
|-|-|-|-|
| error_no_internet     	| - 			| error 	| no_internet	|
| sign_up_hint_login		| sign_up 		| hint 		| login			|
| about_app_copyright		| about_app     | -  		| copyright		|
| action_ok					| -      		| action  	| ok			|
| send_message_description	| send_message  | -  		| description	|

#### 1.2.3 Стили

Названия стилей должны соответствовать `UpperCamelCase` и паттерну `%Feature%%Component%%Type%%Description%`.

Пример:

| Full name      			| Feature		| Component	| Type  	| Description	|
|-|-|-|-|-|
| LoginButtonSignIn     	| Login 		| - 		| Button 	| SignIn		|
| SearchEditTextUsers		| Search 		| - 		| EditText 	| Users			|
| SplashTheme				| Splash     	| - 		| Theme  	| -				|
| DialogButtonPositive	    | -      		| Dialog 	| Button  	| Positive		|

#### 1.2.4 Цвета

Названия цветов должны соответствовать `lowercase_underscore` и паттерну `%feature%_%component%_%color_name%_%description%_%opacity%`.

Пример:

| Full name      			    | Feature		| Component	| Color name    | Description   | Opacity   |
|-|-|-|-|-|-|
| sign_up_button_blue_pressed   | sign_up 		| button    | blue 	        | pressed       | -		    |
| red_dark_80		            | - 	        | - 		| red_dark 	    | -             | 80		|
| download_progress_green	    | download     	| progress 	| green  	    | -             | -			|

#### 1.2.5 Размеры

Названия размеров должны соответствовать `lowercase_underscore` и паттерну `%feature%_%component%_%dimen_type%_%description%`.

Пример:

| Full name      			| Feature   | Component	| Dimen type    | Description   |
|-|-|-|-|-|
| margin_small              | -         | -         | margin 	    | small         |
| text_size_big		        | - 	    | - 		| text_size     | big           |
| download_progress_size    | download  | progress 	| size  	    | -             |

<br> Стандартные размеры для отступов и текста

```xml
    <dimen name="margin_extra_small">4dp</dimen>
    <dimen name="margin_small">8dp</dimen>
    <dimen name="margin_normal">16dp</dimen>
    <dimen name="margin_high">24dp</dimen>
    <dimen name="margin_extra_high">32dp</dimen>
    
    <dimen name="text_size_small">12sp</dimen>
    <dimen name="text_size_normal">14sp</dimen>
    <dimen name="text_size_high">16sp</dimen>
```

### 1.3 Порядок атрибутов элемента XML

1. Идентификатор
2. Стиль
3. Ширина
4. Высота
5. Остальные android атрибуты (`http://schemas.android.com/apk/res/android`) в алфавитном порядке
6. Res-auto атрибуты (`http://schemas.android.com/apk/res-auto`) в алфавитном порядке
7. Tools атрибуты (`http://schemas.android.com/tools`) в алфавитном порядке

### 1.4 Методы жизненного цикла

Переопределенные методы жизненнго цикла должны идти в порядке вызова этих методов

```kotlin
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
    }

    override fun onStart() {
        super.onStart()
    }

    override fun onResume() {
        super.onResume()
    }

    override fun onPause() {
        super.onPause()
    }

    override fun onStop() {
        super.onStop()
    }

    override fun onDestroy() {
        super.onDestroy()
    }
```

## 2 Koltin

### 2.1 Правила именования

* const и незменяемые поля в companion object - `SCREAMING_SNAKE_CASE`
* Любые другие поля и методы - `lowerCamelCase`
* Классы именуются в стиле `UpperCamelCase`

### 2.2 Структура класса

1. Блок companion object
2. Поля:
<br> 1. abstract
<br> 2. override
<br> 3. public
<br> 4. internal
<br> 5. protected
<br> 6. private
3. Блок init
4. Конструкторы (по степени увеличения кол-ва параметров)
5. Методы:
<br> 1. Абстрактные методы
<br> 2. Переопределенные методы родительского класса (в порядке следования их в родительском классе)
<br> 3. Методы интерфейсов (в порядке наследования интерфейсов и в порядке следования методов в интерфейсах)
<br> 4. public
<br> 5. internal
<br> 6. protected
<br> 7. private
6. Вложенные классы

### 2.3 Порядок указания модификаторов

1. public / protected / private / internal
2. expect / actual
3. final / open / abstract / sealed / const
4. external
5. override
6. lateinit
7. tailrec
8. vararg
9. suspend
10. inner
11. enum / annotation
12. companion
13. inline
14. infix
15. operator
16. data

### 2.4 Аннотации

Все аннотации ставятся перед модификаторами

```kotlin
    @Named("Foo")
    @JvmField
    private val foo: Foo
```

Если аннотация одна и без параметров, то она может быть записана в одну строку

```kotlin
    @JvmField private val foo: Foo
    @Test fun foo() { ... }
```

### 2.5 Форматирование кода

Если сигнатура метода или класса не помещается в одну строку, то следует записывать следующим образом:

```kotlin
    fun longMethodName(
        argument: ArgumentType = defaultValue,
        argument2: AnotherArgumentType
    ): ReturnType {
        // body
    }

    class longClassName(
        argument: ArgumentType = defaultValue,
        argument2: AnotherArgumentType
    ): ParentClass(), 
        Interface, 
        AnotherInterface {
        // body
    }
```

Цепочка вызовов методов переносится вместе с `.` или `?.`
```kotlin
    source.firstMethod()
            .secondMethod(10)
            ?.thridMethod { it.progress }
```

Оператор `?:` при разрыве выражения также переносится на новую строку
```kotlin
    val foo = source.veryLongMethodNameThatReturnsResult()
            ?: String.EMPTY
```
### 2.6 Условные операторы

Если `if()...else...` можно записать в одну строку, то фигурные скобки ставить не обязательно
```kotlin
    if (foo) bar() else baz()
```

Если блок в `when` можно записать в одну строку, то фигурные скобки ставить не обязательно
```kotlin
    when (foo) {
        case1 -> bar()
        case2 -> { 
            baz()
            qux()
        }
}
```

Если `if` или `when` возвращают значение, то return можно вынести
```kotlin
    return if (foo) {
        bar()
    } else { 
        baz()
    }
    
    return when (foo) {
        case1 -> bar()
        case2 -> baz()
        case3 -> qux()
    }
```

### 2.7 Лямбда-выражения

Если лямбда-выражение пишется в одной строке и имеет один параметр, то следует использовать `it` в качестве параметра
```kotlin
    foo { it > 10 }
```

При написании лямбда-выражения более чем в одну строку всегда использовать именованный аргумент, вместо `it`
```kotlin
    foo { bar ->
        ...
    }
```

При использовании лямбда-выражения в качестве аругмента следует выносить её за скобки, если этот параметр последний
```kotlin
    foo(bar, baz) { it > 10 }
    
    with(this) {
        ...
    }
```

Неиспользуемые параметры лямбда-выражений следует заменять на символ `_`

### 2.8 Другое

Остальные правила написания на Kotlin можно найти в [официальной документации по Kotlin](https://kotlinlang.org/docs/reference/coding-conventions.html) и на [сайте Android Developer](https://developer.android.com/kotlin/style-guide)

## 3 Java

Правила написания на Java можно найти [оффициальной странице Android](https://source.android.com/setup/contribute/code-style)

## 4 Common

### 4.1 Именование файлов классов

Названия любых файлов должны соответствовать `UpperCamelCase` и паттерну `%Description%%Type%`

Пример:

| Full name      	    | Description 	| Type	        |
|-|-|-|
| ProfileActivity	    | Profile 		| Activity 	    |
| AboutDialog           | About 		| Dialog 		|
| GetMessagesUseCase    | GetMessages 	| UseCase 		|
| DownloadService 	    | Download		| Service    	|
| UsersRepository 	    | Users 		| Repository    |
| ViewExt 	            | View 			| Ext    	    |
| TextUtils 	        | Text 			| Utils    	    |

<br> Если название интерфейса и реализации совпадает, то к названию реализации следует добавлять `Impl`

```kotlin
    interface ProfileRepository {
        ...
    }
    
    class ProfileRepositoryImpl : ProfileRepositroy {
        ...
    }
```

### 4.2 Именование пакетов

Название пакетов должны соответствовать `lowercase` (или для читабельности `lowerCamelCase`). Например: `com.google.presentation.feature.myprofile`
