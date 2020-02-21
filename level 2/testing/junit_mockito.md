1)

    @RunWith(SpringRunner.class)
    
    public class SpringAngularGestionContactApplicationTests {
    
    	@MockBean
    	ContactRepository cr;
    	
    	
    	@Autowired
    	private ContactService contactservice;
    	
    	@TestConfiguration
    	static class ContactServiceContextConfiguration{
    		@Bean
    		public ContactService contactservice()
    		{
    			return new ContactService();
    		}
    	}
    	
    	@Test
    	public void whenFindGetAll() {
    		Contact  c1=new Contact("dffd","qdfsd", new Date(), "sdfsqd@gmail.com", 1234342); 
    		Contact  c2=new Contact("dfzefd","qdfzersd", new Date(), "sdfezrsqd@gmail.com", 134134); 
    		List<Contact>  data=Arrays.asList(c1,c2);
    		
    		BDDMockito.given(cr.findAll()).willReturn(data);
    		assertThat(contactservice.getAll()).hasSize(2).contains(c1,c2);
    	}
    	
    	
    	
    }

2)

    @RunWith(SpringRunner.class)
    @SpringBootTest(webEnvironment = SpringBootTest.WebEnvironment.RANDOM_PORT)
    @AutoConfigureMockMvc
    public class TestController {
    
    	@Autowired
    	MockMvc  mock;
    	
    	@MockBean
    	private ContactService contactservice;
    	
    	@Test
      public void getAllTest() throws Exception
      {
    	 // mock.perform(MockMvcRequestBuilders.get("/contacts")).andExpect(MockMvcResultMatchers.status().isOk());
    		
    		Contact  c1=new Contact("Anis","qdfsd", new Date(), "sdfsqd@gmail.com", 1234342); 
    		Contact  c2=new Contact("dfzefd","qdfzersd", new Date(), "sdfezrsqd@gmail.com", 134134); 
    		List<Contact>  data=Arrays.asList(c1,c2);
    		BDDMockito.given(contactservice.getAll()).willReturn(data);
    		//assertThat(contactservice.getAll()).hasSize(2).contains(c1,c2);
    		
    		
    		mock.perform(MockMvcRequestBuilders.get("/contacts").contentType(MediaType.APPLICATION_JSON))
    		.andExpect(MockMvcResultMatchers.status().isOk())
    		.andExpect(MockMvcResultMatchers.jsonPath("$[0].nom", equalTo(c1.getNom())));
    		
    		
    		
      }
    	
    	@Test
    	public void create() throws Exception
    	{
    		Contact  c1=new Contact("Anis","qdfsd", new Date(), "sdfsqd@gmail.com", 1234342);
    		BDDMockito.given(contactservice.save(Mockito.any(Contact.class))).willReturn(c1);
    		ObjectMapper om=new ObjectMapper();
    		mock.perform(MockMvcRequestBuilders.post("/contacts").content(om.writeValueAsString(c1)).contentType(MediaType.APPLICATION_JSON))
    		.andExpect(MockMvcResultMatchers.status().isCreated())
    		.andExpect(MockMvcResultMatchers.jsonPath("$.nom", is(c1.getNom())));
    		
    		
    	}
    }
