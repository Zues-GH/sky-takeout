+++
title = 'sky-takeout'
weight = 6
+++

## 技术栈
Java 17
Spring Boot 3.x
Spring MVC
Spring Data JPA
MySQL 8.x
Maven

### 项目结构
```
src/main/java/com/takeout/
├── config/        # 配置类
├── constant/      # 常量类
├── controller/    # 控制层
├── dto/           # 数据传输对象
├── entity/        # 实体类
├── exception/     # 异常处理
├── mapper/        # MyBatis映射接口
├── repository/    # JPA仓库接口
├── service/       # 服务层
└── SkyTakeoutApplication.java
```

### Nginx
Nginx目录必须放在没有中文的目录才能正常运行