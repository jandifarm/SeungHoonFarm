# JekinsPluginStructure

이번 파일럿 프로젝트로 Jenkins Plugin을 개발하게 되었다.

현재 Jenkins pipeline에서 Kubernetes로 배포하는 과정에서 모든 빌드를 마치고 마지막 CD를 진행하는 과정에서 shell script로 helm Chart를 install/update 하여 배포하도록 되어있다.

이렇게 진행하게 될 경우 현재 Kubernetes로 배포된 application들의 형상관리가 어려운점이있다.

이를 해결하기위해 kubeapps를 도입해보려고 하고, 아를 위해 프로토타입 형태로 기존의 CD부분을 kubeapps의 API를 사용해서 배포를 해보려고 한다.

따라서 CD를 하는 시점에 kubeapps API를 사용해서 kubeapps로 배포하도록 하는 Jenkins Plugin을 개발하게 되었다.


## User Story

* 사용자는 개발된 Jenkins Plugin을 다운받는다.
* kubeapps에서 발급받은 토큰을 jenkins system config에 등록하여 클러스터를 등록한다.
* pipeline의 deploy부분을 해당 Plugin으로 대체하고 char에 대한 값들을 설정한다.
* deploy시 이미 배포가 되어있을 경우 upgrade를 진행하고 아닐경우 새로 deploy한다.
