# sass
Aprendendo sobre Sass

[SASS](https://sass-lang.com/guide/)
> O SASS é uma linguagem de extensão do CSS, a sigla significa “Syntactically Awesome Style Sheets” traduzindo ao pé da letra, folhas de estilo com uma sintaxe incrível. A sua ideia é adicionar recursos especiais como variáveis, mixins, funções e operações e outras opções variadas
> para tornar o CSS mais fácil de escrever e manter.
> O SASS é compilado para CSS, portanto, os navegadores não precisam saber o que é o sass.
> O SASS é uma linguagem de programação que pode ser utilizada para criar CSS mais rápido.

### index.html
```
<head>
    <link rel="stylesheet" href="./styles/index.css">
</head>
<body>
    <h1>Olá Mundo!</h1>
</body>
```

### index.scss
```
body {
    background: #cccccc;
    h1 {
        color: #333;
    }
}
```

### Compilando o SASS para CSS
```
instalar a extenção "live sass" e clicar no botao "watch sass"
```

### index.css gerado
```
body {
    background: #cccccc;
}
body h1 {
    color: #333;
}
```

### Variável
```
    $primary-color: #333;
    $secondary-color: #eee;
    $font: Helvetica, sans-sefit;
```

### Aninhamento
```
    body {
        background: $secondary-color;
        h1 {
            color: $primary-color;
        }
        &:after {
            content: "";
            width: 20px;
            height: 20px;
            background: $primary-color;
        }
        &:hover {
            opacity: .5;
        }
    }
```
### Modulos
```
//_modulo1.scss
$primary-color: #333;

body {
    font: Helvetica;
}

//index.scss
@use 'modulo1';
h1 {
    color: modulo1.$primary-color;
}
```

### Mixins
- São um grupo de declarações CSS
```
@mixin tema($theme: DarkGray) {
    background: $theme;
    color: #fff
}
.info {
    @include tema();
}
.alerta {
    @include tema(DarkRed);
}
.success {
    @include tema(DarkGreen);
}
```

### Extended 
```
.contato {
    @extended promocao;
}
```

