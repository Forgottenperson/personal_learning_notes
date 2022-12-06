* SELECT
    * 可再欄位後邊新增其他名稱來當作新的欄位名稱
    * Distinct 過濾欄位內重複資料

    * SUM() 數值總和
    * MAX()
    * MIN()
    * AVG()
    * COUNT()
    * SUBSTR(a.name,1,1)
    * Length()
    * IF(500<1000, "YES", "NO")
    

* FROM
    * From可以接收多個來源當作資料查詢
    * From dataA as a,dataB as b

        as 可以幫資料來源取短名
        
        再搭配where可以做到關聯查詢
        
        where a.title=b.title

        where 再其後面可以加上"(+)"來顯示該表格其他未顯示內容

        where a.title=b.title (+)

* WHERE 
    * like
        * 萬用字元(非正規表示式)

        ```
        % 代表 0~* 字母
        _ 代表 1個字母 空格不算

        ```

    * AND/OR

    * IN/Not in

    用子查詢過濾出未曾訂貨過客戶

    ```
    SELECT name Customers 

    From Customers

    where Customers.id not in(

        select customerId from Orders 

    )
    ```

    * Between

    * is

    ```
    is null
    ```
    
* Orderby

* Groupby
    * 若指令中有不只一個相同內容，並且需要使用 SUM() 之類的數值去運算的話則需要使用此指令來做分群運算




* UPDATE 

    ```
    UPDATE table_name
    SET column1 = value1, column2 = value2, ...
    WHERE condition; 

    update Salary
    set sex=if(sex='m','f','m')
    ```

* DELETE

    ```
    DELETE FROM table_name WHERE condition;


    Delete a from Person as a,Person as b
    where a.email=b.email and a.id>b.id

    ```