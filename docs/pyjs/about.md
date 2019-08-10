# About 

<http://pyjs.org/About.html>

## What is pyjs? pyjs 란 무엇인가요?

pyjs is a Rich Internet Application (RIA) Development Platform for both Web and Desktop. With pyjs you can write your JavaScript-powered web applications entirely in Python.
pyjs 는 웹과 데스크톱 플랫폼에 모두 대응하는 RIA(Rich Internet Application)입니다. pyjs 를 사용하면 자바 스크립트 기반 웹 애플리케이션을 파이썬만으로 작성할 수 있습니다.

pyjs contains a Python-to-JavaScript compiler, an AJAX framework and a Widget Set API. pyjs started life as a Python port of Google Web Toolkit, the Java-to-JavaScript compiler.
pyjs 에는 파이썬->자바스크립트 컴파일러, AJAX 프레임워크, 위젯 세트 API 가 포함되어 있습니다. pyjs 는 자바->자바스크립트 컴파일러인 Google Web Toolkit 의 파이썬 포트로 시작되었습니다.

## What is pyjs Desktop? pyjs Desktop 은 무엇인가요?

pyjs Desktop allows the exact same Python web application source code to be executed as a standalone desktop application (running under Python) instead of being stuck in a Web browser.
pyjs Desktop 을 사용하면 Python 웹 애플리케이션을 웹 브라우저를 넘어 (파이썬 아래 실행되는) 단독 실행 데스크탑 애플리케이션으로 만들 수 있습니다. 

For Free Software platforms, most Linux Distributions now come with pyjs and pyjs Desktop pre-packaged: Debian/Testing, FC13, ArchLinux and Gentoo.
자유 소프트웨어 플랫폼의 경우 대부분의 리눅스 배포판에서 pyjs 와 pyjs Desktop 이 사전 패키지로 제공 됩니다. (데비안/Testing, FC13, 아크 리눅스, 젠투 등)

For Windows, pyjs Desktop uses MSHTML. Since MSHTML comes pre-installed on Windows (as part of IE), there is very little extra to download (other than Python itself).
윈도우의 경우 pyjs Desktop 은 MSHTML 을 사용합니다. MSHTML 은 윈도우에 (IE 일부로) 설치되어 있어 (파이썬 외에는) 추가로 다운로드 받아야 할 것이 거의 없습니다.

## Why should I use pyjs? pyjs 를 사용해야하는 이유는 무엇인가요?

You can write web applications in Python - a readable programming language - instead of in HTML and JavaScript, both of which become quickly unreadable for even medium-sized applications. Your application's design can benefit from encapsulating high level concepts into classes and modules (instead of trying to fit as much HTML as you can stand into one page); you can reuse - and import - classes and modules.
HTML 과 자바스크립트 대신 - 가독성이 좋은 프로그래밍 언어인 - 파이썬으로 웹 애플리케이션을 만들 수 있습니다. HTML 과 자바스크립트 중규모 이상 애플리케이션에서는 가독성이 많이 떨어집니다. 애플리케이션 디자인시 (페이지 하나에 모든걸 집어넣는 HTML 과는 달리) 상위 레벨 개념을 클래스와 모듈로 추상화할 수 있으며, 임포트해서 재사용할 수 있습니다.

Also, the AJAX library takes care of all the browser interoperability issues on your behalf, leaving you free to focus on application development instead of learning all the "usual" browser incompatibilities.
또한, AJAX 라이브러리를 대신해 모든 브라우저를 대응해주므로, 브라우저들의 비호환되는 부분을 학습할 필요없이 애플리케이션 개발에만 집중할 수 있게 해줍니다.

## Who are the developers? 개발자들은 어떤 분들인가요?

* The original code for the UI Widget Set and the DOM support libraries came from Google Web Toolkit, and was ported by James Tauber. James wrote the original pyjs compiler.
* UI 위젯 세트와 DOM 지원 라이브러리는 Google Web Toolkit 코드 기반으로 James Tauber 님이 포팅했습니다. James 는 pygs 컴파일러를 작성 했습니다.
* Luke Leighton took over the project in 2008, and updated the UI Widget Set, improved the compiler and created the three pyjs Desktop runtimes.
* Luke Leighton 은 2008 년 프로젝트에 참여해 UI 위젯 세트를 업데이트 하고, 컴파일러를 개선했으며, pyjs Desktop 런타임 3개를 만들었습니다.
* Bernd Dorn and his colleagues from Lovely Systems did some dramatic compiler improvements for 0.5.
* Bernd Dorn 과 동료들은 0.5 버전에 드라마틱한 컴파일러 개선을 이루어냈습니다.
* Kees Bos joined because he was not interested in learning JavaScript, but learn he definitely did. Kees is responsible for the majority of the vast improvements and the more esoteric Python interoperability in the compiler, such as "yield", long data type and much much more.
* Kees Bos 는 자바 스크립트를 배우는데 흥미를 느끼지 못해 참여했고 확실히 그렇다는 걸 알게 되었습니다. Kees 는 기능 향상과 "yield", 롱 데이터 타입 같은 난해한 파이썬 요소들을 컴파일러에 적용하는 것을 담당하고 있습니다.
* C Anthony Risinger took over the project in 2012 to improve the infrastructure and make the project more appealing to a larger audience.
* C Anthony Risinger 는 2012 프로젝트에 참여해 인프라를 개선하고 많은 사람들에게 전파하고 있습니다.

