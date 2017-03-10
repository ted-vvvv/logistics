# logistics
xzbto company project Wuliu01
项目学习笔记


lava lang.Thred.join方法
Thread类join()方法重载了3次.分别是：
join()throws InterruptedException;  //无参数的join()等价于join(0),作用是一直等待该线程死亡
join(long millis, int nanos) throws InterruptedException;  //最多等待该线程死亡millis毫秒
join(long millis, int nanos) throws InterruptedException ; //最多等待该线程死亡millis毫秒加nanos纳秒
Waits for this thread to die，如果join的线程不死亡，那么程序就会阻塞在那里。


在Java中使用Set,可以方便地将需要的类型以集合类型保存在一个变量中.主要应用在显示列表.Set是一个不包含重复元素的 collection。更确切地讲，set 不包含满足 e1.equals(e2) 的元素对 e1 和 e2，并且最多包含一个 null 元素。正如其名称所暗示的，此接口模仿了数学上的 set （集合）抽象。


# 对JAVA的集合的理解是想对于数组
    数组是大小固定的，并且同一个数组只能存放类型一样的数据（基本类型/引用类型）
    JAVA集合可以存储和操作数目不固定的一组数据。
    所有的JAVA集合都位于 java.util包中！
    JAVA集合只能存放引用类型的的数据，不能存放基本数据类型.
    JAVA集合主要分为三种类型：
    Set(集)
    List(列表)
    Map(映射)
    Collection 接口
    Collection是最基本的集合接口，声明了适用于JAVA集合（只包括Set和List）的通用方法。
    Set 和List 都继承了Conllection,Map没有
    Collection接口的方法：
    boolean add(Object o)   :向集合中加入一个对象的引用
    void clear()                        :删除集合中所有的对象，即不再持有这些对象的引用
    boolean isEmpty()           :判断集合是否为空
    boolean contains(Object o): 判断集合中是否持有特定对象的引用
    Iterartor iterator()              : 返回一个Iterator对象，可以用来遍历集合中的元素
    boolean remove(Object o):从集合中删除一个对象的引用
    int size()                               :返回集合中元素的数目
    Object[] toArray()                 :返回一个数组，该数组中包括集合中的所有元素
    关于：Iterator() 和toArray() 方法都用于集合的所有的元素，前者返回一个Iterator对象，后者返回一个包含集合中所有元素的数组。
    Iterator接口声明了如下方法：
    hasNext(): 判断集合中元素是否遍历完毕，如果没有，就返回true
    next()       :返回下一个元素
    remove():从集合中删除上一个有next()方法返回的元素。
    Set(集合)：
    Set是最简单的一种集合。集合中的对象不按特定的方式排序，并且没有重复对象。
    Set接口主要实现了两个实现类：
    HashSet : HashSet类按照哈希算法来存取集合中的对象，存取速度比较快
    TreeSet   : TreeSet类实现了SortedSet接口，能够对集合中的对象进行排序。
    Set 的用法：
    存放的是对象的引用，没有重复对象
    Set set=new HashSet();
    String s1=new String("hello");
    String s2=s1;
    String s3=new String("world");
    set.add(s1);
    set.add(s2);
    set.add(s3);
    System.out.println(set.size());//打印集合中对象的数目 为 2。
    Set 的 add()方法是如何判断对象是否已经存放在集合中？
    boolean isExists=false;
    Iterator iterator=set.iterator();
    while(it.hasNext())           {
    String oldStr=it.next();
    if(newStr.equals(oldStr)){
    isExists=true;
    }
    }


# List(列表)：
    List的特征是其元素以线性方式存储，集合中可以存放重复对象。
    List接口主要实现类包括：
    ArrayList() : 代表长度可以改变得数组。可以对元素进行随机的访问，向ArrayList()中插入与
    与删除元素的速度慢。
    LinkedList(): 在实现中采用链表数据结构。插入和删除速度快，访问速度慢。
    对于List的随机访问来说，就是只随机来检索位于特定位置的元素。
    List 的 get(int index) 方法放回集合中由参数index指定的索引位置的对象，下标从“0” 开始。
    最基本的两种检索集合中的所有对象的方法：
    1: 用for循环和get()方法：
    for(int i=0; i<list.size();i++){
    System.out.println(list.get(i));
    }
    2: 使用 迭代器（Iterator）:
    Iterator it=list.iterator();
    while(it.hashNext){
    System.out.println(it.next);
    }
    Map(映射):
    Map 是一种把键对象和值对象映射的集合，它的每一个元素都包含一对键对象和值对象。
    Map没有继承于Collection接口
    从Map集合中检索元素时，只要给出键对象，就会返回对应的值对象。
    Map 的常用方法：
    1 添加，删除操作：
    Object put(Object key, Object value): 向集合中加入元素
    Object remove(Object key):   删除与KEY相关的元素
    void putAll(Map t):   将来自特定映像的所有元素添加给该映像
    void clear(): 从映像中删除所有映射
    2 查询操作：
    Object get(Object key): 获得与关键字key相关的值
    Map集合中的键对象不允许重复，也就说，任意两个键对象通过equals()方法比较的结果都是false.
    但是可以将任意多个键独享映射到同一个值对象上。
    Conllections : 集合实用类
    Conllections提供了供JAVA集合实用的静态方法
    
 
 # java中的基本类型和引用类型
        8种基本类型 
        一、4种整型 
            byte      1字节           -128——127 
            short     2 字节         -32,768 —— 32,767 
            int       4 字节          -2,147,483,648 ——2,147,483,647（超过20亿） 
            long      8 字节   -9,223,372,036,854,775,808——9,223,372,036854,775,807 
            注释：java中所有的数据类所占据的字节数量与平台无关，java也没有任何无符号类型 
        二、 2种浮点类型 
            float    4 字节         32位IEEE 754单精度（有效位数 6 – 7位） 
            double   8 字节         64位IEEE 754双精度（有效位数15位） 
        三、1种Unicode编码的字符单元 
            char    2 字节          整个Unicode字符集 
        四、1种真值类型 
            boolean    1 位             True或者false 
            3种引用类型 
            类class 
            接口interface 
            数组array 
    
# 举例说明：   
     int  a；  
     a=250； //声明变量a的同时，系统给a分配了空间。
     引用类型就不是了，只给变量分配了引用空间，数据空间没有分配，因为谁都不知道数据是什么，整数，字符？我们看一个错误的例子：
     MyDate today；
     today.day = 4； //发生错误，因为today对象的数据空间未分配。
     那我们怎么给它赋值？引用类型变量在声明后必须通过实例化开辟数据空间，才能对变量所指向的对象进行访问。举个例子：
     MyDate today；            //将变量分配一个保存引用的空间
     today = new MyDate（）；     //这句话是2步，首先执行new MyDate（），给today变量开辟数据空间，然后再执行赋值操作
     //引用变量赋值
     MyDate a，b；                    //在内存开辟两个引用空间
     a  =  new MyDate（）；     //开辟MyDate对象的数据空间，并把该空间的首地址赋给a
     b  =  a；                               //将a存储空间中的地址写到b的存储空间中
