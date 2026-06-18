# v1.1.8

- 행성간 물류 [1/2] 퀘스트 설명문에서 `?`로 보이던 물 수집 안내를 수정했습니다.
- `<small>...</small>` 설명문 태그가 깨지거나 조사가 태그 밖으로 밀려나는 유형을 빌드 검증에서 자동 차단합니다.
- 관련 퀘스트 설명문 일부를 자연스럽게 다듬고, 채굴국 용어 통일 검사를 유지했습니다.

검증:
- `python -m unittest discover -s korean_patch\tests -v` 통과
- `python korean_patch\spacecraft_korean_patch.py --verify --source-pak res1.pak` 통과
