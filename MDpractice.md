# **Django 시작하기**

## 순서

    장고 start -> 앱만들기 -> 모델 정의 -> 마이그레이션 -> 플래시 메시지
    -> 장고 관리자 -> 장고 레이아웃 및 폼양식 -> 템플릿 만들기
    -> 편집 폼 및 레이아웃 -> 삭제 폼 레이아웃 -> 로그인/로그아웃


 
## 들어가기

### 1. 프로젝트 작성:

    django-admin startproject your_projectname을 사용하여 새 프로젝트를 시작(관리자권한)

### 2. 앱 생성: 

    python manage.py startapp yourappname학습을 이용하여 웹사이트의 구성 요소(예: 블로그, 갤러리 등)를 대표하는 앱을 생성

### 3. 모델 정의: 

    앱의 models.py파일에서 데이터베이스 테이블을 정의

#### - ' (3.) 모델정의 -> (4.) 마이그레이션 ' 과정:
    모델을 변경하고(with 'table') 마이그레이션을 생성(with 'db')하고 변경 사항을 데이터베이스에 적용하는 프로세스

#### - HOW?
    1.새 모델을 정의하거나 기존 모델을 변경 (새로운 테이블을 생성하거나 수정할 때)
    2. 명령을 실행하여 새 마이그레이션을 수행 makemigrations. (새로운 데이터 베이스 생성)
    3. 명령을 실행하여 모델의 변경 사항을 데이터베이스에 적용 migrate. (테이블 생성, 수정 -> 기존 DB)

#### < 실습 1 > 새 마이그레이션 생성

    python manage.py makemigrations 

#### <실습 2> sql구문 미리보기

    python manage.py sqlmigrate blog 0001
    
#### < 실습 3 > 변경사항을 데이터베이스에 적용

    python manage.py migrate
    
#### < 실습 4 > 프로젝트에서 해당     마이그레이션의 상태를 나열해보자.

    "no changes detected"
    -> 모델변경 X (세션, 브라우저) -> 앱이 지정되지 않았다. ex) python manage.py makemigrations 앱이름
    -> INSTALLED_APPS에 등록된 앱이 인식하지 못 할 경우
    -> 마이그레이션 파일이 이미 있다.
    -> 모델 정의 오류
    -> 수동 삭제할 경우

#### - ex) 모델정의
    blog.models.py -> django.db.models.Model의 하위클래스 및 필드가 명시되어야 한다.
    - 상속해서 클래스를 생성 -> DEFAULT_AUTO_FIELD = 'django.db.models.BigAutoField'
    - __str-- 문자열 표현 재정의 메소드
    - class Meta 구성

#### - ex) 내장모델과 함께 사용하며, 참조키를 생성한다.
    from django.contrib.auth.models import User

### 4. 보기와 템플릿 작성: 

    검토를 통해 로직을 처리하고 템플릿을 사용하여 사용자에게 보여주기 HTML을 작성

### 5. URL 설정: 

    urls.py파일에서 URL 패턴을 정의하여 보기(view)와 연결

### 6. 데이터베이스 카탈로그: 

    python manage.py 
    makemigrations과 python manage.py migrate 사용하여 모델 변경 사항을 데이터베이스에 적용

### 7. 정적 및 미디어 파일 관리: 

    CSS, JavaScript, 이미지 등의 정적 파일을 관리하고 설정

### 8. 개발 서버 실행: 

    python manage.py runserver기반으로 개발 서버를 실행하고 웹사이트 확인

### 9. 배포: 
  
    웹사이트가 준비되어 있는 호스팅 서비스에 포함하여 인터넷에 배포를 공개

## 참조

### 장고 클래스 기반이란

    listview 목록표시 -> listview 목록 세부 표시 -> update view
    -> CreateView 폼 만들기 -> Formview 폼등록하기 -> LoginView
    (추가) 암호재설정 활성화, 사용자 프로필 추가
 
### 'django-admin'의 db관련 명령어

    makemigrations -> db 새로 생성

    migrate -> 기존 생성된 db에 테이블 수정

    sqlflush -> ???

    sqlmigrate _sql 미리보기 -> 쿼리 출력

    sqlsequencereset -> ???

### 장고 관리자

    - 관리자 페이지에 모델을 표시를 하려면 admin.py 속성값을 추가해야한다.
    1) admin.site.register(Post) 테이블 등록
    2) 127.0.0.1:8000/admin으로 접속해서 blog/post 확인 후 게시물 몇 개 등록
    3) 등록된 게시물을 표시한다. blog.view.py
    4) setting.py TEMPLATE = [ 'DIRS': [BASE_DIR/'templates'],] 추가
