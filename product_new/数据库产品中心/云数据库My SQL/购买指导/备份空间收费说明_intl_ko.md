## 개요
백업 공간은 한 지역에 위치한 전체 TencentDB for MySQL 인스턴스의 백업 파일을 저장합니다. 백업 파일은 자동 데이터 백업, 매뉴얼 데이터 백업 및 로그 백업을 포함합니다. 

TencentDB for MySQL는 지역별로 일정 사이즈의 무료 백업 공간을 증정합니다. 무료 백업 공간 사이즈는 대응하는 지역별 전체 고가용 인스턴스(마스터 인스턴스, 재해 복구 인스턴스 포함)의 스토리지 공간 합계입니다. 
>
>- 읽기 전용 인스턴스 RO를 구매 시 백업 공간을 증정하지 않습니다. 마스터 인스턴스와 장애 복구 인스턴스를 구매 시에만 증정합니다. 
>- 백업 공간 사이즈는 [MySQL 콘솔](https://console.cloud.tencent.com/cdb/backup)의 데이터베이스 백업 페이지에서 확인할 수 있습니다. 

## 백업 가격
백업 공간이 무료 할당액을 초과할 경우, 중국 대륙 지역은 0.0008위안/GB/시간  기준으로 요금을 부과합니다. 기타 지역의 가격은 [TencentDB for MySQL 가격계산기](https://buy.cloud.tencent.com/price/cdb/calculator)를 참조하십시오.
요금 부과 공간이 6.25GB 미만일 경우 차감하는 요금이 없습니다. 1시간 미만은 1시간으로 집계합니다. 유연한 TencentDB for MySQL 증정 정책을 적용하므로 절대부분 인스턴스는 백업 공간에 별도로 요금을 지불하지 않습니다. 

## 백업 요금 부과 시간
- 2019년 11월 22일 0시부터 아시아·태평양지역(도쿄, 서울, 뭄바이)에서 요금을 부과합니다.
- 2019년 11월 25일 0시부터 홍콩·마카오·타이완지역(중국 홍콩)과 기타 국외 지역에서 요금을 부과합니다.
-2019년 11월 26일 0시부터 서남지역(청두, 충칭)에서 요금을 부과합니다.
- 2019년 11월 27일 0시부터 화남지역(선전 금융), 화동지역(상하이 금융), 화북지역(베이징 금융)에서 요금을 부과합니다.
- 2019년 11월 28일 0시부터 화북지역(베이징)에서 요금을 부과합니다.
- 2019년 12월 02일 0시부터 화남지역(광저우)에서 요금을 부과합니다.
- 2019년 12월 05일 0시부터 화동지역(상하이)에서 요금을 부과합니다.

## 컴퓨팅 수식

**무료 백업 공간(낱개 지역)=해당 지역에서 구매한 MySQL 고가용 인스턴스의 스토리지 공간 합계**

**요금 사항(낱개 지역)=데이터 백업량(해당 지역)+로그 백업량(해당 지역)-무료 백업 공간(해당 지역)

>휴지통의 TencentDB for MySQL 인스턴스 백업은 여전히 백업 공간으로 간주되며, 전체 공간 사이즈에 포함됩니다. 

**컴퓨팅 예시**
예를 들면 광저우3존에 작동중인 MySQL 고가용 인스턴스(구매한 데이터베이스 스토리지 공간은 월 500GB)와 광저우4존에서 작동중인 MySQL 고가용 인스턴스(구매한 데이터베이스 스토리지 공간은 월 200GB)를 소유할 경우, 광저우 지역은 월별 700GB 공간을 무료로 사용할 수 있습니다.

광저우 지역에서 전체 백업 스토리지가 700GB를 초과할 경우, 예를 들어 데이터 백업 800G, 로그 백업 100G 달성 시 시간당 요금 공간은  800+100-700=200GB/시간입니다. 관련하여 사용자는 별도로 이 200GB에 대응하는 백업 공간 요금을 지불해야 합니다.

## 백업 라이프사이클
<span id = "anliang_zhouqi"></span>
### 종량제 인스턴스
- 백업은 인스턴스의 라이프사이클 기반으로 변화합니다
- 인스턴스 만료 2시간 미만 시, 정상적으로 백업합니다.
- 인스턴스는 만료 2시간 이후 격리되어 휴지통에 이전합니다. 이때 자동 백업, 롤백 금지, 매뉴얼 백업과 백업 다운로드를 종료합니다. 사용자는 콘솔 휴지통에서 재충전하여 인스턴스와 백업을 복구할 수 있습니다.
- 인스턴스는 1일간 격리된 후 공식 비활성화됩니다. 이때 인스턴스는 철저히 삭제되며 관련 데이터 백업도 같이 삭제됩니다. 사용자는 빠른 기간내에 원하는 백업을 저장해주시기 바랍니다.

## 계정 연체 설명

### 종량제 인스턴스
계정이 연체되면, 백업은 사용자의 인스턴스 라이프사이클 기준으로 변화합니다. 위 텍스트의 종량제 백업 라이프사이클 소개를 참조하십시오.
