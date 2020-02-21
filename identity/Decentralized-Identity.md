# DID (Decentralized Identity)

## What is DID?




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
