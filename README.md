# Protobuf 가이드

ProtoBuffer (https://github.com/protocolbuffers/protobuf)

언리얼 엔진에서 사용하려면 빌드된 .lib와 소스코드가 필요하다.

# 0. 주의

원래 Protobuf의 네이밍이 3.XX.XX 였는데

네이밍이 바뀐 22 버전부터는 ABSL이라는 외부 모듈이 추가로 필요한 것으로 보인다.

그래서 지금 설명할 방식으로 CMake를 사용하면 빌드가 되지 않는다.

그러므로 3.XX.X 버전의 가장 최신 버전인 v21.12를 기준으로 만든다.

## 0-01. 번외 : 다른 방법?

github desktop을 다운받고, protobuf를 github desktop으로 다운받으면 dependency에 포함해 받아진다.

필요한 버전을 선택하고, cmake를 사용해라.

# 1. 다운로드

Readme에 있는 Github release page에 들어간다.

적절한 버전을 찾는다.

해당 페이지에서 (~~~) 소스코드를 다운 받는다.

# 2. CMake

 CMake를 다운받는다.

CMake를 실행해서 받은 zip의 압축을 푼다.

where is the source code는 압축풀어서 나온 폴더로 세팅한다. (/cmake 경로로 직접 접근하면 안됨)

where to build the binaries는 적절한 폴더를 쓴다.

configure를 누르면 선택할 것들이 있지만, 그냥 기본값으로 세팅해도 된다.

Generate를 하면 진행이 되다가 멈추는데, BUILD_TESTS와 WITH_ZLIB를 체크를 풀고 다시 진행한다.

# 3. VS

만들어진 솔루션의 protobuf.sln을 들어가고 빌드한다.

빌드하기 전에 debug / release 와 x64 등의 세팅을 먼저 확인한다.

빌드가 완료되면 lib파일과 protoc.exe를 얻을 수가 있다.

debug로 빌드하면 파일 이름에 d가 붙고, release로 빌드하면 파일 이름에 d가 붙지 않는다. debug와 release 버전 둘다 필요하면 빌드를 따로해야한다.

# 4. 소스 코드

외부에서 사용할 때 소스 코드가 필요하다.

소스 코드는 처음에 압축 풀었던 폴더에 src/google 안에 있다.

소스 코드 경로가 전부 google이 들어가 있기 때문에 google 폴더 자체를 복사해서 사용하는 것을 추천함.