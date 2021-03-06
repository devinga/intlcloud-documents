## 소개

AS는 모니터링되는 지표에 따라 동적으로 확장되는 스케일링 그룹의 용례 수를 지원하며, 확장된 모니터링 지표 상태를 트리거하고 수요 변화에 따라 확장하는 알람 트리거 정책을 정의해야 합니다.

알람 정책을 생성하려면 조건 및 조치를 지정해야 합니다.
- 조건 양식: 지표+임계 값+주기+ 지속적으로 도달한 임계 값 주기수. 지표는 연속 N개 주기에 모두 임계 값에 도달합니다.
- 실행 행위: 공지 전송+지정된 Cloud Virtual Machine 수의 증가/감소

각 스케일링 그룹에 확장 정책과 축소 정책을 생성할 것을 권장합니다. 비지니스양이 알람 정책에 지정된 조건에 도달하면 AS는 실행 연결 정책을 스케일링 그룹에 대해 축소(용례 종료) 및 확장(용례 시작)을 수행합니다.

다음 이미지 참고:
![](https://mc.qcloudimg.com/static/img/83557f69f860be57cf464b2b45ab31c5/1.jpg)


## 시나리오 예시

예를 들어 현재 5개 용례를 사용하는 전자상거래 웹 사이트 애플리케이션이 있습니다. 액세스가 예상을 초과할 것을 대비해 운영 이벤트를 수행한 경우, 현재 용례의 부하가 70%로 증가하면 두개의 새로운 용례를 설정하고, 부하가 40%로 감소하면 필요없는 용례를 종료합니다. 이런 조건에 따라 스케일링 그룹을 구성하여 자동으로 확장할 수 있습니다.
![](https://main.qcloudimg.com/raw/97a4db1b251321307f58e4f75057ad00.png)

## 작업 절차

1. [콘솔](https://console.cloud.tencent.com/autoscaling/config)을 열고 사이드바의 [스케일링 그룹]을 선택합니다.

2. 수정할 스케일링 그룹을 선택하고 ID를 클릭하면 기본 정보 페이지로 진입합니다.
![](https://mc.qcloudimg.com/static/img/cebad1b79ccba9fb9548c2bd2c30a210/2.jpg)


3. 위의 사이드바에서 [알람 트리거 정책]을 선택하고 이 페이지에서 스케일링 그룹과 관련된 알람 트리커 정책을 관리합니다.
	- [생성]을 클릭하여 새로운 알람 트리거 정책을 추가하십시오.
	- [삭제]를 클릭하여 해당 알람 트리거 정책을 삭제하십시오.
![](https://mc.qcloudimg.com/static/img/570e5bd24b8975c65dd939bc9052d5a3/3.jpg)



## 알람 스케일링 정책의 영향을 받지 않는 서버 지정
오토스케일링을 사용하기 전에 시스템은 이미 상용 서버가 있고 알람 스케일링 정책에서 기기를 제거하지 않으려면 아래 몇가지를 참고해야 합니다.

**멀티 사용** : 클러스터의 서버는 클러스터의 작업을 수행하는 외에도 다른 용도로 사용됩니다. 예를 들어, 웹 사이트 구축 초기에 사용자 서버는 캐시 서버 및 파일 서버로 사용됩니다. 캐시 서버 클러스터가 스케일링 그룹에 배치되면 알람 스케일링 정책에서 제거되는 것을 원하지 않습니다.

-**데이터 저장**: 서버는 상태 저장 또는 다른 서버에 없는 데이터를 가져옵니다. 예를 들어, 클러스터에서 다른 서버 실행 중에 생성된 증분 데이터는 모두 해당 서버에 저장됩니다.

**미러이미지/스냅숏 업데이트**:이 서버는 정기적으로 미러이미지와 스냅숏을 사용합니다.


**설정 방법:**

**1단계**: [스케일링 그룹 목록](https://console.cloud.tencent.com/autoscaling)에서 서버가 있는 스케일링 그룹을 클릭하여 관리 페이지로 진입합니다.

**2단계**: 관리 페이지 하단의 "클라우드 호스트 목록"에서 설정하려는 클라우드 호스트의 " 보호 설정 제거"를 클릭하십시오.
