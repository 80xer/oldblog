title: Microsoft Visual Studio Community 2015 에서 ASP.NET 5, Web API, Angular.js, Grunt, Bower 사용하기
date: 2016-01-25 14:30:31
tags:
---

[ASP.NET 5: Jump Start to AngularJS with MVC 6 Web API](http://proudmonkey.azurewebsites.net/asp-net-5-jump-start-to-angularjs-with-mvc-6-web-api/)를 preview가 아닌 정식버전 ASP.NET5로 따라하기.

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

모든 javascript 파일을 넣을 **Scripts** 라는 폴더와 ASP.NET MVC의 모델에 해당하는 클래스들을 넣어둘 **Models** 폴더를 루트폴더 아래에 미리 생성한다.

![Scripts와 Models폴더를 생성](images/16012501-폴더생성.png)


### 패키지 매니저를 이용해 필요한 패키지들을 설치하기.
패키지 매니저 중 npm과 bower를 이용해서 패키지들을 설치한다.
먼저 npm을 이용해서 Grunt와 Grunt플러그인들을 설치한다.
프로젝트에 우클릭하고 **추가>새항목** 을 실행하여 **새 항목 추가** 창을 띄운다.
**새 항목 추가** 창의 왼쪽에 **설치됨>Client-side**를 선택하고 중앙의 항목중 **NPM 구성 파일** 을 선택한다.

![npm 구성 파일 선택](images/16012501-npm구성파일선택.png)

**추가** 버튼을 클릭하면 npm 구성파일인 package.json 파일이 프로젝트에 추가된다.
package.json 파일을 더블클릭하여 열고 애플리케이션에서 사용할 grunt, grunt-contrib-uglify, grunt-contrib-watch 세가지 패키지를 아래와 같이 추가한다.

![npm 구성 파일 선택](images/16012501-npm구성파일편집.png)

추가한 후 package.json 파일을 저장하게 되면 콘솔에서 npm install 한것 처럼 자동으로 패키지들이 설치되고 솔루션 탐색기의 **종속성>NPM** 아래에 패키지들을 확인 할 수 있다.

![솔루션 탐색기의 npm 모듈들](images/16012501-솔루션탐색기에 나타난 패키지들.png)

실제로 윈도우 탐색기를 통해 확인해보면 프로젝트소스 루트 폴더아래에 node_modules 라는 폴더안에 패키지들이 설치되어 있다. 

![실제로 설치된 npm 모듈들](images/16012501-설치된패키지들.png)

### Grunt 설정하기.
Grunt는 node.js로 만들어진 모듈로 애플리케이션의 Client 리소스들에 대하여 여러 작업들을 자동화할 수 있는 오픈소스 Javascript Task Runner이다.
즉 Client 파일들을 합치거나 난독화하거나 복사하는등의 개발/배포 과정에서 필요한 귀찮고 반복적인 작업들을 다양한 플러그인들을 이용해 명령어 한번으로 자동화 시킬 수 있는 도구이다.


### ASP.NET MVC 설정하기.

### 모델 추가하기.

