<h2 id="stringvalueof">String.valueOf()</h2>
<blockquote>
<p>다양한 타입의 값을 문자열로 변환하는 Java의 정적 메서드</p>
</blockquote>
<h3 id="stringvalueof를-사용해야-하는-이유">String.valueOf()를 사용해야 하는 이유</h3>
<h4 id="1-null-처리">1. null 처리</h4>
<ul>
<li><code>String.valueOf()</code>는 인자가 <code>null</code>일 때 <code>&quot;null&quot;</code>이라는 문자열을 반환함</li>
<li><code>null</code> 값을 문자열로 변환할 때 <code>NullPointerException</code>이 발생하지 않음</li>
</ul>
<h4 id="2-다양한-타입을-문자열로-변환">2. 다양한 타입을 문자열로 변환</h4>
<ul>
<li>Primitive 타입과 Reference 타입 모두 문자열로 변환이 가능함</li>
</ul>