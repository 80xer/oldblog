title: Microsoft Visual Studio Community 2015 에서 ASP.NET 5, Web API, Angular.js, Grunt, Bower 사용하기(업데이트중)
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
즉 Client 파일들을 합치거나 축소시키거나 복사하는등의 개발/배포 과정에서 필요한 귀찮고 반복적인 작업들을 다양한 플러그인들을 이용해 명령어 한번으로 자동화 시킬 수 있는 도구이다.

Scripts 폴더안에 있는 javascript 모든파일들을 합치고 축소시켜서 wwwroot 폴더아래에 app.js 파일로 생성할 수 있는 Grunt 설정을 해본다.

솔루션 탐색기의 프로젝트에서 우클릭 **추가>새 항목** 을 선택하여 **새 항목 추가** 창을 띄운다.
**새 항목 추가** 창에서 우측 **Client-side**를 선택하고 중앙의 항목중 **Grunt 구성파일**을 선택하고 **추가** 버튼을 클릭한다.

![Grunt 구성파일 생성](images/16012501-Grunt구성파일생성.png)

생성된 **gruntfile.js** 를 아래와 같이 수정한다.

![gruntfile.js](images/16012501-gruntfile.png)

위의 gruntfile은 크게 세부분으로 이루어져있다.
첫번째 부분은 grunt.loadNpmTasks 로 npm을 통해 설치했던 Grunt 플러그인들을 로딩하는 부분이다.
두번째 부분은 grunt.initConfig 로 각 플러그인들의 실행에 관련된 설정을 해주는 부분으로
uglify 는 Scripts 폴더의 app.js 와 그 하위폴더를 포함한 모든 파일들을 wwwroot 안에 app.js 로 합쳐서 축소시킨다.
watch 는 Scripts 폴더안의 파일들을 지켜보다가 변경 사항이 발생하면 uglify 플러그인을 실행한다.
세번째 부분은 grunt.registerTask 로 하나의 Task에서 실행할 플러그인들을 지정하여 grunt task 를 등록하는 부분이다.
'default'라는 이름의 task에 uglify와 watch 플러그인을 등록했다.

gruntfile.js 를 저장하고 Visual Studio의 상단메뉴중 **보기>다른 창>작업 러너 탐색기**를  선택하여 작업 러너 탐색기 창을 열어보면 다음과 같이 grunt 작업을 볼 수 있다. 만약 작업들이 안보인다면 작업 러너 탐색기 좌상단의 리프레쉬 버튼을 클릭한다.

![작업 러너 탐색기](images/16012501-작업러너탐색기.png)

**default** 작업위에 우클릭 **실행** 을 선택해서 작업을 실행해 보면 아직 Scripts 폴더아래에 파일이 없기 때문에 아래와 같은 출력을 볼 수 있다.

![작업실행-Scripts 폴더아래 작업을 실행할 파일이 없다](images/16012501-작업실행1.png)

### 모델 추가하기.

위에서 만든 Models 라는 폴더에 우클릭 **추가>클래스**를 선택하여 "DOTAHero"라는 클래스를 추가 하고 아래와 같이 편집한다.

![DOTAHero.cs](images/16012501-dotahero.png)

한번 더 같은 Models 폴더에 "HeroManager" 라는 클래스를 추가하고 아래와 같이 편집한다.

![HeroManager.cs](images/16012501-heromanager.png)

HeroManager 클래스는 다음을 포함한다.
- readonly property 로 정의된 hero들의 리스트(실제로 데이터베이스에서 가져와야할 테지만 예제이므로 간단히 스태틱한 리스트로 정의한다.)
- 모든 히어로를 반환하는 GetAll property
- 특정 type의 히어로 리스트를 반환하는 GetHeroesByType() 메소드
- 특정 ID를 갖는 히어로를 반환하는 GetHeroByID() 메소드

### Web API Heroes Controller 추가하기.
Controllers 폴더에 우클릭 **추가>새 항목**  을 선택하여 **새 항목 추가** 창을 띄운다.
좌측에 Server-side 를 선택하고 중앙의 항목중 **Web API 컨트롤러 클래스** 를 선택하고 이름을 **HeroesController.cs** 로 입력한후 **추가**버튼을 클릭한다.

![HeroesController.cs 추가](images/16012501-heroescontroller추가.png)

Controllers 폴더아래에 추가된 HeroesController.cs 파일을 연다.
상단 using 문에 위에서 추가한 모델 네임스페이스를 추가하고 아래 api 구현 부분의 기본내용을 아래와 같이 편집한다.

![HeroesController.cs](images/16012501-heroescontroller.png)
