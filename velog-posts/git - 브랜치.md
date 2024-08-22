<h2 id="1-브랜치-생성하기">1. 브랜치 생성하기</h2>
<h3 id="①-브랜치란">① 브랜치란?</h3>
<ul>
<li><strong>브랜치(branch)</strong>란 프로젝트 기준 코드인 main 브랜치로부터 독립적인 작업 공간을 만들어주는 기능</li>
<li>여러 개발자가 서로 다른 버전의 코드를 만들 때 서로의 작업에 영향을 주고 받지 않기 위해 필요</li>
</ul>
<br />

<h3 id="②-깃허브-원격-저장소에서-브랜치-생성하기">② 깃허브 원격 저장소에서 브랜치 생성하기</h3>
<blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/nuypotss/post/f7bf0f0b-c3a1-406c-b7c5-fe8193441c0e/image.png" /></p>
</blockquote>
<ul>
<li>새로 생성되는 브랜치는 현재 브랜치의 최신 상태를 기준으로 생성됨</li>
</ul>
<h4 id="√-git-remote-update">√ git remote update</h4>
<blockquote>
<ul>
<li>해당 명령어는 우리가 지역 저장소에 등록한 원격 저장소의 최신 정보를 가져옴</li>
</ul>
</blockquote>
<h4 id="√-git-branch--a">√ git branch -a</h4>
<blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/nuypotss/post/8e048409-0eb3-4581-9bd1-276a651ff904/image.png" /></p>
</blockquote>
<ul>
<li>git branch 명령어를 실행해 지역 저장소와 원격 저장소의 브랜치의 정보를 확인</li>
<li>-a  옵션은 지역 저장소와 원격 저장소의 브랜치 정보를 함께 보여줌</li>
<li>main: 지역 저장소의 main 브랜치를 의미 (*는 현재 작업 중인 브랜치를 의미)</li>
<li>'remotes/origin' 접두사가 붙은 브랜치는 원격 저장소, 특히 origin 시별자로 등록한 원격 저장소의 브랜치를 의미</li>
<li>원격 저장소에는 main, master, remote-branch 브랜치가 존재한다는 사실을 확인할 수 있음</li>
</ul>
<h4 id="√-git-checkhout--t-브랜치명">√ git checkhout -t &lt;브랜치명&gt;</h4>
<blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/nuypotss/post/defad1ff-ed1b-426c-b54d-b733a2bb4da8/image.png" /></p>
</blockquote>
<ul>
<li>원격 저장소에서 생성한 브랜치를 지역 저장소의 작업 브랜치로 설정하는 명령어</li>
</ul>
<blockquote>
<ul>
<li>git checkout 명령어 주요 옵션</li>
<li>b: 브랜치를 생성하고 사용할 브랜치로 지정 (git chekcout -b)</li>
<li>t: 원격 저장소에서 생성한 브랜치를 지역 저장소에서 사용할 브랜치로 지정 (git checkout -t)</li>
</ul>
</blockquote>
<blockquote>
<ul>
<li>git branch -a 명령을 통해 지역 저장소에 origin/test/remote-branch가 추가되고 작업 브랜치(*)가 갱신되었음을 알 수 있음
<img alt="" src="https://velog.velcdn.com/images/nuypotss/post/27b3eab6-ee1b-4244-a0ef-eac24bf8e07e/image.png" /></li>
</ul>
</blockquote>
<br />

<h3 id="③-지역-저장소에서-깃을-통해-브랜치-생성하기">③ 지역 저장소에서 깃을 통해 브랜치 생성하기</h3>
<h4 id="√-git-branch--l">√ git branch -l</h4>
<blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/nuypotss/post/4f32297f-4d11-464a-a9ad-a1e491284134/image.png" /></p>
<ul>
<li>현재 작업 중인 브랜치를 확인</li>
<li>위에서 새로 생성된 test/remote-brach로 현재 작업 브랜치가 변경됨</li>
<li>main 브랜치를 기준으로 새로운 브랜치를 생성하려면 현재 작업 브런치를 main 브랜치로 변경해야 함</li>
</ul>
</blockquote>
<h4 id="√-git-checkout-main">√ git checkout main</h4>
<blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/nuypotss/post/09d92ed4-83ec-461d-88f7-e10fc941904c/image.png" /></p>
</blockquote>
<ul>
<li>git checkout 명령어를 실행해 작업 브랜치를 main 브랜치로 변경</li>
</ul>
<h4 id="√-git-branch-새로운-브랜치명">√ git branch {새로운 브랜치명}</h4>
<blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/nuypotss/post/a49fc263-d09f-4645-945b-133b6251f368/image.png" /></p>
</blockquote>
<ul>
<li>git branch 명령어를 이용해서 새로운 브랜치 생성</li>
</ul>
<blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/nuypotss/post/db507d26-b400-4632-bc62-57c471d3c9f7/image.png" /></p>
</blockquote>
<ul>
<li>새로운 브랜치가 생성되었는지 확인</li>
<li>원격 저장소의 브랜치까지 함께 확인하는 -a 옵션 사용</li>
<li>test/remote-branch에 'remote/origin/' 접두사가 붙지 않은 것을 보아 원격 저장소에 반영되지 않았음을 알 수 있음</li>
</ul>
<blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/nuypotss/post/97ec8a53-5577-4622-8d11-d2e7f3cd7536/image.png" /></p>
</blockquote>
<ul>
<li><strong>git checkout</strong> 명령어를 통해 새로운 브랜치를 작업 브랜치로 변경</li>
</ul>
<br />

<h3 id="④-브랜치-삭제하기">④ 브랜치 삭제하기</h3>
<h4 id="√-git-branch--d-브랜치명">√ git branch -d {브랜치명}</h4>
<ul>
<li>지역 저장소의 브랜치를 삭제하는 명령어<blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/nuypotss/post/512d4f82-f8ea-436a-9a2e-5341ba53f7fd/image.png" /></p>
</blockquote>
</li>
</ul>
<h4 id="√-git-push-origin--d-브랜치명">√ git push origin -d {브랜치명}</h4>
<ul>
<li>원격 저장소의 브랜치를 삭제하는 명령어<blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/nuypotss/post/2887e6cc-edba-4adb-8563-f4a54ae55e55/image.png" /></p>
</blockquote>
</li>
</ul>
<br />
<br />

<h2 id="2-브랜치-병합하기">2. 브랜치 병합하기</h2>
<h3 id="①-브랜치-병합이란">① 브랜치 병합이란?</h3>
<ul>
<li>새로운 작업 브랜치의 커밋 내역을 기준 브랜치에 반영하는 작업을 브랜치 병합이라고 함</li>
<li>깃에서는 브랜치 병합 기능을 제공함
→ 두 브랜치를 비교하여 파일의 변경 내용을 비교하여 합침</li>
</ul>
<br />

<h3 id="②-빨리감기-병합-fast-forward">② 빨리감기 병합: fast forward</h3>
<ul>
<li>main 브랜치를 기준으로 작업 브랜치를 생성한 후, 작업을 완료하여 main 브랜치에 병합을 시도함. 이때 main 브랜치에 새로운 커밋이 없다면 빨리감기 병합으로 진행됨</li>
<li>즉, 기준 브랜치에 작업 브랜치의 새로운 커밋이 단순히 최신 커밋으로 더해지고, 기준 브랜치가 바라보는 최신 커밋만 변경됨</li>
</ul>
<blockquote>
<p>(1) main 브랜치에서 test/fast-forward 브랜치 생성 후, 새 브런지를 작업 브랜치로 설정
<img alt="" src="https://velog.velcdn.com/images/nuypotss/post/5fbff754-a07b-4a3b-97ed-5987f651d59e/image.png" /></p>
</blockquote>
<blockquote>
<p>(2) 파일 수정</p>
</blockquote>
<blockquote>
<p>(3) 변경할 파일 추가 및 커밋 생성 명령 실행
<img alt="" src="https://velog.velcdn.com/images/nuypotss/post/3d4ede0c-7e9c-4a3d-a169-08a512a847a4/image.png" /></p>
</blockquote>
<blockquote>
<p>(4) 현재 커밋 내역의 상태 확인
<img alt="" src="https://velog.velcdn.com/images/nuypotss/post/768162ac-2e0b-4f1a-a1aa-910e89d0ac3f/image.png" /></p>
</blockquote>
<ul>
<li>현재 작업 브랜치인 test/fast-forward만 가장 최근에 생성한 커밋을 바라보고 있음</li>
<li>main 브랜치를 포함한 다른 브랜치들은 이전의 커밋을 바라보고 있음</li>
</ul>
<p><strong>test/fast-forward 브랜치의 작업 내용을 main 브랜치에 병합해보자!</strong></p>
<blockquote>
<p>(1) main 브랜치로 작업 브랜치를 변경
<img alt="" src="https://velog.velcdn.com/images/nuypotss/post/6b258e5b-5908-44ba-bcd6-84440e422121/image.png" /></p>
</blockquote>
<blockquote>
<p>(2) main 브랜치에 커밋 내역 살펴보기
<img alt="" src="https://velog.velcdn.com/images/nuypotss/post/ed9a9a0c-7103-481d-8891-ff6155b72db3/image.png" /></p>
</blockquote>
<ul>
<li>test/fast-forward에서 생성한 커밋(1a2a495f06d951c32125688ff9d5a9cc54c6bd1d)은 보이지 않음
→ 아직 새로운 브랜치의 작업 내용을 병합하지 않았기 때문</li>
</ul>
<blockquote>
<p>(3) test/fast-forward 브랜치의 작업 내용을 main 브랜치에 병합</p>
</blockquote>
<h4 id="√-git-merge-브랜치이름">√ git merge 브랜치이름</h4>
<p><img alt="" src="https://velog.velcdn.com/images/nuypotss/post/5ec2ce07-8eff-4996-aad0-8bc20f1c5126/image.png" /></p>
<ul>
<li>test/fast-forward를 main 브랜치를 기준으로 생성하고, test/fast-forward 브랜치의 작업 내용을 다시 main 브랜치에 병합할 때까지 main 브랜치에는 아무런 변경 내용이 없었기 때문에 빨리감기 병합 방식으로 이루어짐</li>
</ul>
<blockquote>
<p>(4) 병합 후, 커밋 내역 살펴보기
<img alt="" src="https://velog.velcdn.com/images/nuypotss/post/f02c2012-85f8-48b6-8d5c-7f61a3b67529/image.png" /></p>
</blockquote>
<ul>
<li>기존에 존재하지 않았던 커밋(1a2a495f06d951c32125688ff9d5a9cc54c6bd1d)이 추가됨</li>
<li>main 브랜치와 test/fast-forward 브랜치가 같은 커밋을 바라보고 있음</li>
</ul>
<br />

<h3 id="③-병합-커밋-생성-merge-commit">③ 병합 커밋 생성: merge commit</h3>
<ul>
<li>빨리감기 병합 방법과는 다르게 기준 브랜치에 변경이 존재하는 경우에 사용하는 방법</li>
<li>즉, 기준 브랜치와 새로운 작업 브랜치의 변경 내용을 하나로 합치는 작업이 필요함</li>
</ul>
<blockquote>
<p>(1) test/fast-forward를 작업 브랜치로 설정
<img alt="" src="https://velog.velcdn.com/images/nuypotss/post/08aa381d-fef2-49d2-aca0-793e079ba4ca/image.png" /></p>
</blockquote>
<blockquote>
<p>(2) 임의로 파일 내용 수정</p>
</blockquote>
<blockquote>
<p>(3) 변경한 파일 추가 및 커밋 생성 명령 실행
<img alt="" src="https://velog.velcdn.com/images/nuypotss/post/e0eed546-0e31-409e-a88f-12d6944a054d/image.png" /></p>
</blockquote>
<blockquote>
<p>(4) main 브랜치를 작업 브랜치로 변경
<img alt="" src="https://velog.velcdn.com/images/nuypotss/post/dc597f5f-47f6-4cc7-aad9-b81a06e1554e/image.png" /></p>
</blockquote>
<blockquote>
<p>(5) git merge 명령어를 이용하여 test/local-branch의 작업 내용을 main 브랜치에 병합함
<img alt="" src="https://velog.velcdn.com/images/nuypotss/post/698ba432-59d2-44f0-bc61-5f2e56b2702f/image.png" /></p>
</blockquote>
<blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/nuypotss/post/c149af9f-6402-4479-b761-45c533f9fce7/image.png" /></p>
</blockquote>
<ul>
<li>빨리감기 병합과 다르게 git merge 명령어를 실행하면 터미널 결과와 같이 커밋 작성 에디터가 나타남</li>
<li>바로 이 부분이 기준 브랜치인 main 브랜치와 작업 브랜치인 test/local-branch 양쪽 변경 내용을 하나로 합치는 과정임<blockquote>
<p><img alt="" src="https://velog.velcdn.com/images/nuypotss/post/2c74dda4-f7de-4ed3-90f4-58b90fd27430/image.png" /></p>
</blockquote>
</li>
</ul>
<blockquote>
<p>(6) 병합 후, 커밋 내역 살펴보기
<img alt="" src="https://velog.velcdn.com/images/nuypotss/post/f8ceee9b-2096-499d-a10c-3d64018cff44/image.png" /></p>
</blockquote>
<ul>
<li>test/local-branch에서 작업 후 main 브랜치에서 병합된 커밋과
test/local-branch에서 작업 후 main 브랜치에 병합된 커밋이 하나의 병합 커밋으로 묶여 생성됨</li>
</ul>
<br />
<br />

<h2 id="3-충돌-해결하기">3. 충돌 해결하기</h2>
<ul>
<li>여러 개발자가 프로젝트를 진행하다 보면 병합 시, 충돌이 발생할 수 있음</li>
<li>충돌이란 깃이 자동으로 병합을 완료할 수 없는 상황을 말함</li>
<li>대부분은 두 명 이상이 각자의 작업 브랜치에서 동일한 코드를 수정한 후, 이를 병합할 때 충돌이 발생함</li>
<li>깃 입장에서는 두 브랜치가 같은 파일의 동일한 코드를 수정했기 때문에 어떤 내용을 최종적으로 반영해야 하는지 알 수 없음</li>
</ul>
<br />
<br />