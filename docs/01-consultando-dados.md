# Consultando Dados

# SELECT

# Descrição

Usado para selecionar dados de uma ou mais colunas.

# Sintaxe

```sql
SELECT lista_de_colunas
FROM nome_tabela;
```

# Exemplos

```sql
SELECT TrackId, Name, Composer, UnitPrice
FROM tracks;
```

```sql
SELECT *
FROM tracks;
```

# Observações
- `SELECT *` retorna todas as colunas.


# ORDER BY

# Descrição

Usado para ordenar os resultados retornados.

# Sintaxe

```sql
SELECT lista_de_colunas
FROM nome_tabela
ORDER BY coluna ASC;
```

# Exemplos

```sql
SELECT name, milliseconds, albumid
FROM tracks
ORDER BY albumid ASC;
```

```sql
SELECT name, milliseconds, albumid
FROM tracks
ORDER BY 3 ASC;
```

# Observações

- `ASC` = ordem crescente, utilizado por padrão.
- `DESC` = ordem decrescente.

# DISTINCT

# Descrição

Remove valores duplicados.

# Exemplo

```sql
SELECT DISTINCT city
FROM customers
ORDER BY city;
```

# CASE

# Descrição

Implementa lógica condicional semelhante ao `if-else`.

# Sintaxe

```sql
CASE expressao
    WHEN valor THEN resultado
    ELSE resultado_padrao
END
```

# Exemplo

```sql
SELECT customerid,
       firstname,
       lastname,
       CASE country
            WHEN 'USA' THEN 'Domestic'
            ELSE 'Foreign'
       END AS CustomerGroup
FROM customers;
```

# Exemplo 2

```sql
SELECT trackid,
       name,
       milliseconds,
       CASE
            WHEN milliseconds < 60000 THEN 'Short'
            ELSE 'Long'
       END AS Category
FROM tracks;
```