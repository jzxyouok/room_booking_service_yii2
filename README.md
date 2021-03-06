<p align="center">
    <a href="https://www.netsurfing.science" target="_blank">
        <img src="http://www.nankai.edu.cn/_upload/tpl/00/3f/63/template63/images/logo.png" height="100px">
    </a>
    <h1 align="center">学生活动中心房间预约及管理系统</h1>
    <br>
</p>

本项目为南开大学学生活动中心房间预约系统（学生端）以及一个对应的管理系统（教师端）。

项目基于<a href="https://www.yiiframework.com/">Yii2</a>框架制作。

部署步骤
-------------------
1. 使用`git clone`命令将网站文件获取至网站部署目录。
2. 进入网站根目录， 运行`composer install`命令安装运行环境。
3. 在根目录下执行`php init`（Linux）或`init.bat`（Windows），选择运行配置。
4. 将前台网站根目录设置为`frontend/web`，后台网站根目录设置为`backend/web`，入口文件为`index.php`。
5. 确保php允许`open_basedir`。
6. 确保网站根目录被赋予了足够的权限。
7. 根据网络服务器的类型配置URL转写。Apache2的配置如下：
```angular2html
RewriteEngine on
# If a directory or a file exists, use it directly
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
# Otherwise forward it to index.php
RewriteRule . index.php
```

目录结构
-------------------

```
common
    config/              contains shared configurations
    mail/                contains view files for e-mails
    models/              contains model classes used in both backend and frontend
    tests/               contains tests for common classes    
console
    config/              contains console configurations
    controllers/         contains console controllers (commands)
    migrations/          contains database migrations
    models/              contains console-specific model classes
    runtime/             contains files generated during runtime
backend
    assets/              contains application assets such as JavaScript and CSS
    config/              contains backend configurations
    controllers/         contains Web controller classes
    models/              contains backend-specific model classes
    runtime/             contains files generated during runtime
    tests/               contains tests for backend application    
    views/               contains view files for the Web application
    web/                 contains the entry script and Web resources
frontend
    assets/              contains application assets such as JavaScript and CSS
    config/              contains frontend configurations
    controllers/         contains Web controller classes
    models/              contains frontend-specific model classes
    runtime/             contains files generated during runtime
    tests/               contains tests for frontend application
    views/               contains view files for the Web application
    web/                 contains the entry script and Web resources
    widgets/             contains frontend widgets
vendor/                  contains dependent 3rd-party packages
environments/            contains environment-based overrides
```
