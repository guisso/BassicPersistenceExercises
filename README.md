# BasicPersistenceExercises
Applying persistence for simple projects in C# with Entity Framework.

## Rules

- Obey coding conventions
- <mark>Use properties instead of attributes</mark>
- Use the namespace ```BasicPersistenceExercises```
- Use the connection string ```@"server=127.0.0.1;port=3307;uid=root;pwd=;database=basicpersistence"```

## Patient Management

![Patient Management](/resources/persistencia_gestao_pacientes.png)

## Order Management

![Order Management](/resources/persistencia_gestao_pedidos.png)

## Event Management

![Event Management](/resources/persistencia_gestao_eventos.png)

## Task Management

![Task Management](/resources/persistencia_gestao_tarefas.png)

## Repository

```
using System;
using Microsoft.EntityFrameworkCore;

namespace BassicPersistenceExercises
{
    public class Repository : DbContext
    {
        private static readonly String _connectionParams =
        @"server=ifnmg.edu.br;port=3306;uid=root;pwd=;database=mydatabase";

        public Repository() => Database.EnsureCreated();

        protected override void OnConfiguring(DbContextOptionsBuilder optionBuilder)
        {
            base.OnConfiguring(optionBuilder);
            optionBuilder.UseMySQL(_connectionParams);
        }
    }
}
```
