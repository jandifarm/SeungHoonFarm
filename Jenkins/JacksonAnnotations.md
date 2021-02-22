# Jackson-annotations

Jackson annotations은 이번에 Jenkins Plugin을 만들면서 helm Chart의 정보를 받아온다음 받아온 데이터를 kubeapps api를 통해서 kubeapps로 보내는 과정에서 key값의 변경이 필요했다.

처음에는 받아오는 DTO 보내는 DTO 2개를 만들어서 변환하여 진행하려 했지만, Jackson-annotations를 사용하면 Json으로 변환할 때 어노테이션에서 설정한 이름으로 key가 변경된다는 것을 알았다.

```
source code
```