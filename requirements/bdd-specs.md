# BDD Specs

## Narrativa 1

```
 Como um cliente online
Quero que o sistema me mostre minhas compras
 Para eu poder controlar minhas despesas
```

### Cenários

```
 Dado que o cliente tem conexão com a internet
Quando o cliente solicitar para carregar suas compras
 Então o sistema deve exibir suas compras vindo de uma API
    E substituir os dados do cache com os dados mais atuais
```

## Narrativa 2

```
 Como um cliente offline
Quero que o sistema me mostre minhas útlimas compras gravadas
 Para eu poder ver minhas despesas mesmo sem ter internet
```

### Cenários

    Dado que o cliente não tem conexão com a internet
        E exista algum dado gravado no cache
        E os dados do cache forem mais novos que 3 dias

Quando o cliente solicitar para carregar suas compras
Então o sistema deve exibir suas compras vindas do cache

    Dado que o cliente não tem conexão com a internet
        E exista algum dado gravado no cache
        E os dados do cache forem mais velhos ou iguais a 3 dias

Quando o cliente solicitar para carregar suas compras
Então o sistema deve exibir uma mensagem de erro

    Dado que o cliente não tem conexão com a internet
        E o cache esteja vazio

Quando o cliente solicitar para carregar suas compras
Então o sistema deve exibir uma mensagem de erro
