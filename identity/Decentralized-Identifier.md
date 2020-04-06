# 탈중앙형 식별자 (DID: Decentralized Identifier)

물리세계의 신원과 달리 디지털 신원은 인터넷에서 사람을 식별하기 위한 것으로 초기에는 ID/PW 기반이었다.

기존의 신원관리시스템은 도메인 이름 저장소 또는 인증가관과 같은 중앙집중화된 시스템에 기반하였기 때문에 이러한 중앙집중화된 기관은 독자적으로 신뢰의 기반을 구축하여야 한다. 이러한 방식의 쉬운 예는 정부가 생성한 여권으로 시민이 어디에 가든 신분증으로 사용할 수 있도록 하는 시스템에 의해 관리된다. 

블록체인 기술은 탈중앙형 신원관리시스템을 사용할 수 있는 기회를 제공한다. 이 시스템의 엔티티들은 모든 공유된 신뢰 기반을 자유롭게 사용할 수 있다. 
즉 블록체인 기술의 등장으로 권한이 있는 중앙 기관이 없어도 저장된 데이터의 신뢰성을 보장할 수 있는 탈중앙형 신원정보관리 시스템을 구현할 수 있게 한다.  

이 시스템에는 개인, 기관, 사물과 같은 개별 대상(object)을 탈중앙 식별자(DID: Decentralized Identifier)로 식별되고 
전자서명, 프라이버시가 보호된 생체정보 등과 같은 검증가능 자격증명 데이터로 인증된다. 

W3C DID WG의 정의에 따르면 탈중앙형 식별자는 분산원장 기술(distributed ledger technolology) 또는 다른 형태의 탈중앙형 네트워크에 등록되기 때문에 
중앙의 등록기관이 필요 없는 글로벌하게 유일한 식별자(globally unique identifier)로 정의한다.
DID는 W3C의 URN(Unified Resource Name: 영구적인 자원 이름)의 규격과 동일한 기본 패턴을 바탕으로 여러 블록체인에 적용하기 위해 표준화가 진행되었다.
DID는 사용자를 중심으로 개인 신원정보를 생성, 사용, 삭제 등 개인 신원정보를 관리할 수 있는 기반을 제공하여 '나'를 구별하고 '내'가 '나'임을 증명할 수 있는
방법을 제공한다. 

중앙의 등록기관을 요구하지 않는 글로벌 식별자에 대한 요구가 처음이 아니라 2016 년에 W3C의 URN(Unified Resource Name) 규격의 기본 패턴을 따라 
복수의 블록체인에서 동작할 수 있도록 DID를 적용하는 것이 논의되었다. DID에서는 URN의 이름 공간(namespace) 컴포넌트를 
DID 메소드를 규정하는데 사용하고 DID 메소드 규격은 메소드 별 식별자(method-specific identifier)의 형식을 정의한다.
다음은 uuid를 표현하는 URN을 표현하고 있다(출처:w3c). 

![image](./uuid_fornat.png)

다음은 DID를 표현하고 있다.(출처:w3c)

![image](./did_format.png)

디저털 공간에서 모든 개체(entity)는 필요한 수 만큼 (관련 DID 문서와 서비스 종단점 과 함께) DID를 가질 수 있다. 이는 신원(identity), 정체성(persona), 문맥(context)을 분리하려는 개채의 요구를 수용하기 위한 것이다.  

## DID 문서 (DID documents)

DID는 DID 문서를 가리킨다. w3c는 DID 문서를 "DID 주체(subject)가 자신을 인증하고 DID와의 연관성을 입증하는데 사용할 수 있는 공개키 및 생체 인식과 같은
메커니즘을 포함한 DID 주체를 설명하는 데이터 집합" 으로 정의한다. DID 문서는 주체를 설명하는 속성들 또는 주장(claim)들을 포함하기도 한다. 
일반적으로 이 문서는 JSON-LD를 사용하여 표현된 그래프 기반 자료 구조이나 호환 가능한 다른 그래프 기반 데이터 형식을 사용하여 표할될 수 있다.   
DID와 DID 문서는 탈중앙화된 신원의 기반이나 주체를 기술하는 첫 단계이다. 

## DID 방법 (DID method)


DID 방법은 특정 분산 원장 또는 네트워크에서 DID와 관련 DID 문서를 생성, 읽기, 갱신, 비활성화하는 메커니즘이다. 
특별한 탈중앙형 식별자에 DID와 DID 문서의 모든 기능을 가능하게 하기 위해서 DID 방법 명세(specification)은 클라이언트에서 실행되는 
CRUD (Create, Read, Update and Deactive) 작업의 동작 방법을 정의해야 한다.   

DID 방법은 중앙 집중형 신원관리시스템 또는 연합된 신원관리시스템을 위해서도 개발될 수 있다. 모든 유형의 신원관리시스템은 중앙집중형, 연합형,
탈중앙형 식별자 도메인 간 상호 운용성 브리지를 만들어서 DID 지원기능을 추가할 수 있다. 


## Related Terminologies (관련 용어) (defined by W3C Verifiable Credentials Data Model)

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
   
* entity(엔티티): 검증가는 자격증명 데이터의 생태게(?)에서 하나 이상의 역할을 수행하는 사람, 조직, 디바이스와 같이 구별이 되고 독립적으로 존재하는 것(thing)

* digital signature(전자 서명): 디지털 메시지의 진위를 증명하기 위한 수학적인 절차 





## 주요 컴포넌트

* holder(보유자): 하나 이상의 검증가능 자격증명데이터(verifiable credentials)을 소유하고 그것으로 부터 표현(presentation)을 생성하는 개체(entity) 
     + 에: 학생, 고객, 직원
  
* issuer(발행자): 검증가능 자격증명데이터(verifiable credentials)을 생성하여 특정 주체와 연결하여 보유자(holder)에게 전송하는 개체(entity) 
     + 예: 기업, 정부 또는 비영리 단체
 
* Subject(주체): 하나 이상의 검증가능 자격즘명데이터를 주장하는 개체(entity)로 검증가능 많은 경우 자격증명데이터의 보유자가 주체이나 항상 그렇지 않음 
 
* Verifier(검증자): 보유자가 요청한 특정 특성을 가진 검증가능 자격증명데이터를 보유하고 있음을 증명하는 검증가능 표현(presentation)을 요청 및 수신하는 개체(entity)
 
* Verifiable data registry(검증 데이터 저장소): 식별자, 키, 관련 데이터의 생성 및 검증을 중재하는 시스템


## 개인 정보 (Personal Information)

개인 데이터는 정부에서 발급한 식별자, 배송지 주소, 이름 등을 포함하며 개체(entity)를 결정, 추적 및 상관시키기 위해 쉽게 사용될 수 있다. 
이 데이터는 프라이버시 위반에 민감하고 취약한다. 개인적으로 식별가징하니 않는 데이터조차도 다수에게 노출될 수 있다. 
에로 생년월일과 우편번호의 조합은 매우 강력한 상관관계와 익명해제능력을 가질 수 있다. 

## 주장 (Claims)

주장(claim)은 주체(subject)에 관한 서술(statement)이다.
기본적으로 주장은 다음과 같이 주체(subject), 속성(property), 값(value)의 관계로 표현한다. 

![image](./basic_claim_structure.png)

<주장의 기본 구조: source W3c Verifiable Credentials Data Model 1.0>

이 모델은 주체에 대한 다앙한 서술을 하는데 사용할 수 있다. 한 예로 특정인이 특정 대학을 졸업하였는지를 표현할 수 있다. 다음 예는
Pat 가 "Example University의 졸업생"이라는 것을 표현하는 기본적인 주장이다. 

![image](./basic_claim_example.png)

또한 개별적인 주장은 주체에 대한 정보의 그래프 표현을 위해 합칠 수 있다. 이 그래프는 주체와 다른 주체 또는 데이터와의 관계로 구성된 정보의 네트워크이다.
다음은 앞의 예에 Pat가 Sam을 알고 있고 Sam의 직업이 교수라는 것을 나타내는 그래프이다. 

![image](./claims_network.png)

{Q} "이러한 주장들이 믿을 수 있기 위해서 더 많은 정보들이 그래프에 추가될 것이 기대된다" 고 하는데 이 그래프를 구성하는 주체는? 


## Credential Subject (자격증명 주체)

보유자가 제시한 검증가능한 자격증명(verifiable credentials)에는 각 credentialSubject의 *id* 속성과 연관된 값은 
주체(subject)를 검증자(verifier)로 식별할 것으로 예상된다. 또한 보유자가 주체이면 검증자는 자격증명이 보유자와 관련한 공개키 메타데이터를 
가지고 있으면 검증자는 보유자를 인증할 수 있다.  
검증자는 verifiable presentation에 포함된 보유자의 전자 서명으로 보유자를 인증할 수 있다. *id*속성은 선택사항이다. 검증자는 주체를 
유일하게 식별할 수 잇는 검증가능 자격증명(verifiable credential)의 다른 속성을 사용할 수 있다. 

## nonTransferable property (양도불가능한 속성)

credentialSubject만 verifiable presentation에 verifiable credential을 추가할 수 있다면 발행자는 verifiable credential에 
nonTransferable 속성을 추가할 수 있다.
nonTransferable property는 verifiable credential이 credentialSubject에 의해 발행된 증명을 가지고 있는 verifiable presentation으로 만
캡슐화되어야 함을 나타낸다. 즉 nonTransferable property가 true이면 verifiable credential은 credentialSubject에 의해 발행된 증명을 가지고 있는
veerifiable presentation에 의해 캡슐화된다. 

nonTransferable 속성이 포함된 verifiable credential를 포함하는 verifiable presentation의 증명 작성자가
credentialSubject가 아니면 verifiable presentation은 유효하지 않다. 




## Credentials (자격증명데이터)
 
자격증명데이터는 같은 엔티티에 의해 생성된 주장들의 집합이다. 자격증명데이터는 식별자(identifer)와  
발급자(issuer), 만료 날짜와 시간, 대표 이미지, 검증 목적으로 사용되는 공개키, 해지 메커니즘 등 자격증명데이터의 속성을 기술하는 메타데이터를 포함할 수 있다. 
메타데이터는 발급자가 서명한 것 일 수 있다. 검증가능한 자격증명데이터는 변조을 감지할 수 있는 주장(claim)들과 발급자를 암호화 방법으로 증명하는데 사용되는 
메타데이터를 포함한다.

디지털 직원 신분증, 디지털 출생 증명서, 디지털 교육 증명서가 검증가능한 자격증명데이터의 예이다. 
자격증명 데이터 식별자는 자격증염데이터의 특정한 인스턴스를 식별하는데 사용된다. 식별자들은 상관 관계를 설졍하는데 사용할 수도 있다. 상관 관계를 최소화려는 
보유자는 자격증명 식별자를 밝히지 않고 선택적 공개 체계를 사용하는 것이 바람직하다. 

![image](./verifiable_credential.png) 
(source: w3c)

앞의 그림은 검증가능한 자격증명데이터의 기본 컴포넌트로 주장들이 어떻게 정보 그래프로 구성되고 정보 그래프가 검증가능한 자격증명데이터로 어떻게 구성되는지에
대한 상세한 내용을 추상화하였다.  

다음은 최소한 두 개의 정보 그래프로 구성한 검증가능한 자격증명에 대해 상세하게 설명하고 있다. 첫 그래프는 검증가능한 메타데이터와 주장을 포함한 검증가능한 
자격증명을 포현한다. 두번쩨 그래프는 일반적으로 디지털 서명인 디저털 증명(digital proof)를 나타낸다. 

![image](./info_graph_verifiable_credential.png)

자격증명데이터 그래프를 살펴보면 



## Ecosystem (생태계)

![image](https://miro.medium.com/max/2270/1*Cke4CG4fJlcpLNxgVsO_hw.png)


## Standards related to DID

* W3 Draft CG Reprt: [A Primer for Decentralized Identifiers](https://w3c-ccg.github.io/did-primer/) (unofficial draft)
* W3C Working Draft: [Decentralized Identitifers (DIDs) v1.0 Core Data Model and Syntaxes](https://w3c.github.io/did-core/)
* W3C Recommendation: [Verifiable Credentials Data Model 1.0 Expressing verifiable information on the Web](https://www.w3.org/TR/vc-data-model/#what-is-a-verifiable-credential) 19 Nov. 2019.
* W3C Working Draft: [Use Cases and Requirements for Decentralized Identifiers](https://www.w3.org/TR/did-use-cases/) 30 January 2020

## References

* [W3C DIDs 한글 번역 문서](https://ssimeetupkorea.github.io/did-core/) 
* [Decentralized Identifiers: the easy guide](V)
* [Decentralized Identifiers: Personal Information and Claims, the easy guide](https://medium.com/metadium/decentralized-identifiers-personal-information-and-claims-the-easy-guide-ee58b5427dd2)
