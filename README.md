
### Spring Boot 2 アプリのサンプル

* 参考 読み物
* https://qiita.com/toruuetani/items/290d22a42c33c73831da SpringBootとGradleでHelloWorld - Qiita
* https://qiita.com/sugaryo/items/5695bfcc21365f429767 SpringBootに入門する為の助走本（随時更新） - Qiita
* https://qiita.com/yukina-ge/items/1ca029ed69494bfd36d6 Spring Boot 1.5.10 → Spring Boot 2.0.0 にしたときの覚書 - Qiita
* https://docs.spring.io/spring-boot/docs/current/reference/html/index.html Spring Boot Reference Guide
    92章もある巨大なドキュメント（英語） spring boot におおよそ必要な情報はすべてここにありそうな雰囲気を感じる

* https://gradle.org/ Gradle Build Tool
* https://guides.gradle.org/building-spring-boot-2-projects-with-gradle/ Building Spring Boot 2 Applications with Gradle
    基本的にはここの内容に従う。
    ちょいちょい違うところがあり、このままでは動作しない
* https://docs.spring.io/spring-boot/docs/current/gradle-plugin/reference/html/ Spring Boot Gradle Plugin Reference Guide
    spring boot 2 のプラグインの説明。こちらが比較的現状とあってる。

```
# サンプルプロジェクト用のディレクトリを作成
mkdir springboot2test
cd springboot2test

# ひな型一式作成
gradle init --type java-application
```

ここで、gradle.build ファイルを手作り。
詳しくは  https://github.com/george-pon/springboot2test/blob/master/build.gradle  参照。

ビルド

```
# jarもwarも作成する。 warのファイルサイズがjarとほぼ変わらない...。(約16MB)
gradle clean build bootJar bootWar
```

実行

```
# Spring Boot 2 内蔵tomcatによる起動。 Ctrl-C で停止する。
gradle bootRun

# ブラウザから http://localhost:8080/ にアクセスすると、Hello Gradle! が表示される。

# Spring Boot 2 内蔵tomcatによるjar直接起動。 Ctrl-C で停止する。
java -jar ./build/libs/springboot2test.jar

# ブラウザから http://localhost:8080/ にアクセスすると、Hello Gradle! が表示される。
```
