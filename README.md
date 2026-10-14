# Week 7 — CI 기초: GitHub Actions 자동 Test

이번 주 한 문장: **CI는 팀 공통 환경에서 같은 검사를 자동으로 반복해 빠른 Feedback을 주는 장치입니다.**

## 이번 주 범위
- GitHub Actions 자동 Test만 합니다.
- AWS / Deploy / Development Server는 8주차부터 다룹니다.

## 완료 기준
1. 자동 Test PASS 1회
2. 일부러 만든 FAIL 1회
3. Actions Log에서 **실패한 Step과 이유**를 한 문장으로 설명
4. 수정 후 다시 PASS
5. PR에서 Checks 확인 후 Merge

## 실습 순서
0. 이 zip의 압축을 저장소 폴더(C:\dev)가 아닌 곳에 풀어 둡니다
1. 개인 GitHub 저장소 `week7-actions-lab` 생성 → Clone
2. 이 폴더의 `index.html`을 저장소 폴더로 복사 → Commit/Push
3. VS Code 터미널(Git Bash)에서 같은 검사를 먼저 실행 — 세 줄 모두 `0`이면 내 PC에서 PASS
   ```bash
   test -f index.html; echo $?
   grep -q "<title>" index.html; echo $?
   grep -q "<h1>" index.html; echo $?
   ```
4. New File에 `.github/workflows/html-check.yml`을 한 번에 입력해 만들고, 이 폴더의 `html-check.yml.txt` 내용을 전체 복사해 붙여넣기 (PDF·슬라이드에서 복사하지 않기)
5. Push → Actions PASS 확인
6. feature branch에서 `<title>`을 삭제 → Push → FAIL
7. Actions Log에서 `Check title tag` 실패 확인
8. `<title>` 복구 → Commit/Push → PASS
9. Pull Request → Checks → Merge → Local main Pull

## 기억할 3가지 질문
- 지금 코드는 어디에 있는가?
- 무엇이 실행되고 있는가?
- 어떤 Evidence로 성공/실패를 판단하는가?

자세한 화면 절차는 7주차 PPT/PDF를 그대로 따라 하세요.
