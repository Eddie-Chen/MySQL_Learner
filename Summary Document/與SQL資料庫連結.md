# 與SQL資料庫連結



透過PHP與資料庫連結，順序如下:

1. 資料庫系統連線 mysql_connect()
2. 選擇資料庫 mysql_select_db()
3. 送出SQL命令 mysql_query()
4. 取出查詢結果 mysql_fetch_row()
5. 關閉連線 mysql_close()



1. `$db_link = mysql_connect("localhost","root","123456")`

   * 要求連結資料庫伺服器系統。
   * 透過網路連結到資料庫系統，如成功則傳回一個整數型態的連線識別碼  $db_link，否則傳回 0。
   * localhost 表示資料庫伺服器的主機位址(IP 或  URL  位址亦可)，與連線要求的使用者名稱(root)與密碼(123456)

2. $select_db=mysql_select_db(course_db)`

   * 選擇資料庫
   * 一個伺服器系統內大多會被建立多個資料庫，可利用此函數選擇其中某一個資料庫(如:course_db)
   * 成功則傳回一個整數的識別碼存入  $select_db，否則傳回 0。

3. `$sql_ID=mysql_query($sql_query)`

   * 送出  SQL  查詢語言  $sql_query，
   * 先將查詢語句存入  $sql_ID  內。
   * 成功則傳回一個整數識別碼給  $result，否則傳回  0  。

4. `$row=mysql_fetch_row($sql_ID)`

   * 擷取查詢結果($sql_ID) 的一列(row)資料，
   * 並將游標往下移，將擷取結果傳回  $row  內，
   * 如傳回空值表示已擷取完或沒有查詢成功。

5. `mysql_close($db_link)`

   * 要求與資料庫伺服器之間連線中斷。

   ​