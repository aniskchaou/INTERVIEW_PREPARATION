## Spring Security
**HelloResource** 

    @RestController
        public class HelloResource {
        
        	@RequestMapping("/hello")
        	public String hello()
        	{
        		return "Hello World!";
        	}
        }

**MyUserDetailsService**

    @Service
    public class MyUserDetailsService implements UserDetailsService {
    
    	@Override
    	public UserDetails loadUserByUsername(String username) throws UsernameNotFoundException {
    		// TODO Auto-generated method stub
    		return new User("admin","admin",new ArrayList<>());
    	}
    
    }

**SecurityConfigurer** 

    @EnableWebSecurity
    public class SecurityConfigurer extends WebSecurityConfigurerAdapter {
    	@Autowired
    	 MyUserDetailsService myUserDetailsService;
    	
    	@Override
    protected void configure(AuthenticationManagerBuilder auth) throws Exception {
    	auth.userDetailsService(myUserDetailsService);
    }
    	
    	
    	@Bean
    	public PasswordEncoder passwordencoder()
    	{
    		return NoOpPasswordEncoder.getInstance();
    	}
    }
