# ACID

> **ACID - это требования к транзакционным системам**

1. A - Atomicity (атомарность)

Атомарность гарантирует, что транзакция либо полностью выполняется, либо полностью не выполняется, то есть с точки зрения окружающих систем транзакция выполняется как одна неделимая операция. Пока транзакция находится в процессе выполнения, другие системы не могут наблюдать никаких ее промежуточных состояний.

2. С - Consistency (консистентность)

Данные остаются актуальными и согласованными до и после операции.

3. I - Isolation (изолированность)

Изолированность или сериализуемость – это отсутствие влияния на параллельно выполняемые транзакции. Если какие-либо транзакции выполняются параллельно, итог будет таким же, как если бы все транзакции выполнялись последовательно в некотором (задаваемом системой) порядке.

4. D - Durability (надежность)

Никакие сбои после завершения операции не могут привести к отмене результатов транзакции.