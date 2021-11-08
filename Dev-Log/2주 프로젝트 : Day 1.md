## 오늘은 어떻게 프로젝트에 기여했나요?
* 본격적으로 프로젝트에 들어가기 앞서서 Git Flow에 대해서 학습했다.
![Git Workflow](https://user-images.githubusercontent.com/77482552/140753331-550fdf49-52d2-44af-9c47-6ad5847b3723.png)

## 오늘의 프로젝트에서 힘든 점은 무엇인가요?
* 처음엔 프로젝트 Git Flow에서의 흐름이 잘 이해가 가지 않았다.
  하지만 팀원들과 레포지토리를 생성하여 브랜치도 만들고 간단한 기능도 구현해보고 push하면서 익숙해졌고,
  특히 merge를 하는 중에 내가 만난 에러와 팀원들이 만난 에러를 같이 핸들링 하면서 처음에는 시간도 걸리고 힘들었지만 해결하는 과정중에 오히려 이렇게 처음부터 에러를 직면한 것에 대해 경험도 되었고 나중에 도움이 될 것 같은 느낌이 들었다.
 
## 내일은 프로젝트에 기여하기 위해 무엇을 해야 하나요?
- [ ] SR(Software Requirement) 기획
---
## Project Git Flow 정리
1. 초기 Repo 설정 > Origin의 레포를 자신의 로컬로 클론

2. master branch에서 초기설정 진행

3. 초기설정완료 후 자신의 기준 Origin(git push origin master) / 팀원들에게는 Upstream이 될 Repo를 푸쉬

4. Dev 브랜치 생성(git checkout -b dev) / Dev 브랜치를 푸쉬(git push origin dev)

----------- 초기 설정 완료 ----------(초기설정자는 포크 클론을 안받아도 되나요?)

5. 자신의 Local에 작업공간 설정 -> Upstream의 Repo를 **포크(dev branch있는지 확인) & 클론**

6. 팀원들은 dev branch 생성(*git checkout -b dev*) dev 백업 ⇒ git push origin dev

- dev branch는 백업용 Master branch에서 devbranch를 생성하면
    
    즉시 자신의 Origin의 dev branch에 push하여 백업 (*git push origin dev*)
    
    (코드 작업은 dev branch에서 실행되는게 아니라 **Feature branch에서 진행**)
    
- local의 dev branch에서 feature[1,2,3] branch 생성 (*git checkout -b feature01*)

7. Feature Branch의 코드를 Upstream에 적용

8. Local 코드를 팀원들은 FeatureN branch에서 *git push origin FeatureN* 을 통해 Local코드를 자신의 Origin의 FeatureN Branch에 업데이트

9. Origin의 FeatureN Branch에서 Upstream의 Dev Branch(dev로 변경)로P/R 요청(자동으로 merge 되지 않음 머지거부가능)

10. 팀원이 P/R요청한 경우 **코드 리뷰를 거쳐** P/R을 Upstream의 Dev Branch에 Merge여부 결정(admin이 결정)

(Master로의 Pr은 배포가 되기 직전에)

11. 팀원들은 업데이트 된 Upstream의 Dev Branch의 코드를

(git remote -v , upstream 확인후 *git remote add upstream url*)

자신의 Local의 Dev Branch에서 Pull하여 Local Dev Branch 최신화(*git pull upstream dev*)

12. 자신의 Origin의 Dev Branch에 Push하여 백업

13. Origin의 Dev Branch에 백업이 완료된 경우 FeatureN Branch생성 후 추가적인 코드작업 시작

<마지막>

Upstream Dev Branch의 코드가 형태를 갖춘 경우 Upstream의 Dev Branch를Upstarem의 Master Branch에 적용

--------------Version 1------------------
