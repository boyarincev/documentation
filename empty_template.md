# Empty Template
## Добавление кодогенерации и миграций ЕФ.
``` json 
   "dependencies": {
    "Microsoft.VisualStudio.Web.CodeGeneration.Tools": {
      "version": "1.0.0-preview1-final",
      "type": "build"
    },
    "Microsoft.VisualStudio.Web.CodeGenerators.Mvc": {
      "version": "1.0.0-preview1-final",
      "type": "build"
    }
  },

  "tools": {
    "Microsoft.EntityFrameworkCore.Tools": {
      "version": "1.0.0-preview1-final",
      "imports": [
        "portable-net45+win8+dnxcore50",
        "portable-net45+win8"
      ]
    },
    "Microsoft.VisualStudio.Web.CodeGeneration.Tools": {
      "version": "1.0.0-preview1-final",
      "imports": [
        "portable-net45+win8+dnxcore50",
        "portable-net45+win8"
      ]
    }
  },```

Кодогенерация доступна из контекстного меню.
Для миграций используется `dotnet ef` [команда](https://docs.efproject.net/en/latest/cli/dotnet.html).