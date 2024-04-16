# custom-calendar
공모주 일정이나 날씨 등 정보를 제공하는 캘린더


## 프로젝트 구조
프로젝트의 UI는 카카오오븐으로 대체하였습니다.


## ERD
DB로는 MySQL을 사용한다.
<BR>
기능별로 table을 분리한다.
<BR>
기상정보는 DB에 저장하지 않고 일정 시간을 기준으로 조회한 데이터를 사용할 예정이다.

special_day_data : 특일정보를 담은 table이다.
* name : 특일명
* specialDayDate : 특일날짜
* registrationDate : 등록시간

new_stock_data : 공모주 일정을 담은 table이다.
* name : 공모주명
* subscriptionDate : 청약날짜
* winningDate : 청약당첨날짜
* crapeDate : 상장날짜
* registrationDate : 등록시간 


## Branch 관리
이 프로젝트에서는 Git Flow 전략을 사용한다.
<br>
<br>
**feature** : issue 단위로 기능 개발할 때 사용하는 branch
<br>
**develop** : 개발 단계에서의 main branch
<br>
**release** : 운영계에 반영되기 위한 branch, 개발 단계의 검증은 끝났지만 운영 단계에서 QA가 필요한 단계의 branch
<br>
**hotfix** : 운영계에서 수정이 필요할 때 긴급으로 배포하기 위해 사용하는 branch
<br>
**main** : 테스트 완료된 안정적인 운영 단계의 main branch


## Commit message 관리
<br>
**DOCS** : 문서에 대한 commit
<br>
**FEAT** : 새로운 기능에 대한 commit 
<br>
**TEST** : 테스트 코드 수정에 대한 commit
<br>
**FIX** : 버그 수정에 대한 commit
<br>
**CHORE** : 자잘한 수정에 대한 commit



## 참조된 외부 API
* 공휴일 표기를 위한 공공데이터포털 API(특일정보)
https://www.data.go.kr/data/15012690/openapi.do
* 날씨 이모티콘 표기를 위한 API
https://data.kma.go.kr/api/selectApiDetail.do
* 공모주 일정 표기를 위한 API
    * 대부분의 기업들이 사용하는 coocon API는 과금이 필요하고, 이 프로젝트는 영리 목적이 아니기 때문에 크롤링을 통해 진행할 예정이다.
    * 추후 Open API가 있는 경우, api로 변경하고, 크롤링이 문제가 되는 경우에 삭제할 예정이다.