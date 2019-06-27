---
title:  "springBoot 中 查找mybatis中的mapper接口的方法"
categories: 
  - SpringBoot
  - Mybatis
tags:
  - SpringBoot
  - Mybatis
---

## springBoot 中 查找mybatis中的mapper接口的方法

springBoot 中 查找mybatis中的mapper接口的方法: 注解@MapperScan和@Mapper

1. 在spring boot中，首先添加mybatis的starter，此时mybatis的自动配置会生效，mybatis的自动配置里会扫描springboot的有效包路径下的带有@Mapper注解的接口，然后根据里面的mybatis注解生成mapper代理类。

2. 不在SpringBoot主程序中可以扫描的包或者子包下面，可以使用@MapperScan指定需要扫描的路径，配置在主程序上。mybatis配置会扫描指定的路径下的mapper的接口。

两者不可兼得，只能选择其中一种。

两者都是实现了ImportBeanDefinitionRegistrar.registerBeanDefinitions接口。