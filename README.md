
### Spring Boot 2 アプリのサンプル

* 参考 読み物
* https://qiita.com/toruuetani/items/290d22a42c33c73831da SpringBootとGradleでHelloWorld - Qiita
* https://qiita.com/sugaryo/items/5695bfcc21365f429767 SpringBootに入門する為の助走本（随時更新） - Qiita
* https://qiita.com/yukina-ge/items/1ca029ed69494bfd36d6 Spring Boot 1.5.10 → Spring Boot 2.0.0 にしたときの覚書 - Qiita

* https://gradle.org/ Gradle Build Tool
* https://guides.gradle.org/building-spring-boot-2-projects-with-gradle/ Building Spring Boot 2 Applications with Gradle
    
* https://docs.spring.io/spring-boot/docs/current/gradle-plugin/reference/html/ Spring Boot Gradle Plugin Reference Guide
    こちらがマトモか。

```
# サンプルプロジェクト用のディレクトリを作成
mkdir springboot2test
cd springboot2test

# ひな型一式作成
gradle init --type java-application
```

ここで、gradle.build ファイルを手作り。

```
# jarもwarも作成する
gradle clean build bootJar bootWar
```


```
# Spring Boot 2 内蔵tomcatによる起動
gradle bootRun

# ブラウザから http://localhost:8080/ にアクセスすると、Hello Gradle! が表示される。
```
