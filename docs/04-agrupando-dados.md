# Agrupando Dados

# GROUP BY

Agrupa linhas com valores iguais.

# Exemplo

```sql
SELECT albumid,
       COUNT(trackid)
FROM tracks
GROUP BY albumid;
```

# Resultado esperado

| AlbumId | COUNT(trackid) |
|----------|----------------|
| 1        | 10             |
| 2        | 3              |


# HAVING

Filtra grupos após o GROUP BY.

# Exemplo

```sql
SELECT albumid,
       COUNT(trackid)
FROM tracks
GROUP BY albumid
HAVING COUNT(trackid) > 15;
```

## SUM

```sql
SELECT albumid,
       SUM(milliseconds) AS length,
       SUM(bytes) AS size
FROM tracks
GROUP BY albumid;
```

# Explicação

- `SUM(milliseconds)` calcula a duração total do álbum.
- `SUM(bytes)` calcula o tamanho total do álbum.