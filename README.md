# [Database](https://github.com/zhengjiaao/Database/releases/download/v1.0.0/Database.zip)  
常用数据库自动化流程操作    
Database 数据库自动化操作手册 | zheng jiaao   

目录    
数据库自动化操作手 册.....................................................................................................................................................................................1   
一、主要优点.................................................................................................................................................................................................1  
二、适配数据库............................................................................................................................................................................................2  
三、目录文件说明  .......................................................................................................................................................................................3  
四、使用前注意事项...................................................................................................................................................................................3   
五、使用示例.................................................................................................................................................................................................4  
六、定时备份数据库...................................................................................................................................................................................4 
  
一、主要优点  
1、操作人员不再通过 cmd 或 sql 命令方式进行繁杂的数据库操作，配置方式可以更高效、简单化操作数据库  
2、避免操作人员使用错误的 cmd 或 sql 命令对数据库错误操作情况  
3、配置方式对比 cmd、sql 命令方式操作数据库，配置方式让操作人员对操作数据库的恐惧感减少  
4、Postgresql 库 创建操作 - 不需要再手动创建表空间目录，会自动生成表空间目录  
5、Postgresql 库 创建操作 - 自动流程创建库、用户、模式，并给用户授权  
6、Postgresql 库 还原操作 – 支持还原非同源库，例：将 A 库还原到 B 库情况 – 支持库名称不一致情况  
7、Postgresql 库 删除操作 – 自动化流程删除库、删除模式、删除用户、删除表空间  
8、Oracle 库 创建操作 – 自动化流程创建用户、schema、表空间，给用户授权等操作   
9、Oracle 库 备份操作 – 支持配置备份文件路劲，将库备份到指定路径下，默认备份到当前磁盘 
10、Oracle 库 备份操作 – 支持自动生成备份文件名称格式为：“用户-日期-表空间-expdp.sql”  
11、Oracle 库 还原操作 – 支持空表还原   
12、Oracle 库 还原操作 - 支持还原非同源库，例：将 A 库还原到 B 库情况 – 支持表空间、用户不一致情况  
13、Oracle 库 还原操作 - 支持还原备份库会覆盖现有库    
14、Oracle 库 还原操作 - 默认开启多线程还原库，更高效、更加快速还原备份库    
15、Oracle 库 删除操作 – 自动化流程删除用户、schema、表空间     
16、Mongodb 库 创建操作 - 不需要进行多条 cmd 命令创建流程，自动化创建库、用户、给用户授权等操作   
17、Mongodb 库 创建操作 – 默认插入测试数据，为了支持工具“Robo 3T”连接库   
18、Mongodb 库 创建操作 – 避免创建库不在权限认证库(admin)中，连接时提示权限验证失败情况    
19、Mongodb 库 还原操作 – 支持还原非同源库，例：将 A 库还原到 B 库情 – 支持库名不一致情况    
20、Mongodb 库 删除操作 – 自动化流程删除库、删除用户   
  
二、适配数据库 
适配库：oracle、mongodb、postgresql 、mysql 等库部分常用操作 
MONGODB 库操作：  
创建库：创建库、创建用户、用户授权 
删除库：删除库、删除用户  
备份库：将库备份到指定的全局备份路径中，备份完成会提示备份文件路径位置 
1． 支持自动生成备份文件格式：“数据库_日期 _mongodump.gz”  
还原库：不覆盖现有库中已存在表的数据-若现有库 A 表存在，不会还原备份库 A 表数据，若现有库 B 表不存在，  
则会还原备份库 B 表数据 。 强烈推荐-删除现有库，重新创建库再还原备份库  
1． 支持非同源库还原情况，例：将 A 库还原到 B 库情况 – 支持数据库名不一致情况  
2． 支持 mongodb 是否开启权限认证验证备份方式  
ORACLE 库操作： 
创建库：创建用户、创建 schema、创建表空间  
删除库：删除用户、创建 schema、删除表空间  
备份库：将库备份到指定的全局备份路径中，备份完成会提示备份文件路径位置   
1． 支持自动生成备份文件格式：“用户-日期-表空间-expdp.sql”   
2． 支持配置备份文件存储路径(配置-全局备份路径)  
3． 支持非同源库还原情况，例：将 A 库还原到 B 库情况 – 支持数据库名不一致情况  
还原库：覆盖现有库中已存在表的数据-若现有库 A 表存在，会被替换为还原库 A 表数据   
  
支持还原备份库会覆盖现有库   
支持空表还原  
不再手动将备份拷贝到用户表空间进行还原   
支持非同源库还原情况，例：将 A 库还原到 B 库情况 – 支持表空间, 用户都不一致情况   
默认开启多线程还原库，更高效、更加快速还原备份库    
POSTGRESQL 库操作：   
创建库：创建库、创建用户、创建表空间、创建模式   
删除库：删除库、删除用户、删除表空间、删除模式   
备份库：将库备份到指定的全局备份路径中，备份完成会提示备份文件路径位置   
1． 支持自动生成备份文件格式：“数据库_日期_pg_dump. sql”   
还原库：不覆盖现有库中已存在表的数据-若现有库 A 表存在，不会还原备份库 A 表数据，若现有库 B 表不存在，
则会还原备份库 B 表数据。强烈推荐-删除现有库，重新创建库再还原备份库  
支持非同源库还原情况，例：将 A 库还原到 B 库情况 – 支持库名称不一致情况  
MYSQL 库操作：  
创建库：创建库、创建用户  
删除库：删除库、删除用户  
备份库：将库备份到指定的全局备份路径中，备份完成会提示备份文件路径位置   
支持自动生成备份文件格式：“数据库_日期_pg_ mysqldump. sql”    
还原库：覆盖现有库中已存在表的数据-若现有库 A 表存在，会被替换为还原库 A 表数据     

三、目录文件说明    
1、bin 目录：可编辑、可执行文件，操作人员进行修改配置和操作的可执行文件  
2、conf 目录：可编辑 “conf/GlobalConfiguration.bat”全局配置文件(支持配置全局备份路径)  
3、exefile 目录：不可编辑、不可执行文件  
4、CleanCache.exe 清理缓存：日志文件、临时文件、临时文件夹等，不会丢失任何数据   
5、Uninstall_Database.exe 卸载 Database：不能从“回收站“恢复，不会丢失已备份数据   
6、Update-Database.exe 下载最新程序包(可选-安装程序)，安装程序导致 bin 目录配置数据丢失    
w：安装，q：退出(需手动安装程序)    
  
四、使用前注意事项   
1、 建议将 Database 脚本目录放置在“数据库服务器”上，避免某些命令不能执行成功   
2、 Database 目录可放置任何磁盘位置(不推荐中文路径)上，推荐放到磁盘空间较大的位置，因备份文    
件默认存储位置会放置在 Database 文件夹所在的磁盘上    
3、 mongodb、postgresql 安装的 bin 目录配置到 conf/GlobalConfiguration.bat“全局环境变量”  
可修改全局备份存储路径、全局环境变量等全局配置信息     
4、exe 执行脚本被 360 拦截隔离删除(不提示)，需配置信任目录   
  
五、使用示例    
1、进入 Database\bin 目录 , 操作人员只需要对 bin 目录下的 bat 文件内容进行修改、“双击”运行  
2、用编辑器(Notepad++)打开 “Mongodb_Creat_UserAndDatabase.bat” 创建新的 mongo 库  
3、修改参数 “rem 参数-start”---》 “rem 参数-end” 中间为要修改的参数值，然后保存  
4、双击运行“Mongodb_Creat_Database.bat” 脚本，进行创建 Mongo 库和用户   
5、验证：打开 mongo 连接工具(Studio3T.exe)，使用创建的用户和库进行连接 mongo 库  
  
六、定时备份数据库   
Windwos 系统自带 “任务计划程序”，可做定时任务。   
1、打开“任务计划程序”    
方式一：搜索-->任务计划程序   
方式二：计算机管理-->任务计划程序    
2、任务计划程序库   
右击 “任务计划程序库” -->新文件夹 (Database)   
3、创建任务    
右击 “Database” 创建任务--任务名称(PostgreSQL_Backup)   
4、任务修改  
右击任务->属性    
5、任务测试    
右击任务-->"运行"        

**文件下载：**   
[Database.zip](https://github.com/zhengjiaao/Database/releases/download/v1.0.0/Database.zip)
