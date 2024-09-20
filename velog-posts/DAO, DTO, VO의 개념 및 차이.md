<h3 id="1-daodata-access-object">1. DAO(Data Access Object)</h3>
<h4 id="역할">역할</h4>
<ul>
<li>데이터베이스와의 상호작용을 담당하는 객체</li>
<li>데이터베이스에 CRUD(Create, Read, Update, Delete) 작업을 수행하는 메서드를 제공함</li>
</ul>
<h4 id="책임">책임</h4>
<ul>
<li>비즈니스 로직에서 데이터베이스를 직접 다루지 않고, DAO를 통해 데이터를 관리하게 하려 데이터 액세스 로직을 캡슐화함</li>
</ul>
<h4 id="사용-예">사용 예</h4>
<ul>
<li>UserDAO는 데이터베이스에서 사용자 정보를 가져오거나 저장하는 역할을 함<pre><code class="language-java">public class UserDAO{
  public User getUserById(int id) {
      // 데이터베이스에서 id로 사용자 정보를 가져옴}}</code></pre>
</li>
</ul>
<p></p>
<h3 id="2-dtodata-transfer-object">2. DTO(Data Transfer Object)</h3>
<h4 id="역할-1">역할</h4>
<ul>
<li>시스템 간 데이터를 전송하기 위해 사용하는 객체</li>
<li>계층 간 데이터 전송에 초점을 맞추고 있으며, 주로 네트워크 통신이나 API 호출에 사용됨</li>
</ul>
<h4 id="책임-1">책임</h4>
<ul>
<li>불필요한 비즈니스 로직 없이 순수하게 데이터를 담고 전달하는 역할만 수행함</li>
</ul>
<h4 id="사용-예-1">사용 예</h4>
<ul>
<li><p>UserDTO는 사용자 데이터를 API 요청 또는 응답으로 전송함</p>
<pre><code class="language-java">public class UserDTO {
  private int id;
  private String name;
  private String email;

  //Getter, Setter
}</code></pre>
</li>
</ul>
<p></p>
<h3 id="3-vovalue-object">3. VO(Value Object)</h3>
<h4 id="역할-2">역할</h4>
<ul>
<li>불변(immutable) 객체로서, 특정 값을 표현하는 데 사용됨</li>
<li>VO는 동일한 값을 가지면 동일한 객체로 취급됨</li>
</ul>
<h4 id="책임-2">책임</h4>
<ul>
<li>VO는 데이터를 담고 있지만, DTO와 달리 값 그 자체에 의미를 둠</li>
<li>VO는 주로 작은, 변하지 않는 데이터 조각을 모델링할 때 사용됨</li>
</ul>
<h4 id="사용-예-2">사용 예</h4>
<ul>
<li><p>AddressVO는 특정 사용자의 주소 정보를 포함하고 있으며, 주소는 한 번 설정되면 변경되지 않음</p>
<pre><code class="language-java">public class AddressVO {
  private final String street;
  private final String city;

  public AddressVO(String street, String city) {
      this.street = street;
      this.city = city;
  }

  // equals(), hashCode() 재정의
}
</code></pre>
</li>
</ul>
<pre><code>
&lt;/br&gt;&lt;/br&gt;

### 차이
- **DAO**: 데이터베이스 접근을 담당하는 객체, **데이터 관리자**
- **DTO**: 데이터를 전송하는 데 사용되는 객체, 순수한 데이터 보유 역할을 함, **데이터 전달자**
- **VO**: 불변 객체로서 값 그 자체에 의미를 부여하는 객체, **값 보관함**</code></pre>