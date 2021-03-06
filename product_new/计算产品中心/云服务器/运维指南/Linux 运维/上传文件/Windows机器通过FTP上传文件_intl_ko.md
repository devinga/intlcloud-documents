## 작업 시나리오

본 문서는 FTP를 통해, 로컬 서버에서 클라우드 서버로의 파일 업로드 과정을 안내합니다.

## 전제 조건

클라우드 서버에 [FTP 구축 서비스](https://intl.intl.intl.cloud.tencent.com/document/product/213/10912)에 있어야 합니다.

## 작업 순서

1. 클라우드 서버에 로그인하십시오.
2. 오픈 소스 소프트웨어 FileZilla를 다운로드한 후 설치하십시오.
> FileZilla 3.5.3 버전을 사용해 FTP를 업로드할 경우, 업로드 실패 등의 문제가 나타날 경우, 공식 웹 사이트에서 FileZilla 3.5.1 버전 혹은 3.5.2 버전 사용을 권장합니다.
>
3. FileZilla를 여십시오.
4. FileZilla 창에서 호스트, 사용자 이름, 비밀번호 및 포트 등의 정보를 입력한 후 아래와 같이 [빠른 연결]을 클릭하십시오.
**구성 정보 설명**
 - 호스트: 클라우드 서버의 공용 네트워크 IP입니다. [클라우드 서버 콘솔](https://console.cloud.tencent.com/cvm)의 인스턴스 관리 페이지에서 해당 클라우드 서버의 공용 네트워크 IP를 조회할 수 있습니다.
 - 사용자 이름: [FTP 구축 서비스](https://intl.intl.intl.cloud.tencent.com/document/product/213/10912)에서 설정한 FTP 사용자의 계정입니다. 이미지 상의 "ftpuser1"이 예시입니다.
 - 비밀번호: [FTP 구축 서비스](https://intl.intl.intl.cloud.tencent.com/document/product/213/10912)에서 설정한 FTP 사용자 계정에 해당하는 비밀번호입니다.
 - 포트: FTP 수신 포트로써 기본값은 **21**입니다.
5. 왼쪽 하단의 "로컬 사이트" 창에서 업로드 대기 중인 로컬 파일을 마우스 우클릭해 [업로드]를 선택하면 아래와 같이 바로 Linux 클라우드 서버로 파일을 업로드할 수 있습니다.
> 
>- 클라우드 서버의 FTP는 업로드된 tar 압축 파일의 자동 압축 해제를 지원하지 않으며, 아울러 tar 파일의 기능을 삭제합니다.
>- 원격 사이트 경로는 파일을 Linux 클라우드 서버에 업로드하기 위한 기본 경로입니다.
>


