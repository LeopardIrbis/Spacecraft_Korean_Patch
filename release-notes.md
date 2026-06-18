# v1.2.0

- 공장/생산 상태값 `Running`이 `달리기`로 표시되던 오역을 `가동 중`으로 수정했습니다.
- 공장/생산 상태값 `Idle`이 `게으른`으로 표시되던 오역을 `대기 중`으로 수정했습니다.
- 행성간 물류 [1/2] 퀘스트와 관련된 물 수집/펌프/저장 탱크 문구 검증을 다시 확인했습니다.

검증:
- `python -m unittest discover -s korean_patch\tests -v` 통과
- `python korean_patch\spacecraft_korean_patch.py --verify --source-pak res1.pak` 통과
- EXE 임시 설치 테스트 통과
