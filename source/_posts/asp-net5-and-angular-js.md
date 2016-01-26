title: Microsoft Visual Studio Community 2015 에서 ASP.NET 5, Web API, Angular.js, Grunt, Bower 사용하기
date: 2016-01-25 14:30:31
tags:
---

[ASP.NET 5: Jump Start to AngularJS with MVC 6 Web API](http://proudmonkey.azurewebsites.net/asp-net-5-jump-start-to-angularjs-with-mvc-6-web-api/)를
preview가 아닌 정식버전 ASP.NET5로 따라하기.

asp.net5를 사용하기 위해 visual studio community 2015 버전을 설치한다.([다운로드](https://www.visualstudio.com/downloads/download-visual-studio-vs?&WT.srch=1&WT.mc_ID=SEM_yewnJZUr))


### ASP.NET 5 프로젝트를 생성하기.
VS를 실행하고 **파일>새로만들기>프로젝트** 메뉴를 통해 **새 프로젝트** 대화창을 띄운다.
좌측 템플릿 분류에서 **설치됨>템플릿>Visual C#>웹** 을 선택하고 중앙에서 **ASP.NET 웹 응용프로그램**을 선택.
하단에 프로젝트 이름으로 **AngularJS1** 를 입력하고 **확인**!

![새 프로젝트 창](images/16012501-새프로젝트.png)

이어서 **새 ASP.NET 프로젝트** 창이 뜨면 좌측에서 ASP.NET 5 템플릿을 선택하면 되는데... ASP.NET 5 템플릿 아래에는 **Get ASP.NET 5 RC** 라는 것만 있다. 클릭하면 ASP.NET 5 템플릿을 다운로드 한다. 약간의 시간이 걸린다.
다운로드가 완료되면 같은 곳에 **Empty**, **Web API**, **Web Application** 세가지 템플릿이 존재한다.

![새 ASP.NET 프로젝트 창](images/16012501-새asp.net프로젝트.png)

Web API를 선택하고 **확인**을 클릭하면 기본 WebAPI의 뼈대를 갖춘 프로젝트가 생성된다.

![새 ASP.NET 프로젝트 창](images/16012501-프로젝트생성.png)

### Scripts 폴더와 Models 폴더를 추가하기.
우측 **솔루션탐색기**에서 프로젝트루트항목에 오른쪽 클릭하여 **추가>새폴더** 를 통해

![프로젝트 항목에서 우클릭 추가 > 새폴더](images/16012501-프로젝트우클릭메뉴.png)

모든 javascript 파일을 넣을 **Scripts** 라는 폴더와
ASP.NET MVC의 모델에 해당하는 클래스들을 넣어둘 **Models** 폴더를 루트폴더 아래에 미리 생성한다.

![Scripts와 Models폴더를 생성](images/16012501-폴더생성.png)


### 패키지 매니저를 이용해 필요한 패키지들을 설치하기.

### Grunt 설정하기.

### ASP.NET MVC 설정하기.

### 모델 추가하기.

주변 사람들이 괜찮다는 얘기를 많이 하고 표지 디자인이 맘에 들어서 읽기 시작한 책이다. 기술서적이나 글만 보다 보니 좀 가볍게 읽고 싶은 마음도 있었다. 소프트웨어 장인(Software Craftsmanship)
