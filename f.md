# F\#

## Супер Основное

### Имена значений \(неправильно использовать термин - переменная ?\)

Названия значений регистрозависимы.

### Пробелы и блоки кода

Пробелы используются для разграничения блоков кода - любые инструкции имеющие отступ больше, чем у инструкции if - будут считаться телом if.

Использование табов запрещено в F\# \(студия может автоматом преобразовать табы в пробелы\)

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

В F\# имеет значение порядок в котором выполняется компиляция файлов. Можно использовать только те функции и классы, которые были определены выше в этом же файле или в другом файле, скомпилированном ранее.

В студии файлы компилируются в том же порядке, в котором отображаются в окне.

## Основное

### Литералы

Основная статья:

{% embed url="https://docs.microsoft.com/ru-ru/dotnet/fsharp/language-reference/literals" %}



#### **Литералы типов**

| Type | Description | Suffix or prefix | Examples |
| :--- | :--- | :--- | :--- |
| sbyte | signed 8-bit integer | y | `86y`  `0b00000101y` |
| byte | unsigned 8-bit natural number | uy | `86uy`  `0b00000101uy` |
| int16 | signed 16-bit integer | s | `86s` |
| uint16 | unsigned 16-bit natural number | us | `86us` |
| int  int32 | signed 32-bit integer | l or none | `86`  `86l` |
| uint  uint32 | unsigned 32-bit natural number | u or ul | `86u`  `86ul` |
| nativeint | native pointer to a signed natural number | n | `123n` |
| unativeint | native pointer as an unsigned natural number | un | `0x00002D3Fun` |
| int64 | signed 64-bit integer | L | `86L` |
| uint64 | unsigned 64-bit natural number | UL | `86UL` |
| single, float32 | 32-bit floating point number | F or f | `4.14F` or `4.14f` |
|  |  | lf | `0x00000000lf` |
| float; double | 64-bit floating point number | none | `4.14` or `2.3E+32` or `2.3e+32` |
|  |  | LF | `0x0000000000000000LF` |
| bigint | integer not limited to 64-bit representation | I | `9999999999999999999999999999I` |
| decimal | fractional number represented as a fixed point or rational number | M or m | `0.7833M` or `0.7833m` |
| Char | Unicode character | none | `'a'` or `'\u0061'` |
| String | Unicode string | none | `"text\n"`  or  `@"c:\filename"`  or  `"""<book title="Paradise Lost">"""`  or  `"string1" + "string2"`  See also [Strings](https://docs.microsoft.com/ru-ru/dotnet/fsharp/language-reference/strings). |
| byte | ASCII character | B | `'a'B` |
| byte\[\] | ASCII string | B | `"text"B` |
| String or byte\[\] | verbatim string | @ prefix | `@"\\server\share"` \(Unicode\)  `@"\\server\share"B` \(ASCII\) |

#### Префиксы оснований

```fsharp
let hex = 0xFCAF //В 16ричной системе
let oct = 0о7771L // В 8ричной системе
let bin = 0b00101010y //двоичная

```

### Арифметика

