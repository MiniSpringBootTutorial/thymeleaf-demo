Thymeleaf Demo
===================================
Thymeleaf is a new template engine. http://www.thymeleaf.org/index.html

### Features

* Spring Boot Demo
* Template Engine Demo
* Email Template Demo


### spring integration

样例： https://github.com/thymeleaf/thymeleafexamples-springmail


     <bean id="emailTemplateResolver" class="org.thymeleaf.templateresolver.ClassLoaderTemplateResolver">
         <property name="prefix" value="mail/" />
         <property name="templateMode" value="HTML5" />
         <property name="characterEncoding" value="UTF-8" />
         <property name="order" value="1" />
         <!-- Template cache is true by default. Set to false if you want -->
         <property name="cacheable" value="true" />
     </bean>

     <!-- THYMELEAF: Template Engine (Spring3-specific version) -->
     <bean id="templateEngine" class="org.thymeleaf.spring3.SpringTemplateEngine">
         <property name="templateResolvers">
            <set>
              <ref bean="emailTemplateResolver" />
            </set>
         </property>
     </bean>
     
   
### Docker编译

* 命令行:

     $ docker run -it --rm --name thymeleaf-demo-project -v "$(pwd)":/usr/src/app -v "$HOME/.m2":/root/.m2 -w /usr/src/app maven:3.3.3-jdk-8 mvn clean compile

* docker-compose

     $ docker-compose up --abort-on-container-exit && docker-compose rm --force --all

    