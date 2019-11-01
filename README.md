本项目为 .net framework4.5 wpf 项目
创建工具：Visual Studio 2019 （使用低于此版本的VS可能出现异常情况）
用于测试 Sqlite 的 CodeFirst使用方式

测试步骤：
1 创建 .net framework4.5 wpf 项目
2 打开程序包管理控制台
3 在包管理控制台执行命令：Install-Package System.Data.Sqlite
4 在包管理控制台执行命令：Install-Package Sqlite.CodeFirst

4.1（补充） 在app.config 添加连接串配置：
<add name="default" connectionString="Data Source=local.db;" providerName="System.Data.SQLite"/>
并添加Provider配置:
<provider invariantName="System.Data.SQLite" type="System.Data.SQLite.EF6.SQLiteProviderServices, System.Data.SQLite.EF6" />

5 创建类MyDbContext （内容如代码所示）
6 创建类MyInitializer （内容如代码所示）
7 创建Customer类及对应的EF配置类CustomerMap
8 在MainWindow.cs中调用MyDbContext.PreApplicationStartMethod(); 运行程序，数据库将会自动创建。
9 创建User及对用EF配置UserMap。运行程序，执行MyDbContext.PreApplicationStartMethod(); 后将会自动重新创建数据库。
