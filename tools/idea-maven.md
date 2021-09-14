maven 导入jar包到本地仓库：
mvn install:install-file -Dfile=D:\dependRepository\otherJarsNeedMavenInstall\pinyin4j-2.5.0.jar -DgroupId=net.sourceforge  -DartifactId=pinyin4j -Dversion=2.5.0 -Dpackaging=jar

mvn install:install-file 根据指定file进行安装jar包
-Dfile=jar包的绝对路径
-DgroupId= jar包的组织id
-DartifactId=jar包的项目名
-Dversion=jar包的版本号
-Dpackaging=打包方式

mvn install:install-file -Dfile=D:\workSpace\huKai\userCenter\UserCenter\lib\img-1.0.4.20200522.jar -DgroupId=net.sourceforge  -DartifactId=pinyin4j -Dversion=2.5.0 -Dpackaging=jar

mvn install:install-file -Dfile=D:\workSpace\huKai\userCenter\UserCenter\lib\img-1.0.4.20200522.jar -DgroupId=com.yzj -DartifactId=img -Dversion=1.0.4.20200522 -Dpackaging=jar

mvn install:install-file -Dfile=D:\workSpace\huKai\userCenter\UserCenter\lib\framework4.0.jar -DgroupId=micro -DartifactId=framework -Dversion=4.0 -Dpackaging=jar


mvn install:install-file -Dfile=D:\workSpace\huKai\userCenter\UserCenter\lib\micro-server-0.0.1.jar -DgroupId=micro -DartifactId=micro-server -Dversion=0.0.1 -Dpackaging=jar


mvn install:install-file -Dfile=D:\workSpace\huKai\userCenter\UserCenter\lib\micro-client-0.0.1.jar -DgroupId=micro -DartifactId=micro-client -Dversion=0.0.1 -Dpackaging=jar
