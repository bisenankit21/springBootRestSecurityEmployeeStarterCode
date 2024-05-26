Given Access:
UserDetails john= 
                username("john")
                password("{noop}test123")
                roles("EMPLOYEE")
            
          mary=
            .username("mary")
            .password("{noop}test123")
             .roles("EMPLOYEE","MANAGER")
               
         susan= 
             .username("susan")
             .password("{noop}test123")
             .roles("EMPLOYEE","MANAGER","ADMIN")


    To access use this info
     .requestMatchers(HttpMethod.GET,"/api/employees").hasRole("EMPLOYEE")
     .requestMatchers(HttpMethod.GET,"/api/employees/**").hasRole("EMPLOYEE")
     .requestMatchers(HttpMethod.POST,"/api/employees").hasRole("MANAGER")
     .requestMatchers(HttpMethod.PUT,"/api/employees").hasRole("MANAGER")
     .requestMatchers(HttpMethod.DELETE,"/api/employees/**").hasRole("ADMIN")
              
