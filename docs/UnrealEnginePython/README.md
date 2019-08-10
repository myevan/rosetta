# README 

<https://github.com/20tab/UnrealEnginePython/blob/76ae4b11bfd1cf46db0b191657c0ec2263b12741/README.md>

Embed Python in Unreal Engine 4
언리얼 엔진4 파이썬 임베딩

Teaser (by Kite & Lightning): https://twitter.com/KNLstudio/status/932657812466843648
티져

Fixing Mixamo RootMotion tuturial: https://github.com/20tab/UnrealEnginePython/blob/master/tutorials/FixingMixamoRootMotionWithPython.md
믹사모 루트 모션 튜토리얼 수정

Funny snippets for working with StaticMesh and SkeletalMesh assets: https://github.com/20tab/UnrealEnginePython/blob/master/tutorials/SnippetsForStaticAndSkeletalMeshes.md
스태틱 메쉬와 스켈레탈 메쉬 애셋 작업 관련 재밌는 스니펫 모음

More tutorials: https://github.com/20tab/UnrealEnginePython/tree/master/tutorials
추가 튜토리얼

## How and Why ? (어떻게? 왜?)

This is a plugin embedding a whole Python VM (versions 3.x [the default and suggested one] and 2.7) In Unreal Engine 4 (both the editor and runtime).
언리얼 엔진 파이썬은 언리얼 엔진4 에 파이썬 VM을 완전히 임베딩한 (에디터 및 런타임) 플러그인입니다. (기본적으로 파이썬 3.x 지원 및 추천하며 2.7 도 지원됩니다.)

The Python VM tries to give easy access to all of the UE4 internal api + its reflection system. This means you can use the plugin to write other plugins, to automate tasks, to write unit tests and to implement gameplay elements.
파이썬 VM 은 언리얼 내부 API 와 리플렉션 시스템 전체에 쉽게 접근할 수 있는 방법을 제공하는 것을 목표로 하고 있어, 플러그인 제작, 업무 자동화, 유닛 테스트, 게임 플레이 요소 구현에 사용될 수 있습니다.

It is not meant as a way to avoid blueprints or c++ but as a good companion to them (albeit reducing the amount of c++ required for coding a game could be an interesting thing ;). If your development pipeline is already python-based (Maya, Blender, ...), this plugin could easily help you in integrating unreal into it.
블루프린트나 C++ 를 완전히 대체하기보다는 (C++ 코딩을 줄이는데) 좋은 동반자 역할을 할 것입니다. 현재 개발 파이프 라인에 이미 파이썬 기반(마야, 블렌더, ...)이라면 언리얼 엔진 통합에 큰 도움이 될 것입니다. 

If you want to have an idea of what the plugin can do, jump here: https://github.com/20tab/UnrealEnginePython/blob/master/tutorials/YourFirstAutomatedPipeline.md
플러그인으로 할 수 있는 것들에 대해 할 수 싶다면 다음 링크를 참고해주시기 바랍니다.

In addition to this, the plugin automatically adds an actor class (PyActor), a pawn class (PyPawn), a character class (PyCharacter) and a component class (PythonComponent) for "gentle" integration of python in your games.
이외에도 액터(PyActor), 폰(PyPawn), 캐릭터(PyCharacter), 컴포넌트(PythonComponent)등이 추가되어 있어 게임내 파이썬을 "젠틀하게" 통합시킬 수 있스니다. 

In the spirit of automating tasks, even wrappers for third party libraries used by UE4 are exposed in a 'pythonic' way. As an example the FbxSdk is exposed to allow low-level interaction with Fbx files. This is an example extracting animation curves: https://github.com/20tab/UnrealEnginePython/blob/master/examples/fbx_curves_extractor.py
업무 자동화 측면에서도 써드 파티 라이브러리 랩퍼들을 '파이썬스러운' 방법으로 사용할 수 있습니다. 예를 들어 Fbx 파일들이 저수준 통합을 위해 FbxSdk 가 제공됩니다. 다음은 애니메이션 커브를 뽑아내는 예제입니다.  

Another funny feature (well, a side effect ;) is that you can change your python code even after the project has been packaged. You can potentially build a completely new game from an already packaged one.
(사실 사이드 이펙트에 가깝겠습니다만) 재밌는 장점 중 하나는 프로젝트를 패키징한 이후에도 파이썬 코드를 변경할 수 있다는 점입니다. 이점을 이용하면 이미 패키지된 게임에서 완전히 새로운 게임을 만들 수 있습니다.

Once the plugin is installed and enabled, you get access to the 'PythonConsole' item in the 'Development Menu', you can use it to trigger python commands directly from the editor. There is even an experimental Editor/IDE included, you can run it from the Window/Layout/Python Editor menu item.
플러그인을 설치 후 활성화시키면, '개발 메뉴'에서 '파이썬 콘솔'을 사용할 수 있습니다. 여기에서는 에디터에서 파이썬 커맨드를 실행할 수 있습니다. 이것은 실험적으로 에디터/IDE 에 포함되어 있으며 윈도우> 레이아웃> 파이썬 에디터 메뉴에서 실행할 수 있습니다.

All of the exposed engine features are under the 'unreal_engine' virtual module (it is completely coded in c into the plugin, so do not expect to run 'import unreal_engine' from a standard python shell)
엔진 기능들은 가상 모듈 `unreal_engine` 을 통해 접근 할 수 있습니다. (플러그인내 c 로 구현된 것이므로, 스탠다드 파이썬 쉘에서는 임포트할 수 없습니다.)

The currently supported Unreal Engine versions are 4.12, 4.13, 4.14, 4.15, 4.16, 4.17, 4.18, 4.19, 4.20, 4.21 and 4.22
현재 지원되는 파이썬 엔진은 다음과 같습니다: 4.12, 4.13, 4.14, 4.15, 4.15, 4.17, 4.18, 4.19, 4.20, 4.21, 4.22

We support official python.org releases as well as IntelPython and Anaconda distributions.
공식 파이썬 릴리즈(인텔 파이썬, 아나콘다 배포판 포함)을 지원하고 있습니다.

Note: this plugin has nothing to do with the experimental 'PythonScriptPlugin' included in Unreal Engine >= 4.19. We aim at full integration with engine and editor (included the Slate api, check here: https://github.com/20tab/UnrealEnginePython/blob/master/docs/Slate_API.md), as well as support for the vast majority of python features like asyncio, coroutines, generators, threads and third party modules.
참고: 언리얼 엔진 파이썬 플러그인은 언리얼 엔진4.19 부터 포함된 파이썬 스크립트 플러그인과는 관련이 없습니다. 우리는 엔진과 (슬레이트 API를 포함한) 에디터의 완벽한 통합과 파이썬의 중요 기능(비동기 io, 코루틴, 제너레이터, 쓰레드, 써드파티 모듈)이 지원을 목표로 하고 있습니다.

## Binary installation on Windows (64 bit) 윈도우(64비트) 바이너리 설치 

Check in the releases page (https://github.com/20tab/UnrealEnginePython/releases) if there is a binary version that matches your configuration (otherwise open an issue asking us for it [please specify the python version too]) and download it.
릴리즈 페이지에서 원하는 바이너리 버전을 다운로드 받으시기 바랍니다. (적합한 바이너리가 없다면 파이썬 버전을 명시해 문의 부탁드립니다.)

Binary releases are in two forms: standard and embedded. Standard uses the python installation of your system, so ensure the python installation directory is in your system PATH environment variable (otherwise you will get an error while loading your project). Embedded releases include an embedded python installation so you do not need to have python in your system.
바이너리는 스탠다드와 임베디드 2가지 형태로 릴리즈됩니다. 스탠다드 릴리즈는 시스템에 설치된 파이썬을 사용하므로 파이썬 설치 디렉토리가 시스템 환경 변수 PATH 에 존재하는지 확인이 필요합니다. (파이썬이 설치되지 않았다면 프로젝트 로딩시 에러가 발생할겁니다.) 임베디드 릴리즈는 임베디드 파이썬이 포함되어있어 시스템에 파이썬이 없어도 사용할 수 있습니다.

Create (if it does not already exist) a Plugins directory in your project root directory (at the same level of Content/ and the .uproject file) and unzip the plugin into it. If your project is named FooBar you will end with FooBar/Plugins/UnrealEnginePython.
프로젝트 루트 디렉토리에 플러그인 디렉토리가 필요합니다. 플러그인 디렉토리가 없다면 프로젝트 파일(.uproject)나 Content 폴더와 같은 위치이에 Plugins 디렉토리를 만들면 됩니다. 프로젝트 이름이 FooBar 라면 FooBar/Plugins/UnrealEnginePython 라는 경로를 갖게 됩니다.

Open your project and go to the Edit/Plugins menu. Go to the bottom and under "Project/Scripting Languages" enable UnrealEnginePython.
프로젝트를 열고, 편집 > 플러그인 메뉴로 이동합니다. 플러그인 다이얼로그 하단에 "프로젝트 > Scripting Languages" 에서 UnrealEnginePython 을 활성화시켜주세요.

Restart your project and you should see the PythonConsole under the "Window/Developer Tools" menu
프로젝트를 재시작하면 "윈도우 > 개발자 도구" 메뉴에서 파이썬 콘솔을 찾으실 수 있을 겁니다.

Binary releases are mainly useful for editor scripting, if you want to package your project for distribution and you need the python runtime, you need a source release (see below).
바이너리 릴리즈는 주로 에디터 스크립팅을 하는데 유용합니다. 배포용 패키지에서 파이썬 런타임이 필요하다면 아래 나오는 소스 릴리즈를 사용하셔야 합니다.

If instead, you want to package your project without python, just remember to change the UnrealEnginePython.uplugin to have this line: https://github.com/20tab/UnrealEnginePython/blob/master/UnrealEnginePython.uplugin#L20 set as "Editor" instead of "Runtime"
대신 파이썬 없이 프로젝트를 패키지하려면 UnrealEnginePython.uplugin 에서 Runtime 대신 Editor 로 설정해주셔야 합니다.

## Installation from sources on Windows (64 bit) 윈도우(64비트) 소스 설치

Currently python3.6, python3.5 and python2.7 are supported. It is highly suggested to have a python system wide installation (by default the official python distributions are installed in user's home directory) with the PATH environment variable including it (if you change the PATH variable remember to reboot the system before running the build procedure, this is not strictly required but will ensure the PATH is updated). If the PATH variable does not contain the path of your python installation you will see a warning in the build log/output.
현재는 파이썬 3.6, 3.5, 2.7 버전을 지원하고 있습니다. 소스 버전 사용시에는 파이썬을 시스템에 설치하는 것을 추천합니다. 파이썬 공식 배포판은 사용자의 홈 디렉토리에 설치되며, 환경 변수 PATH 에 설치 경로를 추가해줍니다. (PATH 변수가 수정되고 나면 시스템을 리부팅하는 것을 추천하지만, 환경 변수 갱신 방법을 알고 계시다면 상관없습니다.) 만약 PATH 변수에 파이썬 설치 경로가 포함되어있지 않다면 빌드 로그/출력에 경고가 나오게 됩니다.

Download a source official release or simply clone the repository for latest updates:
공식 소스 릴리즈를 다운로드하거나 저장소를 클론해주세요.

```sh
git clone https://github.com/20tab/UnrealEnginePython
```

By default the build procedure will try to discover your python installation looking at hardcoded known paths. If you want to specify a custom python installation (or the autodetection simply fails) you can change it in the Source/UnrealEnginePython/UnrealEnginePython.Build.cs file at this line: https://github.com/20tab/UnrealEnginePython/blob/master/Source/UnrealEnginePython/UnrealEnginePython.Build.cs#L10
현재 구현된 빌드 절차에서는 하드코딩된 기존 파이썬 경로에서 파이썬 설치 경로를 찾습니다. 파이썬을 다른 곳에 설치하셨다면 플러그인 빌드 설정(UnrealEnginePython.Build.cs)를 수정하셔야 합니다.

Note: ensure you have a 64bit python installation
참고: 반드시 64비트 파이썬이 설치되어있어야 합니다.


choose a project you want to install the plugin into, open the file explorer (you can do it from the epic launcher too) and:
플러그인을 설치할 프로젝트를 골랐다면, 탐색기를 오픈합니다. (에픽 런처에서도 가능합니다.)

* create a Plugins/ directory (if it does not exist) in your project and copy the directory UnrealEnginePython into it
* 프로젝트에 Plugins/ 디렉토리를 생성한다음, UnrealEnginePython 을 복사해 넣습니다.
* from the file explorer right click on the project main file and choose 'generate visual studio project files'
* 탐색기에서 프로젝트 파일을 선택 후 우클릭 한다음 "Generate Visual Studio Project Files"를 선택합니다.
* open visual studio, you should now see Plugins/UnrealEnginePython in your solution explorer
* 비주얼 스튜디오를 연 다음 솔루션 탐색기에서 Plugins/UnrealEnginePython 을 확인합니다.
* run the compilation from visual studio
* 비주얼 스튜디오 컴파일을 시작합니다.
* once the compilation ends, double check the python libraries can be found by the plugin (they must be in the system PATH like previously described, or brutally copy them in the Binaries/Win64 directory of the just built plugin)
* 컴파일이 끝나면 플러그인에서 파이썬 라이브러리를 찾을 수 있는지 다시 한번 확인합니다. (환경 변수 PATH 에 정의되어 있거나 Binaries/Win64 디렉토리에 복사해놓으면 됩니다.)
* now you can re-run the unreal engine editor
* 언리얼 엔진 에디터를 재실행합니다.

If all goes well, you will see 'Python Console' in the "Window/Developer Tools" menu
성공했다면 "윈도우>개발자 도구" 메뉴에서 'Python Console' 이 보이실겁니다.

If you want to package your project (it is required only if you need to have a python VM at runtime, read: your game logic is programmed in python) ensure the Content/Scripts/ue_site.py file is in your project (it can be empty). At the end of the build procedure ensure to copy all of your required python scripts in the final directory. Remember that unless you add an embedded python in your final build, the final users of your project will require python installed in his/her system.
(게임 로직이 파이썬으로 코딩되어 있어서) 프로젝트 패키지 런타임에서도 사용하려면 프로젝트내 `Content/Scripts/ue_site.py` 파일이 필요합니다. 빌드 마지막 단계에 임베디드 파이썬을 추가해놓지 않으면 사용자 시스템에서 파이썬을 요구하게 된다는 점을 기억해두시기 바랍니다.

If you want to package without python, just remember to change the UnrealEnginePython.uplugin to have this line: https://github.com/20tab/UnrealEnginePython/blob/master/UnrealEnginePython.uplugin#L20 set as "Editor" instead of "Runtime"
파이썬 없이 패키징 하려면 플러그인 파일(UnrealEnginePython.uplugin)에서Runtime 을 Editor 로 변경해야 합니다.

## Binaries installation on MaxOSX (macOS 바이너리 인스톨)

Check in the releases page (https://github.com/20tab/UnrealEnginePython/releases) if there is a binary version that matches your configuration (otherwise open an issue asking us for it [please specify the python version too]) and download it.
릴리즈 페이지에서 원하는 바이너리 버전을 다운로드 받으시기 바랍니다. (적합한 바이너리가 없다면 파이썬 버전을 명시해 문의 부탁드립니다.)

Binary releases for MacOSX expects an official python installation (the packages you get from python.org).
macOS 용 바이너리 릴리즈는 (python.org 에서 받을 수 있는) 파이썬 공식 배포판을 기준으로 설명합니다.

Create (if it does not already exist) a Plugins directory in your project root directory (at the same level of Content/ and the .uproject file) and unzip the plugin into it. If your project is named FooBar you will end with FooBar/Plugins/UnrealEnginePython.
프로젝트 루트 디렉토리에 플러그인 디렉토리가 필요합니다. 플러그인 디렉토리가 없다면 프로젝트 파일(.uproject)나 Content 폴더와 같은 위치이에 Plugins 디렉토리를 만들면 됩니다. 프로젝트 이름이 FooBar 라면 FooBar/Plugins/UnrealEnginePython 라는 경로를 갖게 됩니다.


Open your project and go to the Edit/Plugins menu. Go to the bottom and under "Project/Scripting Languages" enable UnrealEnginePython.
프로젝트를 열고, 편집 > 플러그인 메뉴로 이동합니다. 플러그인 다이얼로그 하단에 "프로젝트 > Scripting Languages" 에서 UnrealEnginePython 을 활성화시켜주세요.

Restart your project and you should see the PythonConsole under the "Window/Developer Tools" menu
프로젝트를 재시작하면 "윈도우 > 개발자 도구" 메뉴에서 파이썬 콘솔을 찾으실 수 있을 겁니다.

Binary releases are mainly useful for editor scripting, if you want to package your project for distribution and you need the python runtime, you need a source release (see below).
바이너리 릴리즈는 주로 에디터 스크립팅을 하는데 유용합니다. 배포용 패키지에서 파이썬 런타임이 필요하다면 아래 나오는 소스 릴리즈를 사용하셔야 합니다.

If instead, you want to package your project without python, just remember to change the UnrealEnginePython.uplugin to have this line: https://github.com/20tab/UnrealEnginePython/blob/master/UnrealEnginePython.uplugin#L20 set as "Editor" instead of "Runtime"
대신 파이썬 없이 프로젝트를 패키지하려면 UnrealEnginePython.uplugin 에서 Runtime 대신 Editor 로 설정해주셔야 합니다.

## Installation from sources on MacOSX (macOS 소스 설치)

* install the latest official python distribution from python.org (the installation will end in the "/Library/Frameworks/Python.framework/Versions/X.Y" directory).
* python.org 에서 최신 공식 파이써 배포판을 설치 합니다. (설치 경로는 "/Library/Frameworks/Python.framework/Versions/X.Y" 디렉토리 형태 입니다.) 
* create a new unreal engine blank c++ project (NOT a blueprint one, otherwise XCode will not be initialized)
* 새로운 언리얼 엔진 C++ 프로젝트를 생성합니다. (블루프린트 프로젝트는 Xcode 를 초기화시키지 않으므로 사용할 수 없습니다. )
* create a Plugins directory in the project directory
* 프로젝트에 Plugins/ 디렉토리를 생성합니다.
* move to the Plugins directory and clone the plugin repository
* Plugins 디렉토리로 이동해 플러그인 저장소를 클론 합니다. 


```sh
git clone https://github.com/20tab/UnrealEnginePython
```

* restart the editor and a popup should appear asking your for confirmation of the build of the plugin.
* 에디터를 재실행하고 팝업되는 플러그인 빌드 확인 여부에 답변합니다.
* Once the plugin is built, go to the output log console and filter for 'Python'. You should see the Python VM banner.
* 플러그인 빌드가 끝나고 출력창 로그 콘솔 'Python` 필터로 이동하면 파이썬 VM 배너를 볼 수 있습니다.

The build procedure will try to automatically discover python installations. If you need custom paths, just edit here:

https://github.com/20tab/UnrealEnginePython/blob/master/Source/UnrealEnginePython/UnrealEnginePython.Build.cs#L10

Upgrading on MacOSX (macOS 플러그인 업그레이드)
-------------------

To upgrade to the latest development version of UnrealEnginePython:
언리얼 엔진 파이썬 최신 개발 버전으로 업그레이드 하는 방법

* move to the Plugins directory in the project directory and use git pull
* 프로젝트 내 Plugins 디렉토리로 이동해 git pull 을 사용 합니다.

```sh
git pull
```

* move to UnrealEnginePython/Binaries/Mac from the Plugin directory
* 플러그인 디렉토리내 UnrealEnginePython/Binaries/Mac 으로 이동합니다.

* remove the plugin libraries to warn UnrealEngine to recompile the plugin
* 언리얼 엔진이 플러그인을 재컴파일 하도록 플러그인 라이브러리를 삭제합니다.

```sh
rm *.dylib
```

* restart the editor and a popup should appear asking your for confirmation of the build of the plugin.
* 에디터를 재실행하고 팝업되는 플러그인 빌드 확인 여부에 답변합니다.
* Once the plugin is built, go to the output log console and filter for 'Python'. You should see the Python VM banner.
* 플러그인 빌드가 끝나고 출력창 로그 콘솔 'Python` 필터로 이동하면 파이썬 VM 배너를 볼 수 있습니다.

Installation from sources On Linux (64 bit)
-------------------------------------------

Currently the suggested distribution is Ubuntu Xenial (LTS 16.04) 64bit. Obviously you need to already have an Unreal Engine build (note that on ubuntu xenial you need to install the clang-3.5 package to build the editor). Both python2.7 and python3.5 are supported and the default configuration assumes python3 (so ensure to install the python3-dev package).

* Create a new C++ project and close the editor once the project is fully started
* go to the just created project directory and create the Plugins folder
* move to the Plugins folder and clone the plugin repository:


```sh
git clone https://github.com/20tab/UnrealEnginePython
```

* re-open your project, this time you will get a popup asking you for re-building the python plugin. Choose yes and wait.

NOTE: always run your project from a terminal so you can see startup logs (they are really useful when building the plugin the first time, if you cannot build the plugin, open an issue on github pasting the related log lines).

If you want to use python2 (or another specific version) just edit the Source/UnrealEnginePython/UnrealEnginePython.Build.cs file and change the pythonHome string accordingly (ensure to have the python2.7-dev package installed).


Upgrade the plugin on Linux
---------------------------

Just remove the .so files in Plugins/UnrealEnginePython/Binaries/Linux and pull the latest code.

At the next run the build procedure wil be started again.

Android Deployment (안드로이드 개발)
------------------

Check https://github.com/20tab/UnrealEnginePython/blob/master/docs/Android.md
안드로이드 문서를 참고 해주세요.

## Installation on other platforms (기타 플랫폼 설치)

Currently only Windows, MacOSX, Linux and Android are supported.
현재는 Windows, macOS, Linux, Android 만 지원합니다.

## Using Python with Unreal Engine (finally) 언리얼 엔진에서 파이썬 사용하기

If your objective is to script the editor, you can directly jump to
에디터 스크립팅이 목적일 경우 아래 문서들을 참고해주세요.

https://github.com/20tab/UnrealEnginePython/tree/master/docs

and

https://github.com/20tab/UnrealEnginePython/tree/master/examples

The first directory contains the official documentation for specific areas, while the second one is a collection of python scripts doing any sort of 'magic' with your project ;)
첫번째 디렉토리는 공식 문서이고, 두번째 디렉토리는 프로젝트에 유용한 파이썬 스크립트 모음입니다.

Creating a new blueprint class managed by python (파이썬으로 관리되는 블루프린트 만들기)
------------------------------------------------

We are going to create a new Actor based on python (instead of C++ or blueprints)
(C++ 이나 블루프린트 대신)파이썬 기반에 액터를 생성해 보도록 하겠습니다.

This is the "gentle" approach, using a 'proxy' python class to speak with the UE4 api. Once you get familiar with the system, you can
go further and start working withe native subclassing api (https://github.com/20tab/UnrealEnginePython/blob/master/docs/Subclassing_API.md) 
UE4 API 를 사용하기 위해 '프락시' 파이썬 클래스를 사용하는 "젠틀한" 방법입니다. 시스템에 대한 이해도가 높아지면  네이티브 서브 클래싱 API 를 사용하실 수 있게 될 것입니다.

In the content browser click on 'add new' and choose 'blueprint class'
컨텐츠 브라우저에서 'Add New'를 클릭한 다음 'Blueprint class'를 선택합니다.

In the classes menu choose 'PyActor':
클래스 리스트 메뉴에서 'PyActor'를 선택합니다.

![Alt text](screenshots/unreal_screenshot1.png?raw=true "Screenshot 1")

You now have a new asset, give it a meaningful name, and double click on it to start configuring it in the blueprint editor
새로운 애셋에 이름을 지어준 다음 더블 클릭해 블루프린트 에디터를 열어 설정을 시작합니다.

![Alt text](screenshots/unreal_screenshot2.png?raw=true "Screenshot 2")

On the right (in the 'Details' tab) you will find the Python section.
우측 ('디테일' 탭 내부)에서 파이썬 섹션을 찾을 수 있습니다.

For now only 'Python Module' and 'Python Class' are meaningful.
'Python Module' 과 'Python Class' 만 의미가 있습니다.

Go to the Content directory of your project and create a directory named 'Scripts'. This is where all of your python modules will reside. With your favourite text editor create a new python module (like funnygameclasses.py), and define a new class into it:
프로젝트 디렉토리로 이동해 'Scripts' 디렉토리를 생성합니다. 파이썬 모듈들을 모아 놓는 곳입니다. 선호하는 텍스트 에디터를 사용해 (funnygameclasses.py 같은) 파이썬 모듈을 하나 생성한 다음 아래처럼 작성합니다.

```py
import unreal_engine as ue

ue.log('Hello i am a Python module')

class Hero:

    # this is called on game start
    def begin_play(self):
        ue.log('Begin Play on Hero class')
        
    # this is called at every 'tick'    
    def tick(self, delta_time):
        # get current location
        location = self.uobject.get_actor_location()
        # increase Z honouring delta_time
        location.z += 100 * delta_time
        # set new location
        self.uobject.set_actor_location(location)

```

Now, go back to the blueprint editor and set 'funnygameclasses' in the 'Python Module' field, and 'Hero' in 'Python Class'
블루프린트 에디터로 돌아가서 'Python Module' 필드에 'funnygameclasses', 'Python Class' 필드에 'Hero'라고 설정합니다.

As you can see the actor will simply move over the z axis, but we need to give it some kind of visual representation to have a feedback in the scene. In the blueprint editor click on 'add component' and add some shape (a sphere, or a cube, or whatever you want). Save and Compile your blueprint.
방금 만든 파이썬 모듈은 z 축위로 이동하는 액터이지만 움직임을 확인하기 위해서는 시각적인 표현을 붙여줘야 합니다. 블루프린트 에디터에서 'Add Component'를 클릭해 (Sphere 나 Cube 등) 원하는 모양을 축해줍니다. 블루프린트를 컴파일하고 저장하니다.

Now you can drag the bluprint from the content browser to the scene and just click 'Play'.
컨텐츠 브라우저의 블루프린트를 씬에 드래그 한 다음 'Play' 버튼을 클릭합니다.

You should see your actor moving along the 'z' axis at a speed of 1 meter per second
초당 1초의 속도로 z축을 따라 이동하는 액터를 보실 수 있을겁니다.

By default a 'begin_play' and a 'tick' method are expected (they will be automatically taken into account if found). In addition to them an 'automagic' system for defining event is available:
디폹트로 `begin_play` 와 `tick` 메소드가 (파이썬 클래스내 작성되어 있다면 자동으로) 사용 됩니다. 추가적으로 'automagic' 시스템을 사용할 수 있습니다.

```py
def on_actor_begin_overlap(self, me, other_actor):
    pass

def on_actor_end_overlap(self, me, other_actor):
    pass
    
def on_actor_hit(self, me, other_actor, normal_impulse, hit_result):
    pass

...
```

Basically for each method startwing with `on_` the related delegate/event is automatically configured (if available).
기본적으로 `on_`으로 시작되는 메소드들은 (사용가능하다면) 자동으로 관련된 델리게이트나 이벤트로 설정됩니다.

If you instead prefer to manually setup events, the following functions are exposed:
이벤트들을 수동으로 설정하는 것을 선호한다면 아래 방식을 사용하시면 됩니다.

```py

class Ball:

    def begin_play(self):
        self.uobject.bind_event('OnActorBeginOverlap', self.manage_overlap)
        self.uobject.bind_action('Jump', ue.IE_PRESSED, self.uobject.jump)
        self.uobject.bind_key('K', ue.IE_PRESSED, self.you_pressed_K)
        self.uobject.bind_axis('MoveForward', self.move_forward)
        
    def manage_overlap(self, me, other):
        ue.print_string('overlapping ' + other.get_name())
        
    def you_pressed_K(self):
        ue.log_warning('you pressed K')
        
     def move_forward(self, amount):
        ue.print_string('axis value: ' + str(amount))
        

```


What is 'self.uobject' ? (self.uobject 란?)
------------------------

To allow seamless Python integration, each UObject of the engine is automatically mapped to a special Python Object (ue_PyUObject).
매끄러운 파이썬 통합을 위해 엔진내 UObject 들은 자동으로 특정 파이썬 오브젝트(`ue_PyUObject`)로 맵핑됩니다.

Whenever you want to access a UObject from python, you effectively get a reference to a ue_PyUObject exposing (via its methods) the features of the UObject (properties, functions, ....) 파이썬에서 UObject 접근시 (프로퍼티, 펑션 등) UObject 기능을 사용할 수 있는 `ue_PyUObject`레퍼런스를 얻을 수 있습니다.

This special python object is cached into a c++ map in memory. (The key is the UObject pointer, the value is the ue_PyUObject pointer)
이 특별한 파이썬 오브젝트는 메모리상 c++ map 으로 캐시되어 있습니다. (키는 UObject 포인터이고, 값은 `ue_PyUObject`포인터입니다.)

To be more clear, a call to:
좀 더 명확하게 설명하자면, 아래 같은 호출이 있을 경우

```py
text_render_component = unreal_engine.find_class('TextRenderComponent')
```

will internally search for the 'TextRenderComponent' class (via unreal c++ reflection) and when found will check if it is available in the cache, otherwise it will create a new ue_PyUObject object that will be placed in the cache.
내부적으로 'TextRenderComponent' 클래스를 (언리얼 c++ 리플렉션을 통해) 검색합니다. 해당 클래스를 찾아내면 캐시로 사용 가능한지 체크하고 아니면 새로운 `ue_PyUObject` 를 생성해 캐쉬에 넣습니다.

From the previous example the 'text_render_component' maintains a mapping to the UObject (well a UClass in this example).
위 예제에서 `text_render_component` 는 UObjectd 의 맵핑(여기에서는 UClass)를 관리하게 됩니다.

Pay attention: the python class you map to the PyActor (or PyPawn, PyCharacter or PyComponent), is not a ue_PyUObject. It is a classic python class that holds a reference (via the 'uobject' field) to the related ue_PyUObject mapped object. The best technical term to describe those classes is 'proxy'.
주의: PyActor (또는 PyPawn, PyCharacter 또는 PyComponent)에 매핑하는 파이썬 클래스는 `ue_PyUObject`가 아닙니다. 이것은 클래식 파이썬 클래스로 `ue_PyUObject` 매핑된 객체에 대한 참조를 ('uobject'필드를 통해) 보유하고 있습니다. 전문적인 용어로는 '프록시'라고 합니다.


Note about 'uobject' from now on (이후 등장하는 'uobject' 에 대한 참고 사항)
---------------------------------

In the following lines, whenever you find a reference to 'uobject' it is meant as a ue_PyUObject object.
이후 등장하는 'uobject' 는 `ue_PyUObject` 객체를 의미합니다.

Adding a python component to an Actor (액터에 파이썬 컴포넌트 추가하기)
-------------------------------------

This works in the same way as the PyActor class, but it is, well, a component. You can attach it (search for the 'Python' component) to any actor.
PyActor 클래스와 비슷합니다. 단지 컴포넌트라는 차이만 있을 뿐입니다. 어떤 액터라도 'Python' 컴포넌트를 검색해 붙일 수 있습니다.

Remember that for components, the self.uobject field point to the component itself, not the actor.
컴포넌트에서 self.uobject 는 액터가 아니라 컴포넌트 자체를 말합니다.

To access the actor you can use:
액터에 접근하는 방법입니다.

```py
actor = self.uobject.get_owner()
```

The following example implements the third person official blueprint as a python component:
다음 에제는 3 인칭 공식 블루프린트를 파이썬으로 구현한 것입니다.

```py
class Player:
    
    def begin_play(self):
        # get a reference to the owing pawn (a character) 자기 폰 (캐릭터)에 대한 레퍼런스 얻음
        self.pawn = self.uobject.get_owner()

        # the following two values were originally implemented as blueprint variable 아래 2가지 값은 원래 블루프린트 변수로 구현되었음
        self.base_turn_rate = 45.0
        self.base_look_up_rate = 45.0

        # bind axis events 축 이벤트 연동
        self.pawn.bind_axis('TurnRate', self.turn)
        self.pawn.bind_axis('LookUpRate', self.look_up)
        self.pawn.bind_axis('Turn', self.pawn.add_controller_yaw_input)
        self.pawn.bind_axis('LookUp', self.pawn.add_controller_pitch_input)

        self.pawn.bind_axis('MoveForward', self.move_forward)
        self.pawn.bind_axis('MoveRight', self.move_right)

        # bind actions 액션 연동
        self.pawn.bind_action('Jump', ue.IE_PRESSED, self.pawn.jump)
        self.pawn.bind_action('Jump', ue.IE_RELEASED, self.pawn.stop_jumping)

    def turn(self, axis_value):
        turn_rate = axis_value * self.base_turn_rate * self.uobject.get_world_delta_seconds()
        self.pawn.add_controller_yaw_input(turn_rate)

    def look_up(self, axis_value):
        look_up_rate = axis_value * self.base_look_up_rate * self.uobject.get_world_delta_seconds()
        self.pawn.add_controller_pitch_input(look_up_rate)

    def move_forward(self, axis_value):
        rot = self.pawn.get_control_rotation()
        fwd = ue.get_forward_vector(0, 0, rot[2])
        self.pawn.add_movement_input(fwd, axis_value)

    def move_right(self, axis_value):
        rot = self.pawn.get_control_rotation()
        right = ue.get_right_vector(0, 0, rot[2])
        self.pawn.add_movement_input(right, axis_value)
```

Native methods VS reflection 네이티브 메소드 vs 리플렉션
----------------------------

By default the UObject class defines __getattr__ and __setattr__ as wrappers for unreal properties and functions.
기본적으로 UObject 클래스는 언리얼 프로퍼티와 펑션을 `__getattr__` 과 `__setattr__` 로 랩핑 합니다. 

This means that calling:
이런 접근은

```py
self.uobject.bCanBeDamaged = True
```

it is the same as
아래와 동일합니다.

```py
self.uobject.set_property('bCanBeDamaged', True)
```

As well as function calls:
함수 호출은

```py
vec = self.uobject.GetActorRightForward()
```

means
아래처럼 처리됩니다.

```py
vec = self.uobject.call_function('GetActorRightForward')
```

And more important (and handy) `K2_` functions are automagically exposed too:
그리고 더 중요한 (그리고 편리한) `K2_` 함수는 자동으로 노출됩니다.

```py
vec = self.uobject.GetActorLocation()
```

is equal to:
위와 같은 호출은 아래와 동일합니다.

```py
vec = self.uobject.call_function('K2_GetActorLocation')
```

Obviously you can combine methods/properties:
당연히 메소드/속성은 결합해서 사용할 수 있습니다.

```py
self.uobject.CharacterMovement.MaxWalkSpeed = 600.0
```

Albeit the system allows for full unreal api usage, reflection is slower than native methods.
모든 언리얼 API 을 지원하는 시스템이긴 하지만, 리플렉션은 네이티브 메소드 호출보다는 느립니다.

Try to use native methods whenever possible, and open pull request whenever you think a function should be exposed as native methods.
가능하면 네이티브 메소드를 사용하는 것을 추천합니다. 네이티브 메소드로 노출시켜야 한다고 생각한다면 pull request 부탁드립니다.

So
즉,

```py
vec = self.uobject.get_actor_location()
```

is way faster than
위 방식은 아래 방식보다 빠릅니다.

```py
vec = self.uobject.GetActorLocation()
```

Reflection based functions are those in camelcase (or with the first capital letter). Native functions instead follow the python style, with lower case, underscore-as-separator function names.
르플레이션 기반 펑션들은 camelCase (혹은 PascalCase)를 사용니다. 네이티브 펑션들은 파이썬 스타일(`snake_case`)를 따릅니다.

Note that, in editor builds, when you change the property of an archetype (included ClassDefaultObject) via __setattr__ all of the archtype instances will be updated too.
참고로 에디터 빌드에서는 (ClassDefaultObject 를 포함한) archtype 프로퍼티를 변경하면 `__setattr__`을 통해 모든 archtype 인스턴스들이 업데이트 됩니다.

To be more clear:
좀 더 명확하게 표현하자면

```python
your_blueprint.GeneratedClass.get_cdo().CharacterMovement.MaxWalkSpeed = 600.0
```

is a super shortcut for:
위 구문은 아래 구문의 단축 형태입니다.

```python
your_blueprint.GeneratedClass.get_cdo().CharacterMovement.pre_edit_change('MaxWalkSpeed')
your_blueprint.GeneratedClass.get_cdo().CharacterMovement.set_property('MaxWalkSpeed', 600.0)
your_blueprint.GeneratedClass.get_cdo().CharacterMovement.post_edit_change_property('MaxWalkSpeed')
for instance in your_blueprint.GeneratedClass.get_cdo().CharacterMovement.get_archetype_instances():
    instance.pre_edit_change('MaxWalkSpeed')
    instance.set_property('MaxWalkSpeed', 600.0)
    instance.post_edit_change_property('MaxWalkSpeed')
```


The automagic UClass, UStruct and UEnums mappers 자동 마법 UClass, UStruct, UEnum 맵퍼들 
------------------------------------------------

Instead of doing a gazilion of unreal_engine.find_class(name) calls, the plugin adds three 'magic' modules called unreal_engine.classes, unreal_engine.structs and unreal_engine.enums. They allows to import unreal classes/structs/enums like python classes:
`unreal_engine.find_class(name)` 귀찮음 방지를 위해, 플러그인에서는 3 가지 '마법같은' 모듈들(`unreal_engine.classes`, `unreal_engine.structs`, `unreal_engine.enums`)을 준비했습니다. 이들은 언리얼 클래스/구조체/열거형을 파이썬으로 임포트해줍니다.

```py
from unreal_engine.classes import ActorComponent, ForceFeedbackEffect, KismetSystemLibrary

...
components = self.uobject.get_owner().GetComponentsByClass(ActorComponent)

...
self.force_feedback = ue.load_object(ForceFeedbackEffect, '/Game/vibrate')
self.uobject.get_player_controller().ClientPlayForceFeedback(self.force_feedback)

...
name = KismetSystemLibrary.GetObjectName(self.actor)
```

the last example, shows another magic feature: static classes function calls. Obviously in this specific case using self.actor.get_name() would have been the best approach, but this feature allows you to access your blueprint function libraries too.
마지막 예제에서는 또 다른 마법같은 기능: 정적 클래스 펑션 호출을 보여줍니다. 이러한 상황에서는 `self.actor.get_name()`을 사용하는 것이 가장 좋은 접근 방식이겠지만, 이 기능을 사용하면 블루프린트 라이브러리에 접근할 수 있습니다.

Another example for adding a widget:
위젯을 추가하는 또 다른 예제입니다.

```py
from unreal_engine.classes import WidgetBlueprintLibrary

class PythonFunnyActor:
    def begin_play(self):
        WidgetBlueprintLibrary.Create(self.uobject, ue.find_class('velocity_C'))
```

And another complex example using enums, keyword arguments and output values (output values are appended after the return value):
그리고 열거형과 키워드 인자, (리턴 값 뒤에 추가되는) 출력 값을 사용하는 예제입니다.

```py

import unreal_engine as ue
from unreal_engine import FVector, FRotator, FTransform, FHitResult
from unreal_engine.classes import ActorComponent, ForceFeedbackEffect, KismetSystemLibrary, WidgetBlueprintLibrary
from unreal_engine.enums import EInputEvent, ETraceTypeQuery, EDrawDebugTrace

...

is_hitting_something, hit_result = KismetSystemLibrary.LineTraceSingle_NEW(self.actor, self.actor.get_actor_location(), FVector(300, 300, 300), ETraceTypeQuery.TraceTypeQuery1, DrawDebugType=EDrawDebugTrace.ForOneFrame)
if is_hitting_something:
    ue.log(hit_result)
```

To create a new struct instance you can do:
새로운 구조체 인스턴스를 만드는 방법입니다.

```python
from unreal_engine.structs import TerrificStruct

ts = TerrificStruct()
```

or (to initialize some of its fields)
혹은 (몇가지 필드를 초기화 하는 예제입니다)

```python
from unreal_engine.structs import TerrificStruct

ts = TerrificStruct(Foo='Bar', Test=17.22)
```

To access the fields of a struct just call the fields() method.
`fields()` 메소드를 호출해서 구조체 필드에 접근할 수 있습니다.

A good example of struct usage is available here: https://github.com/20tab/UnrealEnginePython/blob/master/docs/Settings.md
구조체 활용 예제입니다.

More details here: https://github.com/20tab/UnrealEnginePython/blob/master/docs/MemoryManagement.md
자세한 내용은 여기서 볼 수 있습니다.

The ue_site.py file `ue_site.py` 파일
-------------------

On Editor/Engine start, the ue_site module is tried for import. You should place initialization code there. If the module cannot be imported, you will get a (harmful) message in the logs.
에디터나 엔진 시작시 `ue_site` 모듈을 임포트하게 됩니다. 여기에 초기화 코드들을 넣어두면 됩니다. 만약 해당 모듈을 임포트할 수 없으며 로그 창에 (에러) 메시지가 나오게 됩니다.

PyPawn 
------

This works like PyActor, but this time you generate a new Pawn class (that you can posses with a controller)
PyActor 비슷하지만 새로운 Pawn 클래스를 생성합니다. (컨트롤러를 통해 제어할 수 있습니다.)


The 'World' concept '월드' 컨셉
-------------------

Every actor is mapped to a world (UWorld in c++). Generally when you play on a Level your objects all live in the same world, but at the same time there could be multiple worlds (for example while testing in the editor there is a world for the editor and one for the simulation)
모든 액터는 월드(C++ 에서 이야기하는 UWorld)에 맵핑됩니다. 일반적으로 레벨을 플레이할 때 오브젝트들은 같은 월드상 존재합니다. 동시에 여러 세계가 존재할 수도 있습니다. (예를 들어 에디터를 테스트하는 동안 에디터용 월드와 시뮬레이션용 월드가 존재하게 됩니다.)

While it is pretty rare to reference other worlds, you may need to compare the world of two uobject's (for example you may have a reference in your python module to a uobject of a hidden world and you want to check if you need to use it).
다른 월드를 참조하는 일은 극히 드문일이긴 하지만, 간혹 다른 월드에 있는 오브젝트를 비교해야할 경우가 있습ㄴ다. (에를 들어 파이썬 모듈에서 숨겨진 월드에 있는 객체를 참조해 사용 가능한지 체크해야할 수 있습니다.)

The uobject.get_world() function returns a uobject representing the world (the C++ UWorld class)
`uobject.get_world()` 펑션은 오브젝트가 존재하는 월드(C++ 의 UWorld 클래스)를 리턴해줍니다.

The uobject api
---------------

Each uobject represent a UObject class of the Engine. This C++ class is basically the root of all the other classes (Actors, Pawns, components, properties ...). Thanks to Unreal Engine reflection system we do not need to implement a python class for each unreal engine class, but for performance reason we expose the most common methods. The uobject system checks for the type of the mapped C++ UObject and will call the method only if it is safe to call it.
각 오브젝트는 엔진의 UObject 클래스를 나타냅니다. 기본적으로 이 C++ 클래스는 다른 모든 클래스의 부모 클래스입니다. (액터, 폰, 컴포넌트, 프로퍼티, ...) 언리얼 엔진의 리플렉션 시스템 덕분에 각 언리얼 클래스들을 파이썬으로 구현할 필요는 없습니다. 하지만 성능상의 이유로 자주 사용되는 메소드들은 직접 노출시켜야 합니다. uobject 시스템은 맵핑된 C++ UObject 의 타입을 체크해 안전하게 호출이 가능한 경우만 해당 메소드를 호출합니다.

Sometime methods are implemented for automatically getting the right object. As an example get_actor_location() when called over a component will automatically retrieve the related actor and will call C++ AActor::GetActorLocation() method over it.
때때로 정확한 오브젝트를 자동으로 얻어내기 위해 구현된 메소드들이 있습니다. 예를 들어 `get_actor_location()`은 컴포넌트상 호출될 때 자동으로 관련된 액터를 찾은 다음 C++ `AActor::GetActorLocation()` 메소드를 호출해줍니다.
When this automagic approach is too risky, the method will check for the uobject type and will raise an exception in the case of inconsistencies.
이런 자동화된 마법 접근 방식은 위험하다고 판단될 때 uobject 의 타입을 체크해 일치하지않을 경우 예외를 발생시키게 됩니다.

Remember, there is no need to implement every single engine class method, the reflection system is powerful enough to be governed only via properties and function calls (check the uobject call() method)
모든 엔진 클래스 메소드를 구현할 필요는 없습니다. 리플렉션 시스템은 프로퍼티와 펑션 호출을 통해서만 제어할 수 있을 정도로 매우 강력합니다. (uobject call() 메소드를 확인해보세요)

Most-used methods are implemented directly as uobject methods for performance reasons.
가장 빈번하게 사용되는 메소드는 성능상의 이슈로 uobject 메소드로 직접 구현되었습니다.

You can get the the list of uobject api methods here: https://github.com/20tab/UnrealEnginePython/blob/master/docs/uobject_API.md
uobject API 메서드 목록은 다음 링크에서 찾아보실 수 있습니다.

Automatic module reloading (Editor only) 자동 모듈 리로딩 (에디터 전용)
----------------------------------------

When in the editor, you can change the code of your modules mapped to proxies without restarting the project. The editor will reload the module every time a PyActor, PyPawn or PythonComponent is instantiated. This is obviously not the best approach. In the future we would like to implement timestamp monitoring on the file to reload only when needed.
에디터에서는 프로젝트 재시작없이도 프락시에 맵핑된 모듈 코드들을 수정할 수 있습니다. 에디터에서는 PyActor, PyPawn, PythonComponet 가 인스턴스될 때마다 모듈을 재로드합니다. 이것이 매우 좋은 방법은 아니기 때문에 추후에 필요할 때만 리로드하기 위해 타임 스탬프를 통한 모니터링을 구현하려고 합니다.

Primitives and Math functions 프리미티브와 수학 펑션들
-----------------------------

The plugin exposes FVector, FRotator, FQuat, FColor, FHitResult and a bunch of the internal handles.
플러그인에서는 FVector, FRotator, FQuat, FColor, FHitResult 및 내부 핸들들을 제공합니다.

Where meaningful, math operations are exposed:
수학 처리 예제입니다


```py
import unreal_engine

class ActorGoingUp:
    def begin_play(self):
        # 1 meter by second
        self.speed = 100
    
    def tick(self, delta_time):
        # get the up vector 업 벡터 얻기
        up = self.uobject.get_up_vector()
        # get current position 현재 위치 얻기
        position = self.uobject.get_actor_location()
        # build a direction vector based on speed 속력 기반 방향 벡터 준비
        up_amount = up * self.speed * delta_time)
        # sum the direction to the position 위치에 방향 합산
        position += up_amount
        # set the new position 새로운 위치 설정
        self.uobject.set_actor_location(new_position)
```

Referencing objects 오브젝트 참조
-------------------

You can use find_class(), find_struct() and find_object() functions to reference already loaded classes/objects.
`find_class(), find_struct(), find_object()` 펑션들을 사용해 이미 로드된 클래스나 오브젝트들을 레퍼런스 할 수 있습니다.

If you need to reference assets (still) not loaded in the engine you can use load_struct(), load_class() or load_object():
엔진에 아직 로드되지 않은 애셋이라면 `load_class(), load_struct(), load_object()`을 통해 로드해서 레퍼런스 할 수 있습니다.


```py
a_struct_data = ue.load_struct('/Game/Data')
ue.log(a_struct_data.as_dict())
```

or to find a specific asset:
특정 애셋을 찾아 볼 수도 있습니다.

```py
texture_class = ue.find_class('Texture2D')
a_specific_texture = ue.load_object(texture_class, '/Game/Textures/logo2')
```

More infos about dealing with assets are available here: https://github.com/20tab/UnrealEnginePython/blob/master/docs/ManagingAssets.md
애셋을 다루는 자세한 정보는 다음 링크에서 확인할 수 있습니다.

The as_dict() method `as_dict()` 메소드
--------------------

This special method can be called on any uobject: it will attempt to serialize it to a python dictionary
`as_dict()`는 어떤 오브젝트에서든 호출할 수 있는 특이한 메소드로 파이썬 사전 형태로 시리얼라이즈할 수 있습니다.


Blueprints integration 블루프린트 통합
----------------------

You can call blueprints functions (or custom events) via the .call() and .call_function() methods:
`.call()` 이나 `.call_function()`메소드를 통해 블루프린트 펑션(이나 커스텀 이벤트)를 호출 할 수 있습니다.

```py
your_funny_blueprint_object.call('AFunctionOrACustomEvent with_a_arg')
```

Whenever you need to reference external object, avoid using find_object() and similar. Instead add a public variable in your blueprint
pointing to the specific object. You can then reference this object easily getting the property value
외부 객체를 레퍼런할스 할때마다 `find_object()`류를 사용하는 것은 피하는 것이 좋습니다. 대신 특정 오브젝트를 가리키는 퍼블릭 변수를 프린트에 추가해두면
프로퍼티 값을 통해 오브젝트를 쉽게 레퍼런스할 수 있습니다.

```py
the_other_object = self.uobject.get_property('target')
the_other_object.set_actor_location(0, 0, 0)
```

.call_function() is more advanced, as it allows for return values and python args:
`.call_function()`은 리턴값과 파이썬 인자를 지원하므로 좀 더 쓸만합니다.

```py
## an example of moving an object z with curves: 곡선 형태로 오브젝트 z 를 움직이는 예제
class Curver:
    def begin_play(self):
        self.curve = self.uobject.get_owner().get_property('curve')
        self.accumulator = 0.0
    def tick(self, delta_time):
        location = self.uobject.get_actor_location()
        z = self.curve.call_function('GetFloatValue', self.accumulator) * 100
        self.uobject.set_actor_location(location.x, location.y, z)
        self.accumulator += delta_time

```

Events 이벤트
------

You can easily bind events (as seen before) with the bind_event function
`bind_event()` 펑션을 사용하면 (에전에 보았듯이) 이벤트를 손쉽게 바인딩할 수 있습니다.

```py
self.uobject.bind_event('OnActorBeginOverlap', a_funny_callback)
```

You can obviously bind to Event Dispatchers too.
이벤트 디스패처도 당연히 바인딩할 수 있습니다.

Triggering events is basically like calling functions, self.uobject.call('OnActorBeginOverlap') will be more than enough.
이벤트 트리거는 기본적으로 펑션처럼 호출됩니다. `self.uobject.call('OnActorBeginOverlap')`같은 형태입니다.

If you want to map events from a blueprint to a python function, the best thing to do is using the 'python call' blueprint functions exposed by the various plugin classes:
블루프린트에서 파이썬 펑션으로 이벤트를 맵핑하는 가장 좋은 방법은 '파이썬 호출' 블루프린트 함수를 사용하는 것입니다. 다양한 플러그인 클래스들을 노출시킬 수 있습니다.

![Alt text](screenshots/unreal_screenshot3.png?raw=true "Screenshot 3")

Plugin Configuration 플러그인 설정
--------------------

You can tune your python environment adding a [Python] stanza to the Config/DefaultEngine.ini file.
`Config/DefaultEngine.ini` 파일 [Python] 스탠자를 추가해 파이썬 환경을 조정할 수 있습니다.

The following parameters are supported:
지원되는 파라미터는 다음과 같습니다.

* `Home`: set the path of the python installation, useful for forcing the python vm to search modules in a specific directory (like old-style virtualenvs)
* `Home`: 파이썬 설치 경로로 특정 디렉토리내 모듈을 검색하도록 파이썬 VM 을 강제하는데 유용합니다. (구 virtualenvs 방식과 비슷합니다.)
* `RelativeHome`: like Home but relative to the /Content directory
* `RelativeHome`: Home 과 비슷하지만 /Content 디렉토리 기준 상대 경로입니다.
* `ProgramName`: set the python program name path
* `ProgramName`: 파이썬 프로그램 이름 경로 설정
* `RelativeProgramName`: like ProgramName, but the path is relative to the /Content directory
* `RelativeProgramName`: ProgramName 과 비슷하지만 /Content 디렉토리 기준 상대 경로입니다.
* `ScriptsPath`: change the default path on where Unreal Engine searches for python scripts
* `ScriptsPath`: 언리얼 엔진이 파이썬 스크립트를 검색하는 디폴트 경로 변경시 사용 
* `RelativeScriptsPath`: like ScriptsPath, but relative to the /Content directory
* `RelativeScriptsPath`: ScriptsPath 과 비슷하지만 /Content 디렉토리 기준 상대 경로입니다.
* `AdditionalModulesPath`: add the specified directory to sys.path
* `AdditionalModulesPath`: sys.path 에 특정 디렉토리 추가 
* `RelativeAdditionalModulesPath`: like AdditionalModulesPath, but the path is relative to the /Content directory
* `RelativeAdditionalModulesPath`: AdditionalModulesPath 와 비슷하지만 /Content 디렉토리 기준 상대 경로입니다.
* `ZipPath`: allow to specify a .zip file that is added to sys.path
* `ZipPath`: sys.path 에 특정 zip 파일 추가
* `RelativeZipPath`: like ZipPath, but the path is relative to the /Content directory
* `RelativeZipPath`: ZipPath 와 비슷하지만 /Content 디렉토리 기준 상대 경로입니다.
* `ImportModules: comma/space/semicolon separated list of modules to import on startup (after ue_site)
* `ImportModules: 시작시 (`ue_site` 이후) 임포트하는 모듈 리스트로 콤마, 스페이스, 세미콜론으로 구분

Example:
예제:

```ini
[Python]
Home = C:/FooBar/Python36
```

Packaging 패키징
---------

When you package your projects, remember to include the libpython (dll or dylib or .so based on your operating system) in the binaries folder and the Scripts directory (if you do not want to force the user to have python installed in its system). For Windows system you can use the embedded distributions available in the official python.org site. Just uncompress the zip in the plugin binary folder (at the same level of UnrealEnginePython.dll)
프로젝트 패키징시에는 (사용자 시스템에 파이썬 설치를 강요하는 걸 원치 않는다면) libpython (운영체제에 따라 .dll, .dylib, .so 등)이 포함된 바이너리 폴더와 스크립트 디렉토리를 포함시켜야 합니다. 윈도우 시스템의 경우 공식 python.org 사이트에서 제공되는 임베디드 배포판을 사용할 수 있습니다. (UnrealEnginePython.dll 과 같은 위치인) 플러그인 바이너리 폴더에 zip 압축을 풀어주면 됩니다.

If you do not want to distribute python sources, you can include only the ```__pycache__``` directory with the bytecode.
파이썬 소스 배포를 원하지 않는다면 바이트 코드가 있는 ```__pycache__``` 디렉토리만 포함시켜도 됩니다.

Do not forget to include python third party modules (if you use any of them in your project)
(프로젝트에서 사용중인) 파이썬 써드 파티 모듈을 포함해야 한다는 점 잊지 마시길 바랍니다. 

Quick Examples 쾌속 예제
--------------

This is a PyActor destroying itself whenever another actor overlap it. Remember to add a mesh component to it (like a sphere) and set its collision behaviour as 'OverlapAll'. This could be tested with the third person official template. 다른 액터에 겹칠때마다 스스로 파괴되는 PyActor 입니다. (구형 같은) 메쉬 컴포넌트를 추가하고 Collision Behaviour 를 'OverlapAll' 로 설정해야 한다는 점 기억해두시기 바랍니다. 공식 3 인칭 템플릿으로 테스트해 볼 수 있습니다.

```py
class Ball:
    def begin_play(self):
        ue.print_string('Hello')

    def on_actor_begin_overlap(self, other_actor):
        ue.print_string('Collided with ' + other_actor.get_name())
        self.uobject.actor_destroy()
```

Now we create (at runtime !!!) a whole new PyActor:
자 (런타임에!!!) PyActor 를 완전히 새롭게 작성해보겠습니다.

```python
class SuperHero:
    def begin_play(self):
        # spawn a new PyActor 새로운 PyActor 스폰
        new_actor = self.uobject.actor_spawn(ue.find_class('PyActor'), Fvector(0, 0, 0),FRotator(0, 0, 90))
        # add a sphere component as the root one 루트에 구형 컴포넌트 추가
        static_mesh = new_actor.add_actor_root_component(ue.find_class('StaticMeshComponent'), 'SphereMesh')
        # set the mesh as the Sphere asset 구형 애셋 메쉬 설정
        static_mesh.call('SetStaticMesh /Engine/EngineMeshes/Sphere.Sphere')
        # set the python module 파이썬 모듈 설정
        new_actor.set_property('PythonModule', 'gameclasses')
        # set the python class 파이썬 클래스 설정
        new_actor.set_property('PythonClass', 'Vertical')
```

For more examples: https://github.com/20tab/UnrealEnginePython/tree/master/examples
추가 예제는 다음 링크에서 보실 수 있습니다.

Spawning Notes 노트 스폰
--------------

Remember that only Actors can be spawned in a world, and that even the editor is a valid world:
월드에는 오직 액터만 스폰될 수 있습니다. 에디터도 월드입니다.

```python
import unreal_engine as ue
from unreal_engine.classes import Actor, Character
from unreal_engine import FVector, FRotator

world = ue.get_editor_world()
actor000 = world.actor_spawn(Actor, FVector(0, 0, 0), FRotator(0, 0, 0))
character000 = world.actor_spawn(Character, FVector(100, 100, 100), FRotator(0, 0, 0))
```

Remember that the Blueprint asset is not a valid actor by itself, you need to get the class generated by the blueprint:
블루프린트 애셋 자체는 액터가 아니므로, 블루프린트로 생성된 클래스가 필요합니다.

```python
import unreal_engine as ue
from unreal_engine.classes import Blueprint
from unreal_engine import FVector, FRotator

world = ue.get_editor_world()

blueprint = ue.load_object(Blueprint, '/Game/TestBall.TestBall')
actor000 = world.actor_spawn(blueprint.GeneratedClass, FVector(0, 0, 0), FRotator(0, 0, 0))
```

otherwise you can directly reference the BlueprintGeneratedClass
BlueprintGeneratedClass 레퍼런스를 직접 참조할 수도 있습니다.

```python
import unreal_engine as ue
from unreal_engine.classes import BlueprintGeneratedClass
from unreal_engine import FVector, FRotator

world = ue.get_editor_world()

blueprint_actor = ue.load_object(BlueprintGeneratedClass, '/Game/TestBall.TestBall_C')
actor000 = world.actor_spawn(blueprint_actor, FVector(0, 0, 0), FRotator(0, 0, 0))
```

The Python Editor 파이썬 에디터
-----------------

Starting from version 20170301 a handy editor has been added to the plugin:
20170301 버전부터 플러그인에 간단한 에디터가 추가되었습니다.

![Alt text](screenshots/python_editor_screenshot001.png?raw=true "Python Editor Screenshot")

It allows you to run, create, modify and delete scripts directly from the UE editor
언리얼 에디터에서 스크립트 실행, 생성, 수정, 삭제등을 할 수 있습니다.

The first pull request for the editor has been issued by https://github.com/sun5471 so many thanks to him ;)
에디터에 첫 풀 리퀘스트는 sun5471 님이 많은 도움을 주셨습니다.

Integration with Qt4/Qt5/PySide2
--------------------------------

Thanks to solid GIL management, you can integrate Qt python apps in Unreal Engine 4.

Pay attention to not call app.exec_() as it will result in Qt taking control of the UE loop. Instead use a ticker to integrate the Qt loop in the editor loop:

```python

## save it as ueqt.py
import sys
import unreal_engine as ue
import PySide2
from PySide2 import QtWidgets

app = QtWidgets.QApplication(sys.argv)

def ticker_loop(delta_time):
    app.processEvents()
    return True

ticker = ue.add_ticker(ticker_loop)
```
now you can start writing your gui (this is a simple example loading asset thumbnail):

```python
import ueqt
from PySide2 import QtCore, QtWidgets, QtGui
import unreal_engine as ue

from unreal_engine import FARFilter

_filter = FARFilter()
_filter.class_names = ['SkeletalMesh', 'Material']

class MyWidget(QtWidgets.QWidget):
    def __init__(self):
        super().__init__()
        self.vertical = QtWidgets.QVBoxLayout()
        self.scroll = QtWidgets.QScrollArea()
        self.content = QtWidgets.QWidget()
        self.scroll.setWidget(self.content)
        self.scroll.setWidgetResizable(True)
        self.layout = QtWidgets.QVBoxLayout()
	
        for asset_data in ue.get_assets_by_filter(_filter, True):
            try:
                thumbnail = asset_data.get_thumbnail()
            except:
                continue

            label = QtWidgets.QLabel()
            data = thumbnail.get_uncompressed_image_data()
            image = QtGui.QImage(data, 256, 256, QtGui.QImage.Format_RGB32)
            label.setPixmap(QtGui.QPixmap.fromImage(image).scaled(256, 256))
            self.layout.addWidget(label)

        self.content.setLayout(self.layout)
        self.vertical.addWidget(self.scroll)
        self.setLayout(self.vertical)



widget = MyWidget()
widget.resize(800, 600)
widget.show()

root_window = ue.get_editor_window()
root_window.set_as_owner(widget.winId())
```

(no need to allocate a new Qt app, or start it, as the UE4 Editor, thanks to to ueqt module is now the Qt app itself)

Note the 2 final lines: they 'attach' the Qt window as a 'child' of the editor root window. Note that on windows platform this is not simple parenting but 'ownership'.

Memory management
-----------------

Dealing with 2 different GC's is really challenging.

Starting from release 20180226 a new memory management system has been added (FUnrealEnginePythonHouseKeeper, available here https://github.com/20tab/UnrealEnginePython/blob/master/Source/UnrealEnginePython/Public/PythonHouseKeeper.h). This new system is completely integrated with the Unreal Engine reflection-based GC and will hold track of each ue_PyUObject abd the related UObject to understand when a python object can be safely destroyed.

The same system works for delegates, as well as Slate.

More details here: https://github.com/20tab/UnrealEnginePython/blob/master/docs/MemoryManagement.md

Unit Testing
------------

The repository includes the tests/ directory from which unit tests will be run.

To run the unit tests (ensure to run them on an empty/useless project to avoid messing with assets) run the following commands from the ue4 python console:

```python
import unreal_engine as ue
ue.py_exec(ue.find_plugin('UnrealEnginePython').get_base_dir() + '/run_tests.py')
```
if you plan to add new features to the plugin, including a test suite in your pull request will be really appreciated ;)

Threading
------------------------

Since release 20180624 threading is fully supported.

As with native threads, do not modify (included deletion) UObjects from non-main threads.

Accessing Python Proxy From UObject
-----------------------------------

Sometimes you may have a UObject and know that it is backed by a python object. To get the python object from the UObject, use the `get_py_proxy` method. For example, imagine you have the following situation:

   1. There is a `PyActor` sub-class called `PyExplosiveActor` which has `Explosive` as its python class.
   2. The `Explosive` has a `go_boom` python method.
   3. There is a `PyActor` sub-class called `PyBadGuyActor` which has a Blueprint property called `MyBomb` and a python class called `BadGuy`.
   4. The `BadGuy` instance in python knows that its UObject has its `MyBomb` as an instance of `PyExplosiveActor` and wants to call the `go_boom` python method.
   
This would be resolved as shown below:

```python
import unreal_engine as ue

class Explosive:
    'Python representation for PyExplosiveActor in UE4'

    def go_boom(self):
        # do python stuff to explode
        ...
        self.uobject.destory()

class BadGuy:
    'Python reprsentation for PyBadGuyActor in UE4'
   
    def ignite_bomb(self, delay):
        bomb = self.uobject.MyBomb
        py_bomb = bomb.get_py_proxy()
        py_bomb.go_boom()
	
```

What is going on here in `BadGuy` is that self.uobject is a reference to the PyActor UObject and `self.uobject.MyBomb` is a reference to the `PyExplosive` uobject. But instead you want to access its proxy class (`Explosive`). The `get_py_proxy()` method returns the python custom class, `Explosive` that the `PyExplosiveActor` object is mapped to.

Status and Known issues
-----------------------

Exposing the full ue4 api is a huge amount of work, feel free to make pull requests for your specific needs.

We still do not have a plugin icon ;)

We try to do our best to "protect" the user, but you can effectively crash UE from python as you are effectively calling the C/C++ api

Contacts and Commercial Support
-------------------------------

If you need commercial support for UnrealEnginePython just drop a mail to info at 20tab.com

Follow @unbit on twitter for news about the project

Special Thanks
--------------

Such a big project requires constant sponsorship, special thanks go to:

* Kite & Lighting http://kiteandlightning.la/ (they are sponsoring various areas of the project, expecially the slate api)

* GoodTH.INC https://www.goodthinc.com/ (they are sponsoring the sequencer api)

* Quixel AB https://megascans.se/ (built their integration tool over UnrealEnginePython giving us tons of useful feedbacks and ideas)
