## Entity

    @Entity
    public class Produit {
       @Id  @GeneratedValue
    	private Long id;
    	private String designation;
    	private double prix;
    	private int qte;
    	
    	public Produit() {
    		// TODO Auto-generated constructor stub
    	}
    
    	public Produit(String designation, double prix, int qte) {
    		super();
    		this.designation = designation;
    		this.prix = prix;
    		this.qte = qte;
    	}
    
    	public Long getId() {
    		return id;
    	}
    
    	public void setId(Long id) {
    		this.id = id;
    	}
    
    	public String getDesignation() {
    		return designation;
    	}
    
    	public void setDesignation(String designation) {
    		this.designation = designation;
    	}
    
    	public double getPrix() {
    		return prix;
    	}
    
    	public void setPrix(double prix) {
    		this.prix = prix;
    	}
    
    	public int getQte() {
    		return qte;
    	}
    
    	public void setQte(int qte) {
    		this.qte = qte;
    	}
    	
    	
    	
    }

## dao

    public interface ProduitRepository extends JpaRepository<Produit, Long>{
    
    }

## controller

    @Controller
    public class ProduitController {
        
    	@Autowired
    	private ProduitRepository produitr;
    	
    	@RequestMapping(value="/index")
    	public String index(Model model)
    	{
    		List<Produit> listeP=produitr.findAll();
    		model.addAttribute("listProduits",listeP);
    		return "produits";
    	}
    	
    	@RequestMapping(value="/add",method=RequestMethod.GET)
    	public String addP(Model model)
    	{
    		model.addAttribute("produit", new Produit());
    		
    		return "FromProduit";
    		
    	}
    	
    	@RequestMapping(value="/save",method=RequestMethod.POST)
    	public String save(Model model,Produit p)
    	{
    		produitr.save(p);
    		return "redirect:/index";
    		
    	}
    	
    	@RequestMapping(value="/delete",method=RequestMethod.GET)
    	public String delete(Long id)
    	{
    		produitr.deleteById(id);
    		
    		return "redirect:/index";
    		
    	}
    	
    	@RequestMapping(value="/chercher")
    	public String chercher(Model model)
    	{
    		
    		return "produits";
    	}
    }

## main

    @SpringBootApplication
    public class SpringMvc1Application {
    
    	public static void main(String[] args) {
    		ApplicationContext ctx=SpringApplication.run(SpringMvc1Application.class, args);
    		ProduitRepository produitdao= ctx.getBean(ProduitRepository.class);
    		
    		
    		produitdao.save(new Produit("zefz",3.3,1));
    		produitdao.save(new Produit("deaed",3.111,1));
    		produitdao.save(new Produit("erzeed",5.3,3));
    	}
    
    }
