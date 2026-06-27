# v1.2.1

- 게임 업데이트로 추가된 데모 오프라인 모드(`DemoOffline`) 안내 문구(`오프라인으로 데모 플레이` 등)를 빌드에 고정했습니다.
- 새 `res.pak`으로 재빌드할 때 해당 문구가 중국어로 되돌아가던 문제를 막았습니다.
- 번역되지 않은 중국어가 결과물에 남으면 검증 단계에서 실패하도록 가드와 테스트를 추가했습니다.
- 화면에 표시되는 번역 내용은 v1.2.0과 동일합니다. (기존 사용자는 재설치하지 않아도 됩니다.)

검증:
- `python -m unittest discover -s korean_patch\tests -v` 통과 (43개)
- `python korean_patch\spacecraft_korean_patch.py --verify --source-pak res1.pak` 통과 (cjk_count 0)
- EXE 임시 설치/삭제 테스트 통과

# v1.2.0

- 공장/생산 상태값 `Running`이 `달리기`로 표시되던 오역을 `가동 중`으로 수정했습니다.
- 공장/생산 상태값 `Idle`이 `게으른`으로 표시되던 오역을 `대기 중`으로 수정했습니다.
- 행성간 물류 [1/2] 퀘스트와 관련된 물 수집/펌프/저장 탱크 문구 검증을 다시 확인했습니다.

검증:
- `python -m unittest discover -s korean_patch\tests -v` 통과
- `python korean_patch\spacecraft_korean_patch.py --verify --source-pak res1.pak` 통과
- EXE 임시 설치 테스트 통과
