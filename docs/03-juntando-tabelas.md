# Juntando Tabelas

# INNER JOIN

Retorna apenas as linhas com correspondência entre as tabelas.

```sql
SELECT Title,
       Name
FROM albums
INNER JOIN artists
ON artists.ArtistId = albums.ArtistId;
```

# LEFT JOIN

Retorna todas as linhas da tabela à esquerda.

```sql
SELECT artists.ArtistId,
       AlbumId
FROM artists
LEFT JOIN albums
ON albums.ArtistId = artists.ArtistId;
```

# RIGHT JOIN

Equivalente ao LEFT JOIN, mas retornando todas as linhas da tabela à direita.

# CROSS JOIN

Gera o produto cartesiano.

```sql
SELECT *
FROM tabela_a
CROSS JOIN tabela_b;
```

# SELF JOIN

Junção de uma tabela com ela mesma.

```sql
SELECT m.firstname || ' ' || m.lastname AS Gerente,
       e.firstname || ' ' || e.lastname AS Subordinado
FROM employees e
LEFT JOIN employees m
ON m.employeeid = e.reportsto;
```

## FULL OUTER JOIN

Retorna todas as linhas das duas tabelas.
