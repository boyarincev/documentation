# F\#

## Супер Основное

### Имена значений (неправильно использовать термин - переменная ?)

Названия значений регистрозависимы.

### Пробелы и блоки кода

Пробелы используются для разграничения блоков кода - любые инструкции имеющие отступ больше, чем у инструкции if - будут считаться телом if.

Использование табов запрещено в F# (студия может автоматом преобразовать табы в пробелы)

### Комментарии

```fsharp
// Однострочный комментарий
(*
Многострочный
комментарий
*)

/// XML-док. Будет отображаться в студии при наведении на идентификатор.
/// Должен устанавливаться перед идентификатором
let main (args : string[]) =
    printfn "Напечатать текст"
```

### Порядок файлов

В F# имеет значение порядок в котором выполняется компиляция файлов. Можно использовать только те функции и классы, которые были определены выше в этом же файле или в другом файле, скомпилированном ранее.

В студии файлы компилируются в том же порядке, в котором отображаются в окне.

## Основное

### Литералы

Основная статья:

{% embed url="https://docs.microsoft.com/ru-ru/dotnet/fsharp/language-reference/literals" %}



#### **Литералы типов**

| Type                      | Description                                                       | Suffix or prefix | Examples                                                                                                                                                                                                                                                                                                             |
| ------------------------- | ----------------------------------------------------------------- | ---------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| sbyte                     | signed 8-bit integer                                              | y                | <p><code>86y</code><br><br><code>0b00000101y</code></p>                                                                                                                                                                                                                                                              |
| byte                      | unsigned 8-bit natural number                                     | uy               | <p><code>86uy</code><br><br><code>0b00000101uy</code></p>                                                                                                                                                                                                                                                            |
| int16                     | signed 16-bit integer                                             | s                | `86s`                                                                                                                                                                                                                                                                                                                |
| uint16                    | unsigned 16-bit natural number                                    | us               | `86us`                                                                                                                                                                                                                                                                                                               |
| <p>int<br><br>int32</p>   | signed 32-bit integer                                             | l or none        | <p><code>86</code><br><br><code>86l</code></p>                                                                                                                                                                                                                                                                       |
| <p>uint<br><br>uint32</p> | unsigned 32-bit natural number                                    | u or ul          | <p><code>86u</code><br><br><code>86ul</code></p>                                                                                                                                                                                                                                                                     |
| nativeint                 | native pointer to a signed natural number                         | n                | `123n`                                                                                                                                                                                                                                                                                                               |
| unativeint                | native pointer as an unsigned natural number                      | un               | `0x00002D3Fun`                                                                                                                                                                                                                                                                                                       |
| int64                     | signed 64-bit integer                                             | L                | `86L`                                                                                                                                                                                                                                                                                                                |
| uint64                    | unsigned 64-bit natural number                                    | UL               | `86UL`                                                                                                                                                                                                                                                                                                               |
| single, float32           | 32-bit floating point number                                      | F or f           | `4.14F` or `4.14f`                                                                                                                                                                                                                                                                                                   |
|                           |                                                                   | lf               | `0x00000000lf`                                                                                                                                                                                                                                                                                                       |
| float; double             | 64-bit floating point number                                      | none             | `4.14` or `2.3E+32` or `2.3e+32`                                                                                                                                                                                                                                                                                     |
|                           |                                                                   | LF               | `0x0000000000000000LF`                                                                                                                                                                                                                                                                                               |
| bigint                    | integer not limited to 64-bit representation                      | I                | `9999999999999999999999999999I`                                                                                                                                                                                                                                                                                      |
| decimal                   | fractional number represented as a fixed point or rational number | M or m           | `0.7833M` or `0.7833m`                                                                                                                                                                                                                                                                                               |
| Char                      | Unicode character                                                 | none             | `'a'` or `'\u0061'`                                                                                                                                                                                                                                                                                                  |
| String                    | Unicode string                                                    | none             | <p><code>"text\n"</code><br><br>or<br><br><code>@"c:\filename"</code><br><br>or<br><br><code>"""&#x3C;book title="Paradise Lost">"""</code><br><br>or<br><br><code>"string1" + "string2"</code><br><br>See also <a href="https://docs.microsoft.com/ru-ru/dotnet/fsharp/language-reference/strings">Strings</a>.</p> |
| byte                      | ASCII character                                                   | B                | `'a'B`                                                                                                                                                                                                                                                                                                               |
| byte\[]                   | ASCII string                                                      | B                | `"text"B`                                                                                                                                                                                                                                                                                                            |
| String or byte\[]         | verbatim string                                                   | @ prefix         | <p><code>@"\\server\share"</code> (Unicode)<br><br><code>@"\\server\share"B</code> (ASCII)</p>                                                                                                                                                                                                                       |

#### Префиксы оснований

```fsharp
let hex = 0xFCAF //В 16ричной системе
let oct = 0о7771L // В 8ричной системе
let bin = 0b00101010y //двоичная

```

### Арифметика
