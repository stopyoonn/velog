<h2 id="1-마이크로서비스-아키텍처란">1. 마이크로서비스 아키텍처란?</h2>
<blockquote>
<p>애플리케이션 개발을 위한 아키텍처 스타일을 의미함.
마이크로 서비스를 사용하면 대규모 애플리케이션을 각각 담당 영역을 가진 소규모의 독립적인 구성요소로 구분할 수 있음.</p>
</blockquote>
<ul>
<li>Microservice Architecture는 애플리케이션이 서비스 모음으로 개발되는 애플리케이션 아키텍처의 한 유형</li>
<li>또한 Microservice Architectrue Diagram과 서비스를 독립적으로 개발, 배포, 유지관리할 수 있는 프레임워크를 제공함</li>
</ul>


<h2 id="2-msa의-등장배경">2. MSA의 등장배경</h2>
<ul>
<li>기존의 시스템은 화면부터 DB까지 전체가 하나의 흐름으로 묶여있는 Monolithic Architecture<blockquote>
<p><strong>Monolithic Architecture</strong></p>
<ul>
<li>소프트웨어의 모든 구성요소가 한 프로젝트에 통합되어 있는 형태</li>
<li>ex) 웹 프로그램을 개발하기 위해 모듈별로 개발을 하고, 개발이 완료된 웹 애플리케이션을 하나의 결과물로 패키징하여 배포되는 형태를 말함</li>
<li><strong>문제점</strong>: 부분 장애가 전체 서비스의 장애로 확대될 수 있으며, 부분적인 서비스의 변경이 어렵고, 수정 시 장애의 영향도 파악이 힘듦
→ 오류가 발생하여 수정한 부분이 예상하지 못하는 다른 부분에 영향을 주어 오류가 발생할 수 있다는 의미</li>
</ul>
</blockquote>
</li>
</ul>


<h2 id="3-모노리스monolith-vs-마이크로서비스microservice">3. 모노리스(monolith) vs. 마이크로서비스(microservice)</h2>
<p><strong>- 모노리스(monolith)</strong></p>
<ul>
<li>하나의 단위로 개발되는 일체식 어플리케이션</li>
<li>단일 프로세스에서 실행됨</li>
<li>여러 개의 모노리스 시스템 모두를 재빌드/재배포해야 함</li>
<li>애플리케이션 병렬 확장은 가능하다 데이터베이스가 통합되어 있어 탄력적 대응이 어려움</li>
</ul>
<p><strong>- 마이크로서비스(microservice)</strong></p>
<ul>
<li>서버 측이 여러 개의 조각으로 구성되어 각 서비스가 별개의 인스턴스로 로딩함.</li>
<li>여러 서비스 인스턴스가 모여 하나의 비즈니스 애플리케이션을 구성함.</li>
<li>각기 저장소가 달라 <strong>업무 단위로 모듈 결계가 명확하게 구분함</strong>.</li>
<li>각 서비스는 또한 <strong>다른 서비스 및 저장소와 격리되어 있으며 API를 통해서만 느슨하게 연계</strong>됨.</li>
<li>각 서비스는 <strong>자동화된 개발 환경에서 독립적으로 배포</strong>됨.</li>
</ul>


<h2 id="4-msa의-특징">4. MSA의 특징</h2>
<ul>
<li>하나의 API를 통해서 모든 구성요소들이 상호작용하는 것<ul>
<li>마이크로서비스는 서비스 end-point을 API 형태로 외부에 노출하여 내부의 구현 로직, 아키텍처와 프로그래밍 언어, 데이터베이스, 품질 유지 체계와 같은 기술적인 사항들은 서비스 API에 의해 철저하게 가려짐.</li>
</ul>
</li>
<li>제대로 설계된 마이크로서비스는 하나의 비즈니스 범위에 맞춰 만들어지므로 하나의 기능만 수행함.</li>
</ul>


<h2 id="5-msa의-장점">5. MSA의 장점</h2>
<ul>
<li>각각의 서비스는 모듈화가 되어있으므로 모듈끼리는 RPC 또는 message-driven API 등을 이용하여 통신함.</li>
<li>이러한 MSA는 각각 개별의 서비스 개발을 빠르게 하며, 유지보수도 쉽게 할 수 있도록 함.</li>
<li>팀 단위로 적절한 수준에서 기술 스택을 다르게 가져갈 수 있음</li>
<li>Microservice는 서비스 별로 독립적 배포가 가능함.<ul>
<li>따라서 지속적인 배포 CD도 모놀로식에 비해서 가볍게 할 수 있음</li>
</ul>
</li>
<li>Microservice는 각각 서비스의 부하에 따라 개별적으로 scale-out이 가능함. 메모리, CPU적으로 상당 부분이 이득이 됨.</li>
</ul>


<h2 id="6-msa의-단점">6. MSA의 단점</h2>
<ul>
<li>모놀리식에 비해 상대적으로 많이 복잡함.</li>
<li>서비스가 모두 분산되어 있기 때문에 개발자는 내부 시스템의 통신을 어떻게 가져가야 할지 반드시 표준 정의가 되어 있어야 함.</li>
<li>통신의 장애와 서버의 부하 등이 있을 경우 어떻게 transaction을 유지할지 경장하고 구현해야 함.</li>
<li>모놀리식에서는 단일 트래잭션을 유지하면 되지만 MSA는 비즈니스에 대한 DB를 가지고 있는 서비스도 각기 다르고, 서비스의 연결을 위해서는 통신이 포함되기 때문에 트랜잭션을 유지하는 게 어려움.</li>
<li>통합 테스트가 매우 어려움.<ul>
<li>개발 환경과 실제 운영환경을 동일하게 가져가는 것이 쉽지 않기 때문임.</li>
</ul>
</li>
<li>실제 운영환경에 대해서 배포하는 것 또한 쉽지 않음.</li>
</ul>


<p><strong>Reference</strong>
<a href="https://mydream72.tistory.com/entry/%EC%95%8C%EA%B3%A0%EB%B3%B4%EB%8B%88-MSA%EB%9E%80">https://mydream72.tistory.com/entry/%EC%95%8C%EA%B3%A0%EB%B3%B4%EB%8B%88-MSA%EB%9E%80</a>
<a href="https://velog.io/@mrcocoball2/MSA-%EC%95%8C%EC%95%84%EB%B3%B4%EA%B8%B0-1.-MSA%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80">https://velog.io/@mrcocoball2/MSA-%EC%95%8C%EC%95%84%EB%B3%B4%EA%B8%B0-1.-MSA%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80</a></p>