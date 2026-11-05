# 나인빅스 팀원들의 기도

GitHub Pages용 정적 웹앱 시제품입니다. 빌드나 npm 설치 없이 배포합니다.

## 파일
- index.html: 전체 앱, 3D 캐릭터/기도마당/음악/채팅
- .nojekyll: Jekyll 빌드 생략용 빈 파일
- README.md: 배포 및 이용 안내

## GitHub 웹에서 배포
1. GitHub에서 새 저장소를 만듭니다. 예: ninevics-prayer
2. ZIP 파일을 PC에서 압축 해제합니다. ZIP 자체를 업로드하지 않습니다.
3. Add file > Upload files에서 index.html, README.md, .nojekyll을 저장소 최상위에 올리고 Commit changes를 누릅니다.
   숨김 파일 .nojekyll이 보이지 않아도 index.html은 반드시 올립니다.
4. Settings > Pages > Build and deployment > Source: Deploy from a branch
5. Branch: main, Folder: / (root)를 선택하고 Save를 누릅니다.
6. 배포 완료 후 Pages 설정에 표시되는 실제 주소를 엽니다.
7. 입장 후 초대 링크를 복사해 공유합니다. 같은 room 값으로 입장해야 만납니다.

index.html을 하위 폴더에만 넣으면 루트 주소에서 열리지 않습니다.
저장소 주소(github.com)와 웹사이트 주소(github.io)는 서로 다릅니다.

## 조작
WASD/방향키 이동, 드래그 시야, 1 합장, 2 가까운 빈 방석 앉기, 3 인사.
앉은 상태에서도 합장할 수 있습니다. Enter 채팅, Esc 입력 해제.
모바일은 조이스틱과 버튼을 사용합니다. 유니폼 보기로 앞면을 확인합니다.

## 기능 및 제한
흰 말티즈 + 녹색 야구 상의(흰 앞판/모자 없음), 방석 24개,
현수막 '나인빅스 밀양 우승 기원', 사찰풍 창작 합성음악, 이름 입장,
같은 방 이동/동작/채팅 공유. 배경은 실제 주택이나 로드뷰가 아닌 창작 앞마당입니다.

인터넷과 WebGL이 필요합니다. Three.js와 MQTT.js는 외부 CDN에서 불러옵니다.
GitHub Pages는 정적 파일만 제공하며 실시간 통신은 별도의 공개 EMQX 테스트
MQTT 서버(wss://broker.emqx.io:8084/mqtt)에 의존합니다.
이 서버는 비공개/인증/접속 보장을 제공하는 운영용 서버가 아닙니다.
이름/위치/메시지는 공개 채널로 전송됩니다. 개인정보를 입력하지 마세요.
앱에는 대화 이력 저장 기능이 없지만 외부 서버의 수집/보관 정책을 보장하지 않습니다.
클라이언트 측 메시지 제한은 악의적 접근을 막는 보안 장치가 아닙니다.
프로그램은 다른 캐릭터를 31명까지만 표시하도록 작성했으며 32명 동시접속을 검증하거나 보장하지 않습니다.
실제 다중 기기, 모바일, 브라우저 음원, 부하 테스트는 수행하지 않았습니다.
팀 전용 정식 운영에는 인증 및 접근 제어와 전용 실시간 서버가 필요합니다.

## 점검
- 입장 후 연결됨이 표시되는지 확인
- 다른 기기에서 같은 방 주소로 접속해 위치/합장/채팅 확인
- 채팅 입력 중 캐릭터가 움직이지 않는지 확인
- 방석 가까이에서 앉고 합장하는지 확인
- 소리가 안 나면 음악 켜기 및 브라우저/기기 음량 확인
- 404 오류면 index.html 위치와 Pages main / (root) 설정 확인

## GitHub 공식 안내
https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
https://docs.github.com/articles/creating-project-pages-manually
