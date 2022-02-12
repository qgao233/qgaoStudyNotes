## AOP

AOP功能可以通过JavaSE动态代理和字节码生成实现

spring的AOP功能是通过**JavaSE动态代理**和**cglib**实现的

* JavaSE动态代理：一个类需要实现了某个接口，才能在运行期间动态的构造这个接口的实现对象，通过反射实现。

* cglib：本身是动态字节码生成工具，可以对没有实现业务接口的对象进行增强。


<aop:config>是Spring AOP配置的根元素，其中有个属性为proxy-target-class

如果为true,则使用cglib生成代理对象，相反为false，

>默认如果目标类实现了接口，选择用jdk动态代理，没有实现接口就采用cglib生成一个被代理对象的子类来作为代理。

可以用注解配置Spring AOP
