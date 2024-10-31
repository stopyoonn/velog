<h2 id="1-mybatis란">1. MyBatis란?</h2>
<ul>
<li>Java 기반의 ORM(Object-Relational Mapping) 프레임워크로, 데이터베이스와의 상호작용을 간편하게 해주는 도구</li>
</ul>
<p></p>
<h2 id="2-mybatis의-기본-개념">2. MyBatis의 기본 개념</h2>
<p>(1) SQL 매핑: SQL 쿼리를 XML 파일이나 annotation으로 정의할 수 있음. 이를 통해 SQL과 Java 코드를 분리할 수 있음
(2) Configuratrion: <code>SqlSessionFactory</code>를 사용해 데이터베이스 연결을 관리함. XML 설정 파일에서 데이터베이스 연결 정보와 Mapper 파일 경로 등을 정의함
(3) Mapper: SQL 쿼리를 매핑하는 XML 파일을 작성하여 Java 메서드와 SQL 쿼리를 연결함.</p>
<p></p>
<h2 id="3-mybatis-사용-예시">3. MyBatis 사용 예시</h2>
<h3 id="1-의존성-추가">(1) 의존성 추가</h3>
<ul>
<li>pom.xml에 MyBatis와 관련된 의존성 추가(maven)<pre><code class="language-xml">&lt;dependency&gt;
  &lt;groupId&gt;org.mybatis&lt;/groupId&gt;
  &lt;artifactId&gt;mybatis&lt;/artifactId&gt;
  &lt;version&gt;x.x.x&lt;/version&gt;
&lt;/dependency&gt;</code></pre>
</li>
</ul>
<h3 id="2-설정-파일-작성">(2) 설정 파일 작성</h3>
<ul>
<li>mybatis-config.xml 파일을 생성하여 MyBatis의 전반적인 설정을 정의<pre><code class="language-xml&lt;?xml">&lt;!DOCTYPE configuration
PUBLIC &quot;-//mybatis.org//DTD Config 3.0//EN&quot;
&quot;https://mybatis.org/dtd/mybatis-3-config.dtd&quot;&gt;
&lt;configuration&gt;
&lt;environments default=&quot;development&quot;&gt;
  &lt;environment id=&quot;development&quot;&gt;
    &lt;transactionManager type=&quot;JDBC&quot;/&gt;
    &lt;dataSource type=&quot;POOLED&quot;&gt;
      &lt;property name=&quot;driver&quot; value=&quot;${driver}&quot;/&gt;
      &lt;property name=&quot;url&quot; value=&quot;${url}&quot;/&gt;
      &lt;property name=&quot;username&quot; value=&quot;${username}&quot;/&gt;
      &lt;property name=&quot;password&quot; value=&quot;${password}&quot;/&gt;
    &lt;/dataSource&gt;
  &lt;/environment&gt;
&lt;/environments&gt;
&lt;mappers&gt;
  &lt;mapper resource=&quot;org/mybatis/example/BlogMapper.xml&quot;/&gt;
&lt;/mappers&gt;
&lt;/configuration&gt;</code></pre>
</li>
</ul>
<h3 id="3-mapper-인터페이스">(3) Mapper 인터페이스</h3>
<ul>
<li>SQL 쿼리를 호출할 메소드를 정의하는 인터페이스 작성</li>
<li>@Mapper 어노테이션을 붙여줘야 mapper로 인식할 수 있음<pre><code class="language-java">@Mapper
public interface YourMapper {
  List&lt;YourEntity&gt; selectAll();
  YourEntity selectById(int id);
}</code></pre>
</li>
</ul>
<h3 id="4-mapper-xml-파일">(4) Mapper XML 파일</h3>
<ul>
<li>SQL 쿼리를 정의하는 XML 파일 작성</li>
<li>view에서 입력받는 username의 값으로 조건을 설정하고 싶으면 ```#{username} 처럼 앞에 #을 붙여주면 됨<pre><code class="language-xml">&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;!DOCTYPE mapper PUBLIC &quot;-//mybatis.org//DTD Mapper 3.0//EN&quot; &quot;http://mybatis.org/dtd/mybatis-3-mapper.dtd&quot;&gt;
&lt;mapper namespace=&quot;com.mapper.YourMapper&quot;&gt;
  &lt;select id=&quot;selectAll&quot; resultType=&quot;YourEntity&quot;&gt;
          SELECT * FROM your_table
  &lt;/select&gt;
  &lt;select id=&quot;selectById&quot; parameterType=&quot;int&quot; resultType=&quot;YourEntity&quot;&gt;
          SELECT * FROM your_table WHERE id = #{id}
      &lt;/select&gt;
&lt;/mapper&gt;</code></pre>
</li>
</ul>
<h3 id="5-service에서-사용">(5) Service에서 사용</h3>
<pre><code class="language-java">@Service
public class YourService {
    @Autowired
    private YourMapper yourMapper;

    public List&lt;YourEntity&gt; getAll() {
        return yourMapper.selectAll();
    }
}</code></pre>