# mybatisplus-adapter

Mybatis-Plus Adapter is the Mybatis-Plus adapter for jCasbin, which provides interfaces for loading policies from Mybatis-Plus and saving policies to it.

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
