#   에라 유형 
 ## 에러내용
 Configuration file: C:/Users/user/Desktop/최태호/devgit/blangs.github.io/_config.yml Dependency Error: Yikes! It looks like you don't have tzinfo or one of its dependencies installed. In order to use Jekyll as currently configured, you'll need to install this gem. If you've run Jekyll with `bundle exec`, ensure that you have included the tzinfo gem in your Gemfile as well. The full error message from Ruby is: 'cannot load such file -- tzinfo' If you run into trouble, you can find helpful resources at https://jekyllrb.com/help/!
 jekyll 4.2.2 | Error:  tzinfo
## 해결방법 
# [깃페이지 루트]/Gemfile 아래 내용 추가
 gem 'tzinfo'
 gem "tzinfo-data", platforms: [:mingw, :mswin, :x64_mingw, :jruby] 

 깃블로그(4) Jekyll 테마 로컬 사용법
 1 minute read
 On this page
루비(Ruby) 개요
루비(Ruby) 설치
로컬서버에서 지킬 테마 실행하기
로컬서버 실행시 Error 유형
유형1
유형2
루비(Ruby) 개요Permalink
: Jekyll 은 Ruby 기반의 심플하고 블로그 지향적인 정적 사이트 생성기 컴파일러 이다. 루비 기반의 Jekyll 은 GitHub Pages 의 내부 엔진 으로 있기때문에, Jekyll 페이지/블로그/웹사이트를 GitHub 서버에 무료로 호스팅이 가능하다. 하지만 로컬에서 실행하기 위해서는 루비가 별도로 설치되어있어야 한다.

루비(Ruby) 설치Permalink
: 본격적으로 루비를 설치한다.

루비 공식홈페이지 이동 https://rubyinstaller.org/
Download > WITH DEVKIT 항목에서 원하는 버전 선택
(작성기준) Ruby+Devkit 3.1.2-1 (x64) 를 다운로드
(작성기준) 디폴트 설치 경로에 설치
각각의 대화상자에서 체크박스 모두 선택 후 Next.. Next..
설치완료
# 설치 확인
ruby -v 
ruby 3.1.2p20 (2022-04-12 revision 4491bb740a) [x64-mingw-ucrt]

로컬서버에서 지킬 테마 실행하기Permalink
: 루비기반의 지킬로 만들어진 minimal-mistakes 테마를 로컬에서 실행하자.

테마 다운로드 https://github.com/mmistakes/minimal-mistakes

다운받은 테마를 나의 로컬저장소에 압축풀기

 1. minimal-mistakes 테마 파일을 압축해제한다.
 2. 깃페이지로 구성된 로컬레파지토리 (나의깃허브아이디.github.com 일것이다.) 디렉토리에 모두 붙여넣는다.
 ex) C:\Users\user\Desktop\admin\devgit\blangs.github.io 

jekyll Ruby Gem 설치
아까 위에서 Ruby를 설치했다면, 이제 Ruby를 사용하여 jekyll Gem을 설치한다.
 # jekyll Gem을 설치  
 gem install bundler

jekyll 테마와 관련된 bundle 설치
테마가 다운된 경로에서 번들을 설치한다.
 # 아까 넣은 테마와 관련된 bundle 을 모두 설치한다.
 # 설치
 bundle install

 # 설치 확인
 jekyll -v
 jekyll 4.2.2

로컬 서버 실행

 # 로컬서버실행
 bundle exec jekyll serve


 # 아래 주소로 접속해서 정상적으로 지킬테마가 적용된 웹사이트가 출력되면 정상.
 # http://localhost:4000
 # http://127.0.0.1:4000

github에 바로 push를 하게 되면 잘못된 커밋도 모두 로그가 남고 번거롭다. 로컬서버로 테스트하면 즉각 반영되고 확인이 가능하므로 편하다.

완료!
로컬에서 루비 기반의 지킬테마를 정상적으로 실행했다.

로컬서버 실행시 Error 유형Permalink
: 작업도중 에러 유형을 실시간으로 기록했다.

유형1Permalink
에러내용

 # 에러내용
 Configuration file: C:/Users/user/Desktop/최태호/devgit/blangs.github.io/_config.yml Dependency Error: Yikes! It looks like you don't have tzinfo or one of its dependencies installed. In order to use Jekyll as currently configured, you'll need to install this gem. If you've run Jekyll with `bundle exec`, ensure that you have included the tzinfo gem in your Gemfile as well. The full error message from Ruby is: 'cannot load such file -- tzinfo' If you run into trouble, you can find helpful resources at https://jekyllrb.com/help/!
 jekyll 4.2.2 | Error:  tzinfo

해결방법
1. # [깃페이지 루트]/Gemfile 아래 내용 추가
 gem 'tzinfo'
 gem "tzinfo-data", platforms: [:mingw, :mswin, :x64_mingw, :jruby]

1. # 에러내용
 C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/jekyll-4.2.2/lib/jekyll/commands/serve/servlet.rb:3:in `require': cannot load such file -- webrick (LoadError)
     from C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/jekyll-4.2.2/lib/jekyll/commands/serve/servlet.rb:3:in `<top (required)>'유형2Permalink
 # webrick 설치
 bundle add webrick
 gem install webrick

1. # ERROR: Invalid first code point of tag name U+B9AC
ERROR: Invalid first code point of tag name U+B9AC
해결방법 : md 파일 내에 잘못 사용된 tag로 인하여 발생되는 에러 이며 tag가 아닌 부분은 명시적으로 tag가 아님을 확인 시켜주어야 합니다. <와 >의 앞에 \ 를 넣어주시면 해결이 됩니다. 아래는 해당 오류의 예입니다.
오류 발생 : https://raw.githubusercontent.com/<사용자 이름>/<리포지토리 이름>/master/<파일명>
화면 표시 : https://raw.githubusercontent.com/<사용자 이름=””>/<리포지토리 이름=””>/master/<파일명>
<p style="color:red">오류 해결 : https://raw.githubusercontent.com/\ <사용자 이름>/\ <리포지토리 이름\ >/master/\ <파일명\ ></p>

1. # Liquid Exception: undefined method ‘gsub’ for 3.0
Liquid Exception: undefined method ‘gsub’ for 3.0:Float string.gsub(replaceable_char, “-“)

Liquid Exception: undefined method `gsub' for 3.0:Float string.gsub(replaceable_char, "-") ^^^^^ in E:/Github/monoslab.github.io/_layouts/post.html   
   ------------------------------------------------   
   Jekyll 4.2.2   Please append `--trace` to the `serve` command   
                  for any additional information or backtrace.   
   ------------------------------------------------   
C:/Ruby31-x64/lib/ruby/gems/3.1.0/gems/jekyll-4.2.2/lib/jekyll/utils.rb:364:in `replace_character_sequence_with_hyphen':
 undefined method `gsub' for 3.0:Float (NoMethodError)   

   string.gsub(replaceable_char, "-")
          ^^^^^
1. # 해결방법 : tags의 배열에 숫자값이 먼저 나오는 경우 해당 오류를 발생시킵니다. 아래는 해당 오류의 예입니다.
오류 발생 : tags: [Error, TBC, 3.0]
오류 해결 : tags: [Error, TBC 3.0] —

1. # Error message
C:/Users/user/.local/share/gem/ruby/3.2.0/gems/jekyll-3.9.3/lib/jekyll/external.rb:68:in `rescue in block in require_with_graceful_fail': tzinfo (Jekyll::Errors::MissingDependencyException) 해결방법 : tags의 배열에 숫자값이 먼저 나오는 경우 해당 오류를 발생시킵니다. 아래는 해당 오류의 예입니다.
1. # 해결 방법
   1. gem install tzinfo
      gem install tzinfo-date
   1. Gemfile추가 
      gem 'tzinfo'
      gem 'tzinfo-data' , platforms: [:mingw, :mswin, : x64_mingw, :jruby]    