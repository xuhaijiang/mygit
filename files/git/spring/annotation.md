## spring annotation ##

### @Required ###

应用于 bean 属性的 setter 方法。


### @Autowired @Qualifier @Resource ###

- @Autowired自动装配
- @Qualifier配合@Autowired指定唯一bean
- `@Qualifier("Chinese")`：括号里面为实现类的类名
- `@Autowired(required = false)`:false Spring容器bean未定义不抛出异常

例子：
	
	public interface Man
	{
    	public String name();
	}
	
	@Service
	public class Chinese implements Man
	{
	    public String name()
	    {
	        return "Chinese name";
	    }
	}

	@Service
	public class Japanese implements Man
	{
	    public String name()
	    {
	        return "Japanese name";
	    }
	}
	
	@Service
	public class ManFactory
	{
	    @Autowired
    	@Qualifier("Chinese")
	    private Man man;
	    
	    public String toString()
	    {
	        return man.name();
	    }
	}
	
- @Resource 与 @Autowired类似
	- @Resource后面没有任何内容，默认通过name属性去匹配bean，找不到再按type去匹配
	- 指定了name或者type则根据指定的类型去匹配bean
	- 指定了name和type则根据指定的name和type去匹配bean，任何一个不匹配都将报错
- @Resource 与 @Autowired区别
	- 默认方式：@Autowired按照byType匹配，@Resource按照byName匹配
	- 注解来源：@Autowired是Spring的注解，@Resource是J2EE的注解


例子：

	@Service
	public class World
	{
		@Resource
	    private American american;

	    @Resource(name = "chinese")
	    private Chinese chinese;
	    
	    @Resource(type = Japanese.class)
	    private Japanese japanese;
	    
	    public String toString()
	    {
	        return tiger + "\n" + monkey;
	    }
	}


### @Controller @Service @Repository @Component###

- **@Controller** 用于标注控制层组件
- **@Service** 用于标注业务层组件
- **@Repository** 用于标注数据访问组件
- **@Component** 泛指组件，当组件无法归类时可用


### @Bean ###

表明一个方法产生一个bean是由Spring容器管理。

	@Bean
    public Queue queue() {
        return new ActiveMQQueue("sample.queue");
    }

    @Bean
    public Sender mySender() {
        return new Sender();
    }

### @PostConstruct  @PreDestroy ###

实现初始化和销毁bean之前进行的操作

	@PostConstruct  
    public void  init(){  
        System.out.println("I'm  init  method  using  @PostConstrut...."+message);  
    }  
      
    @PreDestroy  
    public void  dostory(){  
        System.out.println("I'm  destory method  using  @PreDestroy....."+message);  
    } 

