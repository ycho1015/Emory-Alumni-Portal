개발환경 구축 가이드
================

필요 설치 항목 
------------
* `Ubuntu 16.10` 
    * 맥 사용자는 설치 필요 없음.
    * 윈도우 사용자는 VM을 이용한 설치보다는 듀얼 부팅을 권장함. 
* `PIP`
    * "Python Package Index", 파이썬으로 작성된 패키지 소프트웨어를 설치 및 관리하는 시스템.
* `Pyenv`
    * "Simple Python Version Management", 로컬에 다양한 파이썬 버전을 설치하고 사용할 수 있도록 한다. `Pyenv`를 사용함으로써 파이썬 버전에 대한 의존성을 해결할 수 있다.
* `Virtualenv`
    * "Virtual Python Environment Builder", 로컬에 다양한 파이썬 환경을 구축하고 사용할 수 있도록 한다. 일반적으로 `Python Packages` 라고 부르는 (`pip install`을 통해서 설치하는) 패키지들에 대한 의존성을 해결할 수 있다.
* `Django`
    * 파이썬으로 만들어진 무료 오픈소스 웹 어플리케이션 프레임워크. 쉽고 빠르게 웹사이트를 개발할 수 있도록 돕는 구성요소로 이루어진 웹 프레임워크.
* `PyCharm`
    * Emory Email을 이용해서 JetBrain에 가입을 하면, 1년동안 JetBrain의 모든 유료 제품을 무료로 사용 가능 
        * `회원가입 <https://www.jetbrains.com/student/>`__
        * `다운로드 <https://www.jetbrains.com/pycharm-edu/download/#section=linux-version>`__
        
        
Mac 최초 설정
~~~~~~~~~~~~~
**Homebrew 설치**

.. code :: bash

  /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"


Ubuntu 최초 설정
~~~~~~~~~~~~~
우분투 설치가 완료되면, Terminal 실행 후,

업데이트

.. code:: bash

  sudo apt-get update && sudo apt-get -y upgrade

PIP 설치

.. code:: bash

  sudo apt-get install python-pip

Vim(text editor) 설치

.. code:: bash
  
  sudo apt-get install vim
  
Pyenv Installation `추가정보 <https://github.com/yyuu/pyenv-installer>`__
~~~~~~~~~~~~~

**Mac:**

  .. code:: bash

      brew install pyenv
      brew install pyenv-virtualenv

  설치 후 shell 설정으로 이동:  

  .. code:: bash

      vim ~/.bash_profile
      
  shell 파일 최 하단에, 아래 적혀있는 코드 3줄을 입력 후 저장 밎 종료
     1. shell 파일로 terminal 창이 이동되면, ``i`` 키 입력
     2. 아래 적혀있는 코드 3줄을 복사 후, 붙혀넣기
     3. ``esc`` + ``:`` + ``w`` + ``q``키를 순서대로 입력하면 저장 및 종료  

  .. code:: bash

      export PYENV_ROOT=/usr/local/var/pyenv
      if which pyenv > /dev/null; then eval "$(pyenv init -)"; fi
      if which pyenv-virtualenv-init > /dev/null; then eval "$(pyenv virtualenv-init -)"; fi

  위 단계를 모두 끝마치면 터미널을 재시작하거나,

  .. code:: bash

      source ~/.bash_profile

**Linux:**

  .. code:: bash

      curl -L https://raw.githubusercontent.com/yyuu/pyenv-installer/master/bin/pyenv-installer | bash

  설치 후 shell 설정으로 이동:    

  .. code:: bash 

      vim ~/.bashrc

  shell 파일 최하단에 아래 적혀있는 코드 3줄을 입력 후 저장 밎 종료
     1. shell 파일로 terminal 창이 이동되면, ``i`` 키 입력
     2. 아래 적혀있는 코드 3줄을 복사 후, 붙혀넣기
     3. ``esc`` + ``:`` + ``w`` + ``q``키를 순서대로 입력하면 저장 및 종료  
  

  .. code:: bash

      export PATH="~/.pyenv/bin:$PATH"
      eval "$(pyenv init -)"
      eval "$(pyenv virtualenv-init -)"

  위 단계를 모두 끝마치면 터미널을 재시작하거나,

  .. code:: bash

      source ~/.bashrc 


Python 설치 전 필요 패키지
~~~~~~~~~~~~~
**Mac**

.. code:: bash

  brew install readline xz

**Ubuntu**

.. code:: bash

  sudo apt-get install -y make build-essential libssl-dev zlib1g-dev libbz2-dev \
  libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev libncursesw5-dev xz-utils

마무리
~~~~~~~~~~~~~
**Pyenv를 사용해서 Python 3.6.0버전 설치**

.. code:: bash
  
  pyenv install 3.6.0

**Virtualenv 설치**

.. code:: bash

  pip install virtualenv

**가상환경 생성**

.. code:: bash

  pyenv virtualenv <version><env name>
  pyenv virtualenv <3.6.0><tutorial>        # Like this! 
  
**사용할 폴더로 이동**

.. code:: bash

  cd projects/django/tutorial

**local에 가상환경 지정** (현재 directory는 projects/django/tutorial)

.. code:: bash

  pyenv local 3.6.0 tutorial

**django 설치** (여기도 현재 directory는 projects/django/tutorial)

.. code:: bash

  pip install django
  
 
