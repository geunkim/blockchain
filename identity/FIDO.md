# FIDO (**F**ast **ID**entity Online)


비밀번호의 문제점을 해결하기 위해 FIDO Alliance에 의해 제안된 사용자 인증 프레임워크이다.
인증 기법(authentication method)와 인증정보를 교환하는 인증 프로토콜(authentication protocol)을 분리하는 것이 핵심이다. 
FIDO 규격은 비밀번호없이 인증하기 위한 UAF(Universal Authentication Framework) 프로토콜과 비밀번호를 보완하여 
인증을 하기 위한 U2F(Universal 2nd Factor) 프로토콜로 구성된다. 
지문, 홍체, 음성 등 생체 정보를 활용하여 사용자 인증에 적용하기 위해 주로 사용한다.

* UAF(Passwordless Experience):

  - 지문, 음성 등 사용자의 교유한 생체 인식 정보를 서버에서 처리하거나 저장하지 않고 사용자가 보유한 단말기에 저장한 후 
  그 결과 값을 전송하여 인증하는 방식으로 스마토 폰 등 개인 단말기를 통한 인증 체계에 활용되는 방식이다.

* U2F(Second Factor Experience):
  - 기존의 패스워드를 사용하는 온라인 서비스의 두 번째 인증요소로 강한 인증을 사용자 로그인 시 추가할 수 있는 기술
