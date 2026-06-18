# v1.1.9

- 예전 작업에서 남은 깨진 `res/extra/lang/export_ko.xml`을 설치 시 자동으로 백업 처리합니다.
- 이 레거시 파일은 `한글Ve a ::target::`처럼 스페인어/한글 접두어가 섞인 파일이라, 게임에서 한국어 슬롯을 잡으면 NPC 대화 선택지가 안 보일 수 있었습니다.
- 현재 패치는 중국어/中文 슬롯(`export_zh.xml`)을 사용합니다.

검증:
- `python -m unittest discover -s korean_patch\tests -v` 통과
- EXE 임시 설치 테스트에서 레거시 `export_ko.xml` 자동 백업 확인
