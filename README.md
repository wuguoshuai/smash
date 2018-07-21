# smash

  这是一个关于mybatis的自动生成工具，一个可视化的工具，支持生成实体类，service，controller，mapper，mapperXML的工具。
  
  环境要求：JDK1.8及以上版本、SpringBoot 1.5.X以上版本的项目
  
  首先，你需要下载Auto-Code文件夹或者Auto-Code.zip自行解压，里面会有以下文件：
  # auto-code-1.0.jar
  # mybatis-support-1.0.jar
  # start.bat
  # stop.bat
  # 使用说明.txt
  
  先声明该工具的具体功能：
  1. 生成mybatis的相关文件，提升开发效率。
  
  2. 提供一些基础的mapper方法，可以直接使用。
  
  3. 对每一个实体提供通用的SQL构造类，并且提供通用接口，生成的service类都继承了该类（CurrencyService），两者配合使用，可以极大的减少XML文件中的代码数量，也就是通过Java代码去执行相关操作，通用接口包括4个方法：
  （1）<T> ArrayList<T> currencySelectSql(@Param("sql")String sql,@Param("resultType")Class resultType)；
  （2）int currencyInsertSql(@Param("sql")String sql); 
  （3）int currencyUpdateSql(@Param("sql")String sql); 
  （4）int currencyDeleteSql(@Param("sql")String sql); 
  顾名思义，currencySelectSql为查询操作使用的方法，其余方法以此类推，其中最需要注意的是currencySelectSql方法中的第二个参数，该参数相当于XML文件中每一个语句的resultType，也就是说，该操作不仅仅支持单表操作，还可以配合SQL构造类，让你可以执行更复杂的SQL并自行指定返回值类型，你只需传入返回类型的class即可。（在使用该通用接口时，你应当将mybatis-support-1.0.jar打入你本地仓库，然后引入项目中，该插件是必须的，否则项目将会报错。）
  
  4.该工具为可视化工具，双击运行start.bat即可启动程序，打开浏览器，访问 http://localhost:8888/auto ，根据页面提示，填写相关信息，然后点击一键生成即可，注意，当前额外配置功能不支持批量生成模式。
  
  5.生成的实体类文件中，以添加了@Alias注解，请自行打开springboot项目中的mybatis关于别名的设置，将这些实体类纳入管理中。 
  
  6.实体类提供复杂构造API，在构造实体时可以使用链式调用，将构造代码简洁化，例如，有一个实体CatUser，构造实体对象时可以直接使用CatUser.builder()方法，紧接着可以直接通过set方法去链式注入属性值，最后再调用build()即可返回对象。
  
  7.更多的详细信息可以查阅使用说明。
  
  
  如果在使用过程中发现了BUG或者问题，可以给我留言。
    
