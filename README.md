# mybatisplus-adapter
[![codebeat badge](https://codebeat.co/badges/998c8e12-ffdd-4196-b2a2-8979d7f1ee8a)](https://codebeat.co/projects/github-com-jcasbin-mybatisplus-adapter-master)
[![build](https://github.com/jcasbin/mybatisplus-adapter/actions/workflows/ci.yml/badge.svg)](https://github.com/jcasbin/mybatisplus-adapter/actions)
[![codecov](https://codecov.io/github/jcasbin/mybatisplus-adapter/branch/master/graph/badge.svg?token=4YRFEQY7VK)](https://codecov.io/github/jcasbin/mybatisplus-adapter)
[![javadoc](https://javadoc.io/badge2/org.casbin/mybatisplus-adapter/javadoc.svg)](https://javadoc.io/doc/org.casbin/mybatisplus-adapter)
[![Maven Central](https://img.shields.io/maven-central/v/org.casbin/mybatisplus-adapter.svg)](https://mvnrepository.com/artifact/org.casbin/mybatisplus-adapter/latest)
[![Discord](https://img.shields.io/discord/1022748306096537660?logo=discord&label=discord&color=5865F2)](https://discord.gg/S5UjpzGZjN)

Mybatis-Plus Adapter is the Mybatis-Plus adapter for jCasbin, which provides interfaces for loading policies from Mybatis-Plus and saving policies to it.

## Installation

    <dependency>
        <groupId>org.casbin</groupId>
        <artifactId>mybatisplus-adapter</artifactId>
        <version>1.0.0</version>
    </dependency>


## Example

    package com.company.example;
    
    import org.casbin.jcasbin.main.Enforcer;
    import org.casbin.jcasbin.util.Util;
    import org.casbin.adapter.MybatisPlusAdapter;
    
    public class Example {
        public void test() {
            Enforcer e = new Enforcer("examples/rbac_model.conf", "examples/rbac_policy.csv");
        
            String driver = "com.mysql.cj.jdbc.Driver";
            String url = "jdbc:mysql://localhost:3306/casbin";
            String username = "YourUsername";
            String password = "YourPassword";
            
            MybatisAdapter a = new MybatisAdapter(driver, url, username, password, true);
        
            // Save policy to DB
            a.savePolicy(e.getModel());
        
            // Load policy from DB
            a.loadPolicy(e.getModel());
        }
    }

## Getting Help

- [jCasbin](https://github.com/casbin/jcasbin)

## License

This project is under Apache 2.0 License. See the [LICENSE](LICENSE) file for the full license text.
