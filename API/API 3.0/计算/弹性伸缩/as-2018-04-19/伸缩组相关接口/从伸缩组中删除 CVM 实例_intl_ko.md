## 1. API 설명

API 요청 도메인 이름: as.tencentcloudapi.com.

본 API(RemoveInstances)는 조정 그룹에서 CVM 인스턴스 삭제에 사용됩니다. 해당 로직에 따라 AS에서 자동으로 생성된 인스턴스가 폐기됩니다. 인스턴스가 생성 후 조정 그룹에 추가되면 조정 그룹에서 제거되고 보관됩니다.

기본 API 요청 빈도 제한: 20회/초.

주의: 본 API는 금융 지역을 지원합니다. 금융 지역과 비금융 지역은 격리되어 서로 연결되지 않기 때문에 공통 매개변수 Region이 금융 지역인 경우(예: ap-shanghai-fsi) 금융 지역을 포함한 지역명을 동시에 지정해야 하며 가장 좋은 것은 Region의 지역과 일치하는 것입니다. 예를 들어, as.ap-shanghai-fsi.tencentcloudapi.com입니다.



## 2. 입력 매개변수

다음 요청 매개변수 리스트에는 API 요청 매개변수와 일부 공통 매개변수만 나열합니다. 완전한 공통 매개변수 리스트는 [공통 매개변수](/document/api/377/20426)를 참조하십시오.

| 매개변수 이름 | 필수 여부 | 유형 | 설명 |
|---------|---------|---------|---------|
| Action | 예 | String | 공통 매개변수, 본 API 값: RemoveInstances |
| Version | 예 | String | 공통 매개변수, 본 API 값: 2018-04-19 |
| Region | 예 | String | 공통 매개변수, 세부 정보는 제품이 지원하는 [지역 리스트](/document/api/377/20426#.E5.9C.B0.E5.9F.9F.E5.88.97.E8.A1.A8)를 참조하십시오 |
| AutoScalingGroupId | 예 | String | 조정 그룹 ID |
| InstanceIds.N | 예 | Array of String | CVM 인스턴스 ID 리스트 |

## 3. 출력 매개변수

| 매개변수 이름 | 유형 | 설명 |
|---------|---------|---------|
| RequestId | String | 유일한 요청 ID, 매회 요청 시마다 반환됩니다. 문제를 찾을 경우 해당 요청의 RequestId를 제공해야 합니다. |

## 4. 예시

### 예시 1 조정 그룹에서 인스턴스 삭제

#### 입력 예시

```
https://as.tencentcloudapi.com/?Action=RemoveInstances
&AutoScalingGroupId=asg-boz1qhnk
&InstanceIds.0=ins-cri8d02t
&InstanceIds.1=ins-osckfnm7
&<공통 요청 매개변수>
```

#### 출력 예시

```
{
    "Response": {
        "RequestId": "5b039ee6-e8ff-4605-bb24-b45337747431"
    }
}
```


## 5. 개발자 리소스

### API Explorer

**해당 도구는 온라인 호출, 서명 인증, SDK 코드 생성과 빠른 검색 API 등 기능을 제공하고 클라우드 API 사용 난이도를 대폭 낮춰 사용을 추천합니다.**

* [API 3.0 Explorer](https://console.cloud.tencent.com/api/explorer?Product=as&Version=2018-04-19&Action=RemoveInstances)

### SDK

클라우드 API 3.0은 일체화된 SDK를 제공하고 여러 종류의 프로그래밍 언어를 지원하여 편리하게 API를 호출할 수 있습니다.

* [Tencent Cloud SDK 3.0 for Python](https://github.com/TencentCloud/tencentcloud-sdk-python)
* [Tencent Cloud SDK 3.0 for Java](https://github.com/TencentCloud/tencentcloud-sdk-java)
* [Tencent Cloud SDK 3.0 for PHP](https://github.com/TencentCloud/tencentcloud-sdk-php)
* [Tencent Cloud SDK 3.0 for Go](https://github.com/TencentCloud/tencentcloud-sdk-go)
* [Tencent Cloud SDK 3.0 for NodeJS](https://github.com/TencentCloud/tencentcloud-sdk-nodejs)
* [Tencent Cloud SDK 3.0 for .NET](https://github.com/TencentCloud/tencentcloud-sdk-dotnet)

### TCCLI

* [Tencent Cloud CLI 3.0](https://cloud.tencent.com/document/product/440/6176)

## 6. 오류 코드

다음은 API 비즈니스 로직과 관련된 오류 코드만 나열하며 다른 오류 코드는 [공통 오류 코드](/document/api/377/20428#.E5.85.AC.E5.85.B1.E9.94.99.E8.AF.AF.E7.A0.81)를 참조하십시오.

| 오류 코드 | 설명 |
|---------|---------|
| InternalError | 내부 오류 |
| InvalidParameterValue.LimitExceeded | 값이 제한을 초과했습니다. |
| ResourceInsufficient.AutoScalingGroupBelowMinSize | 조정 그룹 최소 인스턴스 수보다 적습니다. |
| ResourceNotFound.AutoScalingGroupIdNotFound | 조정 그룹이 존재하지 않습니다. |
| ResourceNotFound.InstancesNotInAutoScalingGroup | 목표 인스턴스가 조정 그룹 내에 존재하지 않습니다. |
| ResourceUnavailable.AutoScalingGroupInActivity | 조정 그룹이 활동 중입니다. |

