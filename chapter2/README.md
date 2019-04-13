<h1>2. 첫 번째 앱 만들기</h1>
  <h2>2.1. 안드로이드 프로젝트 만들기</h2>
    <h3>2.1.1. 프로젝트 생성</h3>
    본격적으로 안드로이드 스튜디오를 이용해 프로젝트를 생성해보자.<br>
    <br>
    <b>Application Name: My First App</b><br>
    <b>Company Domain: example.com</b><br>
    <br>
    각 입력 란에 위와 같이 입력하면 안드로이드 스튜디오가 자동적으로 <code>패키지 이름(Package name)</code>과
    프로젝트의 저장 위치(Project location)을 자동으로 채워줄 것이다.<br>
    <br>
    <i>'include Kotlin support' 옵션이 체크되어 있다면 체크를 해제하자.</i><br>
    <br>
    <h4>패키지 이름(Package Name)</h4>
    안드로이드 앱을 가리키는 유일한(Unique) 값이다. 패키지 이름은 회사 도메인을 거꾸로 쓰고 마지막에 앱 이름을 지칭하는 문자열의 조합으로
    결정되는데, 회사 도메인은 전 세계에서 유일한 값이므로 당연히 패키지의 이름은 중복되지 않는다.<br>
    <br>
    <br>
    <h3>2.1.2. 대상 기기 및 SDK 선택</h3>
    Target Android Devices 단계에서는 개발하려는 앱이 어떤 기기에서 실행되는지, 이때 실행을 위한 최소한의 안드로이드 버전은 무엇인지 지정한다.<br><br>
    폰과 태블릿에 적용할 수 있도록 [Phone and Table]을 선택하고, 책에서는 API 21: Android 5.0 (Lollipop)을 적용했으나
    <code>Minimum SDK</code>에 맞추어준다면 최신 버전의 SDK를 사용해도 좋다.<br>
    <br>
    <h4>Minimum SDK</h4>
    앱을 실행하는데 필요한 최소 API 레벨을 지칭하는 정수. 앱을 설치하려는 기기의 API 레벨이 이 값보다 작으면 해당 기기에서는 앱을 설치할 수 없다.
    물론 우리의 경우 안드로이드 기기가 없기 때문에 에뮬레이터를 이용해 테스트를 해볼 것이므로 최신 버전의 SDK를 이용해도 상관이 없다.<br>
    <br>
    <i>실제로 앱을 출시하게 된다면 Minimum SDK의 설정에는 큰 문제가 생길 수 있다. Minimum SDK가 낮으면 많은 기기에서 호환되나 최신 API의 추가
    기능을 사용하지 못하고, 반대로 Minimum SDK를 높이면 최신 기능은 사용 가능하나 지원되는 기기의 수가 줄어든다.</i><br>
    <br>
    <a href="https://developer.android.com/about/dashboards/?hl=ko"><img src="https://github.com/dahee8kim/Android/blob/master/mdRes/android_version_distribution.JPG" title="안드로이드 버전별 분포" alt="안드로이드 버전별 분포"></a><br>
    <br>
    <br>
    <h3>2.1.3. 화면 구성 선택</h3>
    Add in Activity to Mobile 단계에서는 화면에서 앱을 구성할 화면 템플릿을 선택할 수 있다. 적어도 화면 한 개는 필요하므로 [Empty Activity]를
    선택하도록 한다.<br>
    <br>
    <h4>액티비티(Activity)</h4>
    안드로이드에서 화면을 구성하는 요소이며, 적어도 하나의 화면에는 반드시 하나의 액티비티가 필요하다.<br>
    <br>
    <i>액티비티는 후에 더 자세하게 학습하게 되므로 이번 단원에서는 예제를 가볍게 따라해보는 것으로 충분하다.</i><br>
    <br>
    <br>
    <h3>2.1.4. 액티비티 생성</h3>
    Configure Activity 단계에서는 액티비티의 이름을 지정할 수 있다. 액티비티는 <code>자바 클래스</code>와 레이아웃을 정의하는
    <code>XML</code> 파일의 쌍으로 구성된다. 현재 단계에서는 기본값으로 두고 프로젝트를 생성하자.<br>
<br>
<hr/>
<br>
    프로젝트가 모두 생성되면 안드로이드 스튜디오는 자동적으로 프로젝트를 빌드를 하게되고, 이 때 빌드 중임을 표시하는 메시지가 하단에 보인다.<br>
    <br>
    <i>빌드의 시간은 개개인의 컴퓨터 환경에 따라 다를 수 있다. 빌드가 모두 완료될 때 까지 기다려보자.</i><br>
    <br>
<br>
<br>
<h2>2.2. 프로젝트 구성</h2>
<img src="https://github.com/dahee8kim/Android/blob/master/mdRes/android_project_structure.png" alt="안드로이드 프로젝트 구조도" title="안드로이드 프로젝트 구조도"><br>
<h3>2.2.1. app 부분 살펴보기</h3>
프로젝트는 크게 <code>app</code>과 <code>Gradle Scripts</code> 두 부분으로 구성된다. app 부분은 <code>메니페스트(manifests 폴더), 소스코드(java 폴더), 리소스(res 폴더)</code>가 위치한다.<br>
<br>
소스코드는 앱의 로직을 자바 코드로 작성한 파일을 말하며, 리소스란 소스코드를 제외한 앱 개발에 필요한 모든 자원(레이아웃, 아이콘, 이미지...)이 된다.<br>
<br>
<h4>manifests: 매니페스트</h4>
앱을 구성하는 요소를 정의하는 파일이 위치한다.<br>

```xml
// AndroidManifest.xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.example.myapplication">

    <application
        android:allowBackup="true"
        android:icon="@mipmap/ic_launcher"
        android:label="@string/app_name"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:supportsRtl="true"
        android:theme="@style/AppTheme">
        <activity android:name=".MainActivity">
            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>
</manifest>
```

위의 매니페스트 파일을 해석하면 이 앱은 하나의 <code>액티비티(activity)</code> 를 가지고 있고, 이 액티비티가 메인 액티비티이며, 실행 가능하다는 내용을 <code>&lt;intent-filter&gt;</code>에 포함하고 있다. 만약 화면이 두 개인 앱이었다면 액티비티가 두 개 필요하고, 모두 매니페스트 파일 내부에 기술해야 한다.<br>
<br>
<h4>java: 자바 소스</h4>
자바 소스 파일이 위치하는 곳이며 일반 소스 파일과 테스트 소스 파일을 작성하는 폴더로 나누어져 있다.<br>
<h5>MainActivity.java</h5>
안드로이드 스튜디오에서 새로운 프로젝트를 생성 마법사로 생성했을 때 처음에 보이는 파일이다. 클래스 정의와 앱을 시작하는 부분이다.<br>
<h5>ExampleInstrumentedTest.java (androidTest)</h5>
앱의 생명주기 및 이벤트를 제어하는 기능을 갖춘 통합 테스트 코드.<br>
<h5>ExampleUnitTest.java (test)</h5>
데이터 및 동작에 대해 단위 테스트가 작성되어 있다.<br>
<br>
<h4>res: 리소스</h4>
앱을 개발할 때 필요한 그림, 레이아웃, 아이콘, 간단한 값 등의 리소스가 <code>drawable, layout, mipmap, values</code> 디렉터리에 위치한다.<br>
<h5>res/drawable</h5>
jpg, png, gif, 나인패치와 같은 이미지 파일과 안드로이드에서 이미지를 표현하는 특별한 XML 파일이 위치한다.<br>
<h5>res/layout</h5>
사용자 인터페이스 레이아웃을 정의하는 XML 파일이 위치한다.<br>
<br>
<i>프로젝트를 생성하면 함께 생성되는 activity_main.xml은 메인 액티비티의 레이아웃을 정의하고 있다.</i><br>
<h5>res/mipmap</h5>
앱을 실행하는 아이콘 파일이 위치한다. 아이콘을 나타내는 화면의 해상도에 따라 <code>mdpi, hdpi, xhdpi, xxhdpi, xxxhdpi</code>로 구분한다.<br>
뒤로 갈 수록 해상도가 높아진다.<br>
<h5>res/values</h5>
<code>문자열(strings.xml), 색(colors.xml)</code>과 같은 단순한 값이 들어있는 XML 파일이 위치한다. 또한 <code>(스타일)styles.xml</code>도 포함이 된다.<br>
<br>
<br>
<h3>2.2.2. Gradle Scripts 부분 살펴보기</h3>
<h3>2.3. 그레이들 빌드 시스템</h3>
<h3>2.4. 앱 실행</h3>
