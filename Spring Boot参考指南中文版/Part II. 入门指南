如果你刚刚开始使用Spring Boot，这是你的一部分内容！ 在这里我们将会回答一些基本的what?”, “how?” 和 “why?”的问题。 在这里你会找到一个详细的介绍Spring Boot和安装说明。 然后，我们将构建我们的第一个Spring Boot应用程序，并讨论一些核心原则。

8. Spring Boot 介绍

Spring Boot可以基于Spring轻松创建可以“运行”的、独立的、生产级的应用程序。 对Spring平台和第三方类库我们有一个自己看法，所以你最开始的时候不要感到奇怪。 大多数Spring Boot应用程序需要很少的Spring配置。

您可以使用Spring Boot创建可以使用java -jar或传统 war 包部署启动的Java应用程序。 我们还提供一个运行“spring脚本”的命令行工具。

我们的主要目标是： 
* 为所有的Spring开发者提供一个更快，更广泛接受的入门体验。 
* Be opinionated out of the box, but get out of the way quickly as requirements start to diverge from the defaults. 
* 提供大量项目中常见的一系列非功能特征（例如嵌入式服务器，安全性，指标，运行状况检查，外部化配置）。 
* 绝对没有代码生成，也不需要XML配置。

9. 系统要求

默认情况下，Spring Boot 1.5.2.RELEASE需要Java 7和Spring Framework 4.3.7.RELEASE或更高版本。 您可以进行一些其他配置在Java 6上使用Spring Boot。 有关详细信息，请参见第84.11节“如何使用Java 6”。 为Maven（3.2+）和Gradle 2（2.9或更高版本）和3提供了显式构建支持。

虽然您可以在Java 6或7上使用 Spring Boot，但我们通常推荐Java 8。
9.1 Servlet容器

以下嵌入式servlet容器可以直接使用：

名称	Servlet 版本	Java 版本
Tomcat 8	3.1	Java 7+
Tomcat 7	3.0	Java 6+
Jetty 9.3	3.1	Java 8+
Jetty 9.2	3.1	Java 7+
Jetty 8	3.0	Java 6+
Undertow 1.3	3.1	Java 7+
您还可以将Spring Boot应用程序部署到任何兼容Servlet 3.0+ 的容器中。

10. 安装 Spring Boot

Spring Boot可以与“经典(classic)”Java开发工具一起使用或作为命令行工具安装。 无论如何，您将需要Java SDK v1.6或更高版本。 在开始之前检查当前的Java安装：

$ java -version
1
如果您是Java开发的新手，或者您只想尝试一下 Spring Boot，您可能需要首先尝试使用 Spring Boot CLI，如果想正式使用Spring Boot，请阅读“经典(classic)”安装说明。

虽然Spring Boot 与Java 1.6兼容，但我们建议使用最新版本的Java。

10.1 Java开发程序员安装说明

Spring Boot的使用方式与标准Java库的使用相同，只需在类路径中包含适当的spring-boot-*.jar文件。Spring Boot不需要任何特殊的集成工具，所以可以使用任何IDE或文本编辑器进行开发；并且Spring Boot 应用程序没有什么特殊的地方，因此您可以像其他Java程序一样运行和调试。虽然您可以直接复制Spring Boot 的jar包，但我们通常建议您使用依赖关系管理的构建工具（如Maven或Gradle）。

10.1.1 Maven安装

Spring Boot 兼容 Apache Maven 3.2。 如果您还没有安装Maven，可以按照 https://maven.apache.org/ 上的说明进行安装。

在许多操作系统上，Maven可以通过软件包管理器进行安装。 如果您是OSX Homebrew用户，请尝试使用命令：brew install maven。 Ubuntu用户可以运行命令：sudo apt-get install maven。

Spring Boot 依赖 org.springframework.boot groupId。通常，您的Maven POM文件将从 spring-boot-starter-parent 项目继承，并声明一个或多个“启动器(启动器)”的依赖关系。Spring Boot还提供了一个可选的Maven插件来创建可执行的jar包。

典型的pom.xml文件：

    <?xml version="1.0" encoding="UTF-8"?>
    <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.example</groupId>
    <artifactId>myproject</artifactId>
    <version>0.0.1-SNAPSHOT</version>

    <!-- Inherit defaults from Spring Boot -->
    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>1.5.2.RELEASE</version>
    </parent>

    <!-- Add typical dependencies for a web application -->
    <dependencies>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
    </dependencies>

    <!-- Package as an executable jar -->
    <build>
        <plugins>
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
            </plugin>
        </plugins>
    </build>
    </project>

spring-boot-starter-parent是使用Spring Boot的一个很好的方式，但它并不是所有的时候都适合。有时您可能需要从不同的父POM继承，或者您可能不喜欢我们的默认设置。 请参见第13.2.2节“使用不带父POM的Spring Boot”作为使用导入作用域(import scope)的替代解决方案。
10.1.2 Gradle 安装

Spring Boot 兼容 Gradle 2（2.9或更高版本）和Gradle 3。如果您尚未安装Gradle，您可以按照 http://www.gradle.org/ 上的说明进行操作。

可以使用org.springframework.boot 组(group)声明Spring Boot 的依赖项。 通常，您的项目将声明一个或多个“启动器(Starters)”的依赖。Spring Boot提供了一个有用的Gradle插件，可用于简化依赖关系声明和创建可执行 jar包。

Gradle Wrapper

当您需要构建项目时，Gradle Wrapper提供了一种“获取(obtaining)”Gradle的更好的方式。 它是一个小脚本和库，它与代码一起引导构建过程。 有关详细信息，请参阅 https://docs.gradle.org/2.14.1/userguide/gradle_wrapper.html 。

典型的 build.gradle 文件：

    plugins {
        id 'org.springframework.boot' version '1.5.2.RELEASE'
        id 'java'
    }


    jar {
        baseName = 'myproject'
        version =  '0.0.1-SNAPSHOT'
    }

    repositories {
        jcenter()
    }

    dependencies {
        compile("org.springframework.boot:spring-boot-starter-web")
        testCompile("org.springframework.boot:spring-boot-starter-test")
    }

10.2 安装Spring Boot CLI

Spring Boot CLI是一个命令行工具，如果要使用Spring快速原型(quickly prototype)，可以使用它。 它允许您运行Groovy脚本，这意味着会有您熟悉的类似Java的语法，没有太多的样板代码(boilerplate code)。

您也不必要通过CLI来使用Spring Boot，但它绝对是开始Spring应用程序最快方法。

10.2.1 手动安装

您可以从Spring软件版本库下载Spring CLI发行版：

spring-boot-cli-1.5.2.RELEASE-bin.zip
spring-boot-cli-1.5.2.RELEASE-bin.tar.gz
各发布版本的快照。

下载完成后，请按照解压缩后文件中的INSTALL.txt的说明进行操作。 总而言之：在.zip文件的bin/目录中有一个spring脚本（Windows的spring.bat），或者你可以使用java -jar（脚本可以帮助您确保类路径设置正确）。

10.2.2 使用SDKMAN!安装

SDKMAN!（软件开发套件管理器）可用于管理各种二进制SDK的多个版本，包括Groovy和Spring Boot CLI。从http://sdkman.io/ 获取SDKMAN！并安装Spring Boot。

    $ sdk install springboot
    $ spring --version
    Spring Boot v1.5.2.RELEASE

如果您正在开发CLI的功能，并希望轻松访问刚创建的版本，请遵循以下额外说明。

    $ sdk install springboot dev /path/to/spring-boot/spring-boot-cli/target/spring-boot-cli-1.5.2.RELEASE-bin/spring-1.5.2.RELEASE/
    $ sdk default springboot dev
    $ spring --version
    Spring CLI v1.5.2.RELEASE

这将安装一个称为dev的spring的本地实例(instance)。 它指向您构建位置的target，所以每次重建(rebuild)Spring Boot时，Spring 将是最新的。

你可以看到：

    $ sdk ls springboot
    
    ================================================================================
    Available Springboot Versions
    ================================================================================
    > + dev
    * 1.5.2.RELEASE
    
    ================================================================================
    + - local version
    * - installed
    > - currently in use
    ================================================================================


10.2.3 OSX Homebrew 安装

如果您在Mac上使用 Homebrew，安装Spring Boot CLI 只需要下面命令：

    $ brew tap pivotal/tap
    $ brew install springboot

Homebrew会将Spring 安装到 /usr/local/bin。

如果您没有看到公式(formula)，您的安装可能会过期。 只需执行brew更新，然后重试。
10.2.4 MacPorts安装

如果您在Mac上使用 MacPorts，安装Spring Boot CLI 只需要下面命令：

    $ sudo port install spring-boot-cli

10.2.5 命令行补全

Spring Boot CLI为BASH和zsh shell提供命令补全的功能。 您可以在任何shell中引用脚本（也称为spring），或将其放在您的个人或系统范围的bash完成初始化中。 在Debian系统上，系统范围的脚本位于 /shell-completion/bash 中，当新的shell启动时，该目录中的所有脚本将被执行。 手动运行脚本，例如 如果您使用SDKMAN安装了！

    $ . ~/.sdkman/candidates/springboot/current/shell-completion/bash/spring
    $ spring <HIT TAB HERE>
      grab  help  jar  run  test  version

如果使用Homebrew或MacPorts安装Spring Boot CLI，则命令行补全脚本将自动注册到您的shell。
10.2.6 快速启动Spring CLI示例

这是一个非常简单的Web应用程序，可用于测试您的安装是否正确。 创建一个名为app.groovy的文件：

    @RestController
    class ThisWillActuallyRun {
    
        @RequestMapping("/")
        String home() {
            "Hello World!"
        }
    
    }


然后从shell运行它：

    $ spring run app.groovy

因为下载依赖的库，首次运行应用程序需要一些时间，。 后续运行将会更快。

在浏览器中打开 http://localhost:8080 ，您应该会看到以下输出：

    Hello World!

10.3 从早期版本的Spring Boot升级

如果您从早期版本的 Spring Boot 升级，请检查项目wiki上托管的“发行说明”。 您将找到升级说明以及每个版本的“新的和值得注意的”功能的列表。

要升级现有的CLI安装，请使用包管理工具相应的package manager命令（例如brew upgrade），如果您手动安装了CLI，请按照标准说明记住更新PATH环境变量以删除任何旧的引用。

11. 开发您的第一个Spring Boot应用程序

让我们在Java中开发一个简单的“Hello World！”Web应用程序，突显Spring Boot一些主要的功能。 我们将使用Maven构建该项目，因为大多数IDE支持它。

https://spring.io/ 包含许多使用Spring Boot的“入门指南”。 如果您正在寻求解决一些具体问题; 可以先看一下那里。

您可以在 https://start.spring.io/ 的依赖关系搜索器中选择Web启动器来快速完成以下步骤。 
这会自动生成一个新的项目结构，方便您立即开始编码。 查看文档了解更多详细信息。
在开始之前，打开终端来检查您是否安装了有效的Java和Maven版本。

    $ java -version
    java version "1.7.0_51"
    Java(TM) SE Runtime Environment (build 1.7.0_51-b13)
    Java HotSpot(TM) 64-Bit Server VM (build 24.51-b03, mixed mode)

    $ mvn -v
    Apache Maven 3.2.3 (33f8c3e1027c3ddde99d3cdebad2656a31e8fdf4; 2014-08-11T13:58:10-07:00)
    Maven home: /Users/user/tools/apache-maven-3.1.1
    Java version: 1.7.0_51, vendor: Oracle Corporation

这个示例需要在其自己的文件夹中创建。 后面我们假设您在当前目录已经创建了一个正确的文件夹。
11.1 创建POM

我们需要先创建一个Maven pom.xml文件。 pom.xml是用于构建项目的配置文件。打开编辑器并添加以下内容：

    <?xml version="1.0" encoding="UTF-8"?>
    <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
        xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
        <modelVersion>4.0.0</modelVersion>
    
        <groupId>com.example</groupId>
        <artifactId>myproject</artifactId>
        <version>0.0.1-SNAPSHOT</version>
    
        <parent>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-parent</artifactId>
            <version>1.5.2.RELEASE</version>
        </parent>
    
        <!-- Additional lines to be added here... -->
    
    </project>
 
这应该给你一个工作构建(working build)，你可以通过运行 mvn package 进行测试（你可以暂时忽略警告：“jar will be empty - no content was marked for inclusion!”）。

现在，您可以将项目导入到IDE中（最新的Java IDE内置对Maven的支持）。 为了简单起见，这个示例我们继续使用纯文本编辑器。
11.2 添加类路径依赖关系

Spring Boot提供了一些“启动器(Starters)”，可以方便地将jar添加到类路径中。我们的示例应用程序已经在POM的父部分使用了spring-boot-starter-parent。spring-boot-starter-parent是一个特殊启动器，提供一些Maven的默认值。它还提供依赖管理 dependency-management 标签，以便您可以省略子模块依赖关系的版本标签。

其他“启动器(Starters)”只是提供您在开发特定类型的应用程序时可能需要的依赖关系。 由于我们正在开发Web应用程序，所以我们将添加一个spring-boot-starter-web依赖关系，但在此之前，我们来看看我们目前的依赖。

    $ mvn dependency:tree

    [INFO] com.example:myproject:jar:0.0.1-SNAPSHOT

    mvn dependency:tree：打印项目依赖关系的树形表示。 您可以看到spring-boot-starter-parent本身不在依赖关系中。 编辑pom.xml并在 parent 下添加spring-boot-starter-web依赖关系：
    
    <dependencies>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
    </dependencies>

如果您再次运行 mvn dependency:tree ，您将看到现在有许多附加依赖关系，包括Tomcat Web服务器和Spring Boot本身。

11.3 编写代码

要完成我们的应用程序，我们需要创建一个的Java文件。 默认情况下，Maven将从src/main/java编译源代码，因此您需要创建该文件夹结构，然后添加一个名为src/main/java/Example.java的文件：

    import org.springframework.boot.*;
    import org.springframework.boot.autoconfigure.*;
    import org.springframework.stereotype.*;
    import org.springframework.web.bind.annotation.*;
    
    @RestController
    @EnableAutoConfiguration
    public class Example {
    
        @RequestMapping("/")
        String home() {
            return "Hello World!";
        }
    
        public static void main(String[] args) throws Exception {
            SpringApplication.run(Example.class, args);
        }
    
    }

虽然这里没有太多的代码，但是有一些重要的部分。

11.3.1 @RestController和@RequestMapping 注解

我们的Example类的第一个注解是@RestController。 这被称为 stereotype annotation。它为人们阅读代码提供了一些提示，对于Spring来说，这个类具有特定的作用。在这里，我们的类是一个web @Controller，所以Spring在处理传入的Web请求时会考虑这个类。

@RequestMapping注解提供“路由”信息。 告诉Spring，任何具有路径“/”的HTTP请求都应映射到home方法。 @RestController注解告诉Spring将生成的字符串直接返回给调用者。

@RestController和@RequestMapping注解是Spring MVC 的注解（它们不是Spring Boot特有的）。 有关更多详细信息，请参阅Spring参考文档中的MVC部分。
11.3.2 @EnableAutoConfiguration注解

第二个类级别的注释是@EnableAutoConfiguration。 这个注解告诉 Spring Boot 根据您添加的jar依赖关系来“猜(guess)”你将如何配置Spring。由于spring-boot-starter-web添加了Tomcat和Spring MVC，自动配置将假定您正在开发Web应用程序并相应地配置Spring。

启动器和自动配置

自动配置旨在与“起动器”配合使用，但两个概念并不直接相关。 您可以自由选择启动器之外的jar依赖项，Spring Boot仍然会自动配置您的应用程序。

11.3.3 “main”方法

我们的应用程序的最后一部分是main()方法。 这只是一个遵循Java惯例的应用程序入口点的标准方法。 我们的main()方法通过调用run()委托(delegates)给Spring Boot的SpringApplication类。 SpringApplication将引导我们的应用程序，启动Spring，然后启动自动配置的Tomcat Web服务器。 我们需要将Example.class作为一个参数传递给run方法来告诉SpringApplication，它是主要的Spring组件。 还传递了args数组以传递命令行参数。

11.4 运行示例

由于我们使用了spring-boot-starter-parent POM，所以我们有一个可用的运行目标，我们可以使用它来启动应用程序。 键入mvn spring-boot：从根目录运行以启动应用程序：

    $ mvn spring-boot:run
    
      .   ____          _            __ _ _
     /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
    ( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
     \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
      '  |____| .__|_| |_|_| |_\__, | / / / /
     =========|_|==============|___/=/_/_/_/
     :: Spring Boot ::  (v1.5.2.RELEASE)
    ....... . . .
    ....... . . . (log output here)
    ....... . . .
    ........ Started Example in 2.222 seconds (JVM running for 6.514)


如果你用浏览器打开 http://localhost:8080 你应该看到以下输出：

    Hello World!

ctrl-c 正常(gracefully)退出应用程序。

11.5 创建可执行的jar

让我们完成我们的例子，创建一个完全自包含的可执行jar文件，我们可以在生产环境中运行。 可执行的jar（有时称为“fat jars”）是包含编译的类以及代码运行所需要的所有jar包依赖的归档(archives)。

可执行jar和Java

Java不提供任何标准的方法来加载嵌套的jar文件（即本身包含在jar中的jar文件）。 如果您正在寻找可以发布自包含的应用程序，这可能是有问题的。 
为了解决这个问题，许多开发人员使用“uber” jars。 一个uber jar简单地将所有类、jar包进行档案。 这种方法的问题是，很难看到您在应用程序中实际使用哪些库。 如果在多个jar中使用相同的文件名（但具有不同的内容），也可能会出现问题。 
Spring Boot采用一个不同的方法这样可以直接对jar进行嵌套。

要创建可执行的jar，我们需要将spring-boot-maven-plugin添加到我们的pom.xml中。 在 dependencies标签 下方插入以下行：
    
    <build>
        <plugins>
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
            </plugin>
        </plugins>
    </build>

spring-boot-starter-parent POM 包括重新打包目标的 executions标签 配置。 如果您不使用该父POM，您将需要自己声明此配置。 有关详细信息，请参阅插件文档。
保存您的pom.xml并从命令行运行 mvn package：

    $ mvn package
    
    [INFO] Scanning for projects...
    [INFO]
    [INFO] ------------------------------------------------------------------------
    [INFO] Building myproject 0.0.1-SNAPSHOT
    [INFO] ------------------------------------------------------------------------
    [INFO] .... ..
    [INFO] --- maven-jar-plugin:2.4:jar (default-jar) @ myproject ---
    [INFO] Building jar: /Users/developer/example/spring-boot-example/target/myproject-0.0.1-SNAPSHOT.jar
    [INFO]
    [INFO] --- spring-boot-maven-plugin:1.5.2.RELEASE:repackage (default) @ myproject ---
    [INFO] ------------------------------------------------------------------------
    [INFO] BUILD SUCCESS
    [INFO] ------------------------------------------------------------------------

如果你看看target目录，你应该看到myproject-0.0.1-SNAPSHOT.jar。 该文件的大小约为10 MB。 如果你想查看里面，可以使用jar tvf：

$ jar tvf target/myproject-0.0.1-SNAPSHOT.jar
1
您还应该在target目录中看到一个名为myproject-0.0.1-SNAPSHOT.jar.original的较小文件。 这是Maven在Spring Boot重新打包之前创建的原始jar文件。

使用java -jar命令运行该应用程序：

    $ java -jar target/myproject-0.0.1-SNAPSHOT.jar
    
      .   ____          _            __ _ _
     /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
    ( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
     \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
      '  |____| .__|_| |_|_| |_\__, | / / / /
     =========|_|==============|___/=/_/_/_/
     :: Spring Boot ::  (v1.5.2.RELEASE)
    ....... . . .
    ....... . . . (log output here)
    ....... . . .
    ........ Started Example in 2.536 seconds (JVM running for 2.864)

像之前一样，ctrl+c正常退出应用程序。

12. 接下来应该读什么

希望本节能为您提供一些Spring Boot基础知识，并让您准备编写自己的应用程序。 如果你是一个面向具体任务的开发人员，你可能想跳过 https://spring.io/ ，看看一些解决具体的“如何用Spring”问题的入门指南; 我们还有Spring Boot-specific How-to参考文档。

Spring Boot库还有一大堆可以运行的示例。 示例与代码的其余部分是独立的（这样您不需要构建多余的代码来运行或使用示例）。

