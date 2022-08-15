# 连接两个表
> 表: Person
>
> +-------------+---------+
| 列名         | 类型     |
+-------------+---------+
| PersonId    | int     |
| FirstName   | varchar |
| LastName    | varchar |
+-------------+---------+
personId 是该表的主键列。
该表包含一些人的 ID 和他们的姓和名的信息
>
>
> 表: Address  
>
> +-------------+---------+  
| 列名         | 类型    |  
+-------------+---------+  
| AddressId   | int     |  
| PersonId    | int     |  
| City        | varchar |  
| State       | varchar |  
+-------------+---------+  
addressId 是该表的主键列。  
该表的每一行都包含一个 ID = PersonId 的人的城市和州的信息。  
>
>
> 编写一个SQL查询来报告 Person 表中每个人的姓、名、城市和州。如果 personId 的地址不在 Address 表中，则报告为空  null 。  
>
> 以 任意顺序 返回结果表。  
>
>
>来源：力扣（LeetCode）175  
>链接：https://leetcode.cn/problems/combine-two-tables

解决方案：  
```mysql
SELECT FirstName, LastName, City, State
FROM Person LEFT JOIN Address
ON Person.PersonId = Address.PersonId
```
## 总结
inner join：2表值都存在  

outer join：附表中值可能存在null的情况。  

总结：  

①A inner join B：取交集  

②A left join B：取A全部，B没有对应的值，则为null  

③A right join B：取B全部，A没有对应的值，则为null  

④A full outer join B：取并集，彼此没有对应的值为null  

上述4种的对应条件，在on后填写。
