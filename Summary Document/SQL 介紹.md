# SQL 介紹

------

SQL全名:Structured Query Language 結構化查詢語言

管理系統，可分為兩種:

1. 關聯式資料庫管理系統 (RDBMS)
2. 關係流資料管理系統 (RDSMS)

資料庫可分為四種語言:

1. 資料定義語言 (Data Definition Language, DDL): 針對資料庫的資料表進行建立，變更，刪除..等命令。如: Create(建立資料庫物件)，Alter(變更資料庫物件)，Drop(刪除資料庫物件)，Truncate，Comment and Renmae ...etc.
2. 資料處理語言 (Data Manipulation Language, DML): 處理資料表內的命令。如: Select(選取資料庫中的資料)，Insert(新增資料到 Table 中)，Update(更改 Table 中的資料)，Delete(刪除 Table 中的資料) ...etc
3. 資料控制語言 (Data Control Language, DCL): 管理資料庫與授權的命令。如: Grant(賦予使用者使用物件的權限)，Revoke(取消使用者使用物件的權限) ...etc
4. 交易控制語言 (Transaction Control Language): 多人環境的交易控制命令。如: Savepoint，Rollback(異動的資料回復到 Transaction 開始的狀態) and Settransaction ...etc

> 資料庫本身就是一堆資料表集合而成，所以資料經過處理後的結果也還是資料表，差別在於欄位數目與資料筆數會隨著改變。



##DML 資料處理語言 

-------

### 大概介紹:

1. SELECT 命令: `SELECT"欄位" FROM"表格名稱";`
2. WHERE 命令: `SELECT"欄位" FROM"表格名稱" WHERE"condition";`
3. IN 命令: `SELECT"欄位" FROM"表格名稱" WHERE"欄位" IN('值1','值2','值3','值4'....);`
4. LIKE 命令: `SELECT"欄位" FROM"表格名稱" WHERE"欄位" LIKE{模式};`
5. DISTINCT 命令: `SELECT DISTINCT"欄位" FROM"表格名";`
6. AND/OR 命令: `SELECT"欄位" FROM"表格名" WHERE"簡單條件" {[AND/OR]"簡單條件"}+;`
7. BETWEEN 命令: `SELECT"欄位" FROM"表格名" WHERE"欄位" BETWEEN'值1' AND'值2';`
8. ORDER BY 命令: `SELECT"欄位" FROM"表格名" [WHERE"條件"] ORDER BY"欄位"[ASC,DESC];`
9. COUNT 命令: `SELECT COUNT("欄位") FROM"表格名";`
10. GROUP BY 命令: `SELECT"欄位" FROM"表格名稱" GROUP BY"欄位_1";`
11. CREATE 命令: `CREATE TABLE"表格名稱" ("欄位_1","欄位_2","欄位_3","欄位_4,...etc");`
12. DROP 命令: `DROP TABLE"表格名稱";`
13. TRUNCATE 命令: `TRUNCATE TABLE"表格名稱";`
14. UPDATE 命令: `UPDATE"表格名稱" SET"欄位_1"=[值] WHERE"條件";`
15. HAVEING 命令: `SELECT"欄位_1",SUM("欄位_2") FROM"表格名稱" GROUP BY"欄位_1" HAVING(函數條件);`
16. INSERT 命令: `INSERT INTO"表格名稱"("欄位_1","欄位_2",...etc) VALUES("值_1","值_2","值_3",...etc);`
17. DELETE 命令: `DELETE FROM"表格名稱" WHERE"條件";`
18. (Not)LIKE 命令: `*、_、%、[abc]、Pattern`
19. 比較 命令: `= 、 < 、 > 、 <= 、 >= 、 between`
20. 聚合 命令:`Count 、 Ave 、 Sum 、 Max 、 Min`
21. 運算 命令: `+ 、 - 、 * 、 / 、 %`

##### Select 語法

* 用來截取或查詢資料表內容
* 用到 WHERE: [查詢]、[擷取]取出某些滿足條件的資料表內容
* 沒用 WHERE: [擷取]取出資料表某些欄位內容

Code:

```mysql
SELECT 欄位1, 欄位2,, 
FROM 資料表名稱
WHERE <條件式>;
```

範例:

```mysql
SELECT* //擷取所有欄位的資料
FROM teachers; //從teachers資料表中
```

| name | tel     | sex  | address      |
| ---- | ------- | ---- | ------------ |
| 曉華 | 3769999 | 女   | 高雄市三民區 |
| 小明 | 2769999 | 男   | 高雄市左營區 |
| 小鐘 | 1769999 | 男   | 高雄市前鎮區 |

以上這些資料儲存在 Students資料表內。

STUDENT_ID: NAME

CLASS_ID: TEL, SEX

MAILBOX: ADDRESS

```MYSQL
SELECT NAME, TEL, SEX, ADDRESS//擷取這些欄位的資料
FROM Students//從Students資料表中
```



##### SELECT / WHERE語法

* 在SELECT查詢中，透過WHERE的條件來判斷並取出所要的資料

```MYSQL
SELECT 欄位_1, 欄位_2....
FROM 資料表名稱
WHERE 條件敘述(欄位 判斷式 數值)
```

判斷式:

1. 等於: =
2. 大於: >
3. 小於: <
4. 不等於: <>
5. 大於等於: >=
6. 小於等於: <=
7. 集合: IN
8. (Not)BETWEEN A and B、IS (Not) Null

範例:

```mysql
SELECT NAME, TEL, ADDRESS
FROM Students
WHERE SEX="女";
```

