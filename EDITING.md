# 운영자용 수정 안내

사이트 방문자용 편집 화면은 없습니다. GitHub 저장소의 파일을 수정한 뒤 Commit changes를 누르면 자동 게시됩니다.

## 문구: locales.json

ko는 한국어, ja는 일본어입니다. 왼쪽 키는 유지하고 오른쪽 문구를 수정하세요. 사이트 제목은 site.title, 소개는 site.subtitle, 하단 안내는 site.footer입니다. {videos}, {clips}, {year} 등은 숫자가 들어갈 자리이므로 유지하세요.

## 디자인: style.css / index.html

style.css 첫 부분의 --accent는 강조색, --bg는 배경색, --ink는 글자색입니다. font-size는 글자 크기, padding과 margin은 여백입니다. 큰 요소 배치는 index.html에서 수정합니다. style.css 마지막 부분의 Bottom dock and video display에서 하단 재생 바와 영상 창을 수정할 수 있습니다.

## 클립: clips.json

한 클립당 id(중복 없는 이름), title(클립 이름), source(방송명), videoId(YouTube 영상 ID), start(시작 초), end(종료 초), category(장르), date(YYYY-MM-DD)를 입력합니다. 같은 videoId는 같은 영상으로, date의 연도에 따라 묶입니다. date가 없으면 ‘연도 미등록’에 표시됩니다.

별도 MP3나 audioUrl은 필요하지 않습니다. 기존 데이터에 audioUrl이 남아 있어도 재생에는 사용하지 않습니다. 현재 샘플 영상은 YouTube 공식 API 예제 영상이며 실제 후와 보이스는 아직 등록되지 않았습니다.

## 재생과 조회수

하단 바는 화면을 스크롤해도 고정됩니다. 영상 보기를 누르면 같은 YouTube 플레이어가 바 위에 펼쳐집니다. 영상 표시를 접어도 플레이어를 다시 만들거나 재생 위치를 초기화하지 않습니다. 정지를 누르면 플레이어를 정지하고 바와 영상 창을 닫습니다.

원본에서 직접 재생하지만 모든 재생이 조회수에 반영된다고 보장하지는 않습니다. YouTube 공식 문서는 플레이어 안의 기본 재생 버튼으로 시작한 재생에 대한 집계 조건을 명시합니다. 랜덤·자동·반복 버튼 사용만으로 집계를 보장할 수 없습니다. 플레이어를 화면 밖에 두고 재생하는 기능은 YouTube API 정책에서 허용하는 방식과는 별개라는 점에도 유의하세요.

유튜브 공식 플레이어에서는 별도 음성 파일용 음량 맞춤을 적용하지 않습니다. 기존 normalize.js와 demo-tone.wav 파일은 이전 버전의 파일이며 현재 페이지에서 읽지 않습니다.
