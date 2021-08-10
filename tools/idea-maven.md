maven 导入jar包到本地仓库：
mvn install:install-file -Dfile=D:\dependRepository\otherJarsNeedMavenInstall\pinyin4j-2.5.0.jar -DgroupId=net.sourceforge  -DartifactId=pinyin4j -Dversion=2.5.0 -Dpackaging=jar

mvn install:install-file 根据指定file进行安装jar包
-Dfile=jar包的绝对路径
-DgroupId= jar包的组织id
-DartifactId=jar包的项目名
-Dversion=jar包的版本号
-Dpackaging=打包方式