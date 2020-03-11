# 탈중앙형 식별자 DID (Decentralized Identifier)

물리세계의 신원과 달리 디지털 신원은 인터넷에서 사람을 식별하기 위한 것으로 초기에는 ID/PW 기반이었다.

기존의 신원관리시스템은 도메인 이름 저장소 또는 인증가관과 같은 중앙집중화된 시스템에 기반하였기 때문에 이러한 중앙집중화된 기관은 독자적으로 신뢰의 기반을 구축하여야 한다. 이러한 방식의 쉬운 예는 정부가 생성한 여권으로 시민이 어디에 가든 신분증으로 사용할 수 있도록 하는 시스템에 의해 관리된다. 

블록체인 기술은 탈중앙형 신원관리시스템을 사용할 수 있는 기회를 제공한다. 이 시스템의 엔티티들은 모든 공유된 신뢰 기반을 자유롭게 사용할 수 있다. 
즉 블록체인 기술의 등장으로 권한이 있는 중앙 기관이 없어도 저장된 데이터의 신뢰성을 보장할 수 있는 탈중앙형 신원정보관리 시스템을 구현할 수 있게 한다.  

이 시스템에는 개인, 기관, 사물과 같은 개별 대상(object)을 탈중앙 식별자(DID: Decentralized Identifier)로 식별되고 
전자서명, 프라이버시가 보호된 생체정보 등과 같은 검증가능 자격증명 데이터로 인증된다. 

## 디지털 신원 (Digital Identity)

W3C DID WG의 DID 정의에 따르면 DID는 분산원장 기술 또는 다른 형태의 탈중앙형 네트워크에 등록되어 권한을 가진 중앙화된 등록기관에 등록할 필요가 없는 
글로벌한 식별자로 정의한다.

W3에서 자원에 대한 식별자로 URN(Unified Resource Name)과 URL(Unified Resource Locator) 

DID는 W3C의 URN(Unified Resource Name: 영구적인 자원 이름)의 규격과 동일한 기본 패턴을 바탕으로 여러 블록체인에 적용하기 위해 표준화가 진행되었다.
DID는 사용자를 중심으로 개인 신원정보를 생성, 사용, 삭제 등 개인 신원정보를 관리할 수 있는 기반을 제공하여 '나'를 구별하고 '내'가 '나'임을 증명할 수 있는
방법을 제공한다. 

DID





* public DID vs private DID


## Related Terminologies (관련 용어)

* credentials (자격증명데이터): 사실 또는 자격을 증명할 수 있는 데이터
   + 예: 운전 면허증, 의사 신분증, 졸업장, 사원증 등
   + 운전 면허증: 

* verifiable credentials(검증가능 자격증명데이터): 물리적인 자격증명데이터가 표현하는 것과 같은 모든 정보를 표현할 수 있다.
디지털 서명과 같은 기술들을 추가하여 물리적인 자격증명데이터보다 변조되지 않고 더욱 신뢰할 수 있는 자격증명 데이터 
   + verifiable credentials의 보유자(Holder)는 특정 특성을 가진 verifiable creddentials를 가지고 있다는 것을 증명하기 위해서 
   verifiable presentation을 생성하고 검증자(verifier)와 verifiable presentation을 공유한다.
   
* verifiable presentation(검증가능 표현): 특정 검증자(verifier)와 공유되는 하나 이상의 발행자(issuer)가 발행한 하나 이상의
검증가능 자격증명데이터로 부터 파생된 데이터
    + 암호 검증 프로세스 후 데이터의 소유권을 신뢰할 수 있도록 인코딩하여 변조를 감지할 수 있는 표현
    + verifiable presentation의 형태에 오리지널 검증가능 자격증명데이터로 부터 합성이 되었으나 원 검증가능 자격증명데이터는
    포함하지 않는 데이터가 포함될 수 있다. (영-지식 증명) 
    
 * holder(보유자):
 
 
 * issuer(발행자):
 
 
 * verifier(검증자):
 
 
 * verifiable data registry(검증 데이터 저장소):
   



## Ecosystem (생태계)


![image](https://miro.medium.com/max/2270/1*Cke4CG4fJlcpLNxgVsO_hw.png)



## Standards related to DID

* W3C: [Verifiable Credentials Data Model 1.0 Expressing verifiable information on the Web](https://www.w3.org/TR/vc-data-model/#what-is-a-verifiable-credential) - W3C Recommendation 19 Nov. 2019.


## References

[Decentralized Identifiers: the easy guide](https://medium.com/metadium/decentralized-identifiers-the-easy-guide-fb96429e8b24)
