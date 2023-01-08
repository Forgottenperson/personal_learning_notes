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
    * Case when end

        ```
        select stock_name,sum(case
        when operation='Sell' then price
        when operation='Buy' then -price
        End) as capital_gain_loss  
        from Stocks 
        group by stock_name 
        ```

    * UPPER
    * LOWER
    * CONCAT
    * dateDiff
        * Year
        * Month
    * HAVING
        * 取代where 可以使用 aggregate function 進行條件查詢
    
    * FOR XML 
        * PATH

    * stuff 取代字串
        * STUFF ( character_expression , start , length , replaceWith_expression )  
    * group_concat

    ```
    select sell_date,Count(distinct product) num_sold ,group_concat(distinct product) products

    from Activities

    group by sell_date

    order by sell_date
    ```

* FROM
    * From可以接收多個來源當作資料查詢
    * From dataA as a,dataB as b

        as 可以幫資料來源取短名
        
        再搭配where可以做到關聯查詢
        
        where a.title=b.title

* WHERE 
    * like
        * 萬用字元(非正規表示式)

        ```
        % 代表 0~* 字母
        _ 代表 1個字母 空格不算

        使用上需注意表示方式

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
    須注意 not in null 是不正確的寫法
    null 是無法被比較的 其他跟 null 比較會永遠false

    * Between

    * is

    ```
    is null
    ```
    
* Orderby

* Groupby
    * 若指令中有不只一個相同內容，並且需要使用 SUM() 之類的數值去運算的話則需要使用此指令來做分群運算


* INSERT table (scheme) values(N'1123')

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

* Join
    * Left Join
        * on 跟where一樣屬於條件判斷過濾 差別在於他是先過濾再合併
    * Right Join
        * on 跟where一樣屬於條件判斷過濾 差別在於他是先過濾再合併

* UNION 

    ```
    select employee_id from Employees where employee_id not in ( select employee_id from Salaries)

    union

    select employee_id from Salaries where employee_id not in ( select employee_id from Employees)

    order by employee_id
    ```

    ```
    select id ,"Root" type from Tree where p_id is null

    union

    select id ,"Inner" type from Tree where id in(select p_id from Tree) and p_id is not null

    union

    select id ,"Leaf" type from Tree where id not in(select DISTINCT p_id from Tree where p_id is not null) and p_id is not null
    ```

* Intersect
* Except


* SSMS + SQL Server Express
    * 預存程序(類似常數)
        * create PROCEDURE
            * exec (CTRL+Shift+R 刷新)
        * alter PROCEDURE 
        
        ```
        create PROCEDURE db.functionName
	        @vari nchar(1)
        as
        begin
	        select * from db.table where name like @vari+'%'
        end

        ```
    * create/alter trigger
        * SQL 資料庫變動事件

            * inserted 修改後
            * deleted 修改前

        ```
        create TRIGGER dbo.membertrigger
            ON  dbo.member
            after UPDATE -- 觸發事件
        AS 
        BEGIN
            IF UPDATE(id) or UPDATE(name) or UPDATE(sex) or UPDATE(age)
            BEGIN
                select * from deleted;
            END
        END
        ```


* DECLARE 宣告



* sp_executesql 


* 字串中要加入單引號需在前面追加一個單引號，如" '' "
