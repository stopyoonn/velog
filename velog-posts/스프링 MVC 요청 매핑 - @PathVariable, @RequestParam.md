<p>이 글은 김영한님의 &quot;스프링 MVC 1편 - 백엔드 웹 개발 핵심 기술&quot; 수강하고 내용을 정리한 글입니다.
<a href="https://www.inflearn.com/course/%EC%8A%A4%ED%94%84%EB%A7%81-mvc-1">https://www.inflearn.com/course/%EC%8A%A4%ED%94%84%EB%A7%81-mvc-1</a></p>
<h3 id="restcontroller"><code>@RestController</code></h3>
<ul>
<li><code>@Controller</code>는 반환 값이 <code>String</code>이면 뷰 이름으로 인식됨. 그래서 <strong>뷰를 찾고 뷰가 랜더링</strong>됨</li>
<li><code>@RestController</code>는 반환 값으로 뷰를 찾는 것이 아니라, <strong>HTTP 메시지 바디에 바로 입력함</strong>. 따라서 실행 결과로 ok 메세지를 받을 수 있음</li>
</ul>
<h3 id="requestmappinghello-basic"><code>@RequestMapping(&quot;/hello-basic&quot;)</code></h3>
<ul>
<li><code>/hello-basci</code> URL 호출이 오면 이 메서드가 실행되도록 매핑함</li>
<li>대부분의 속성을 <code>배열[]</code>로 제공하므로 다중 설정이 가능함 <code>{&quot;/hello-basic&quot;, &quot;hello-go}&quot;</code></li>
</ul>


<h3 id="pathvariable경로-변수-사용">PathVariable(경로 변수) 사용</h3>
<pre><code class="language-java">/**
 * PathVariable 사용
 * 변수명이 같으면 생략 가능
 * @PathVariable(&quot;userId&quot;) String userId -&gt; @PathVariable String userId
 */
 @GetMapping(&quot;/mapping/{userId}&quot;)
 public String mappingPath(@PathVariable(&quot;userId&quot;) String data) {
    log.info(&quot;mappingPath userId={}&quot;, data);
 return &quot;ok&quot;;
 }
과 </code></pre>
<ul>
<li><code>@RequestMapping</code>은 URL 경로를 템플릿화 할 수 있는데, <code>@PathVariable</code>을 사용하면 매칭되는 부분을 편리하게 조회할 수 있음</li>
<li><code>@PathVariable</code>의 이름과 파라미터 이름이 같으면 생략할 수 있음</li>
</ul>


<h3 id="pathvariable-사용---다중">PathVariable 사용 - 다중</h3>
<pre><code class="language-java"> @GetMapping(&quot;/mapping/users/{userId}/orders/{orderId}&quot;)
 public String mappingPath(@PathVariable String userId, @PathVariable Long 
orderId) {
    log.info(&quot;mappingPath userId={}, orderId={}&quot;, userId, orderId);
 return &quot;ok&quot;;
 }</code></pre>


<h3 id="http-요청-파라미터---requestparam">HTTP 요청 파라미터 - @RequestParam</h3>
<ul>
<li>스프링이 제공하는 <code>@RequestParam</code>을 사용하면 요청 파라미터를 매우 편리하게 사용할 수 있다.<pre><code class="language-java">@ResponseBody
@RequestMapping(&quot;/request-param-v2&quot;)
public String requestParamV2(
      @RequestParam(&quot;username&quot;) String memberName,
      @RequestParam(&quot;age&quot;) int memberAge) {
  log.info(&quot;username={}, age={}&quot;, memberName, memberAge);
return &quot;ok&quot;;
}</code></pre>
</li>
<li><code>@RequestParam</code>: 파라미터 이름으로 인딩</li>
<li><code>@ResponseBody</code>: View 조회를 무시하고, HTTP message body에 직접 해당 내용 입력</li>
</ul>