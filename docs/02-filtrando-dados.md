# Filtrando Dados

# WHERE

# Descrição

Filtra linhas com base em uma condição.

# Exemplo

```sql
SELECT name,
       milliseconds,
       bytes,
       albumid
FROM tracks
WHERE albumid = 1
  AND composer LIKE '%Smith%'
  AND mediatypeid IN (2,3)
  AND milliseconds > 250000;
```

# AND / OR

```sql
SELECT BillingAddress,
       BillingCity,
       Total
FROM invoices
WHERE (BillingCity = 'New York'
       OR BillingCity = 'Chicago')
  AND Total > 5;
```

# LIMIT

```sql
SELECT trackid,
       name
FROM tracks
LIMIT 10;
```

# OFFSET

```sql
SELECT trackid,
       name
FROM tracks
LIMIT 10 OFFSET 10;
```

# BETWEEN

```sql
SELECT InvoiceId,
       BillingAddress,
       Total
FROM invoices
WHERE Total BETWEEN 14.91 AND 18.86;
```

# IN

```sql
SELECT TrackId,
       Name,
       MediaTypeId
FROM tracks
WHERE MediaTypeId IN (1,2);
```

# LIKE

```sql
WHERE name LIKE 'Wild%'
```

Começa com `Wild`.

```sql
WHERE name LIKE '%Wild'
```

Termina com `Wild`.

```sql
WHERE name LIKE '%Wild%'
```

Contém `Wild`.

```sql
WHERE name LIKE '%Wi_d%'
```

`_` representa exatamente um caractere.

# IS NULL

```sql
SELECT lista_colunas
FROM nome_tabela
WHERE coluna IS NULL;
```

# GLOB

```sql
WHERE name GLOB 'Man*'
```

Começa com `Man`.

```sql
WHERE name GLOB '*Man'
```

Termina com `Man`.

```sql
WHERE name GLOB '?este*'
```

`?` representa um único caractere.

```sql
WHERE name GLOB '*[0-9]*'
```

Contém números.

```sql
WHERE name GLOB '*[^0-9]*'
```

Não contém números.