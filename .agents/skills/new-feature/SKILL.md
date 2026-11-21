---
name: new-feature
description: 프로젝트명과 기능 폴더명을 받아 기존 프로젝트에 새 기능 폴더를 만들고 공용 요청서 템플릿을 복사한다.
---

# 새 기능 요청서 만들기

저장소 루트를 기준으로 작업한다. 호출 예시는 `$new-feature raidio-biz winter-new-channel-popup`이다. 첫 번째 값은 프로젝트 폴더명이고 두 번째 값은 기능 폴더명이다.

1. 값이 두 개이며 각각 영문 소문자와 숫자로 이루어진 단어를 하이픈으로 연결한 이름인지 확인한다. 형식이 맞지 않으면 호출 예시를 안내하고 중단한다.
2. `projects/<프로젝트>/project.md`를 읽고 `templates/request.md`가 있는지 확인한다. 프로젝트 문서나 템플릿을 찾을 수 없으면 해당 경로를 안내하고 중단한다. 템플릿이 비어 있으면 빈 파일을 그대로 복사한다.
3. `projects/<프로젝트>/features/<기능>/`을 만들고 그 안에 템플릿을 `request.md`로 복사한다. 상위 `features/` 폴더는 필요할 때 만든다. 기능 폴더는 기존 경로가 있으면 실패하는 방식으로 생성하고, 이미 있는 경우 중단한다. 기본 파일 도구 또는 `mkdir`과 `cp`로 처리한다.
4. 복사에 성공하면 새 요청서 경로를 알려준다. 위 예시 경로는 `projects/raidio-biz/features/winter-new-channel-popup/request.md`다. 복사에 실패하면 원인과 생성된 경로를 안내한다.
