## 0805_03_pjt(관통 프로젝트)

### 반응형 웹 페이지 구현

- 프로젝트 목표
  
  - HTML을 통한 웹 페이지 마크업 이해
  
  - CSS 라이브러리의 이해와 활용
  
  - Bootstrap 컴포넌트 및 Grid system을 활용한 반응형 레이아웃 구성

#### 01_nav_footer_html

###### 학습한 내용

- navbar 구현 시에는 bootstrap 을 활용하는 게 편하다.

- 하이퍼 링크 역할을 하는 로고 이미지는 내가 직접 사이즈(width,height) 지정해 주는 게 편하다.

- <mark>Modal Component를 띄우려면 레이아웃이 겹치지 않게 Body의 맨위에 두는 것이 좋다. </mark>

    - tab-index:-1 은 tab 눌렀을 때(키보드) index 임 상관X

< 내비게이션 메뉴 중 Login은 클릭 시 Bootstrap Modal Component가 나타납니다.
• Modal Component 내부에는 HTML form 요소를 배치합니다. >

```html
<li class="nav-item">
  <a class="nav-link" href="exampleModal" role="button" data-bs-toggle="modal" data-bs-target="#exampleModal">Login</a>
</li>
```

- **<mark>data-bs-target을 모달 id랑 같게 해줘야 함.</mark>**

```html
/*body 맨 위에*/
<div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
</div>
```

넣어주고 modal body에 form 에서 로그인 형식 복사해서 넣어주면 됨. title이랑 버튼은 그대로 놔두고!

- navbar, footer 는 sticky-top, sticky-bottom으로 고정해주기

###### 어려웠던 점

- login link(a) 누르면 로그인 모달창 띄우는 게 어려웠다. 

#### 02_home.html

- Bootstrap Card Component 사용

- Card 기본으로 1개 보이는 걸로 넣고, sm 이상되면 3개 보이게 함
  
  ```html
  <div class="row row-cols-1 row-cols-sm-3 g-4">
  </div>
  ```

- row-cols는 한 행을 나눠주고 row 하고 밑에 col-x-3 넣어주면 그 row 안에서 나눠 가짐

#### 03_community.html

###### 학습한 내용

- main 을 container로 정해주고(문제에서 주어진 기본으로 차지하는 사이즈가 html main 100%니까) aside, section을 div class="row"로 묶어줌

- aside, section 각자 class="col-lg-2", class="col-lg-10" 해주고

- lg(992px)이상일 때 띄워야하는 table을 감싼 section은 기본값을 d-none 주고, d-lg-block으로 lg가 됐을 때 보이게 함.

- 작은 사이즈 일때 보여야 하는 article을 감싼 section은 **d-lg-none** 으로 화면이 커졌을 때 안보이게 함.

- 위처럼 해서 lg보다 작을때 article, lg 이상일때 table이 보이게 함.

###### 어려웠던 점

- 어떤 걸 container,row 로 잡을지 헷갈리고, 반응형으로 각 요소의 사이즈를 바꾸고 보였다 안보였다 하는 걸 구현 하는 게 어려웠다. 
  
  -> 한 div(row인) 안에 감싸서 column 사이즈를 나눠주고, d-none 주면 되는 걸 몰라서 어려웠음

##### 소감

부트스트랩으로 웹 페이지를 만든 건 처음이라, 활용하고 응용해서 구현하는 게 생각보다 훨씬 어려웠다..
