# Maven插件

## 拷贝插件 maven-antrun-plugin

**打包完成后,把构建结果复制到其他位置**

```xml
<plugin>
<groupId>org.apache.maven.plugins</groupId>
<artifactId>maven-antrun-plugin</artifactId><!-- 拷贝插件 -->
<executions>
    <execution>
        <id>package</id>
        <phase>package</phase><!-- maven生命周期 -->
        <configuration>
            <target>
                <echo message="copy package to deplay dir"/>
                <copy todir="C:\Users\B.W.H\Downloads" overwrite="true"> <!--  文件将要输出目录 在parent pom中统一配置，此处引用即可-->
                    <fileset dir="${project.build.directory}"> <!-- 待拷贝文件的目录，默认目录在项目的target下-->
                        <include name="${project.artifactId}.jar" /> <!-- 待拷贝文件，可以使用下面的通配符，还可以是其他目录的文件。此处需要与project.bulid.finalName对应，否则可能找不到文件 -->
                        <!-- <include name="*.jar" /> -->
                    </fileset>
                </copy>
<!--                <copy file="${basedir}/target/archbase-${profiles.evn}-${project.version}.war"-->
<!--                      tofile="E:/Repositories/workspace/deplay/archbase.war"-->
<!--                      overwrite="true"/>-->
            </target>
        </configuration>
        <goals>
            <goal>run</goal>
        </goals>
    </execution>
</executions>
</plugin>

```

- `<phase>package</phase>` 表示插件要在Maven 的 package 时执行
- `<goal>run</goal>` 这时插件内部的一个执行目标
- `<target></target>` 之间可以写任何Ant支持的task