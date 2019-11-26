# Commands in Hyperledger

## commands related peer (피어와 관련한 명령어)

```peer```관련 명령어는 다섯 영역의 명령어군으로 구성되며 이 명령어를 통해 관리자는 피어와 관련한 작업을 수행할 수 있다. 
```peer``` 관련 명령어의 다섯 영역은 다음과 같다. 

```shell
~$peer chaincode [option] [flags]   // 스마트 컨트렉트 관련 명령어
~$peer channel   [option] [flags]   // 채널 관련 명령어 
~$peer logging   [option] [flags]   // 피어의 로그 레벨을 동적으로 설정하고 볼 수 있는 명령어 
~$peer node      [option] [flags]   // 피어 노드와 관련한 명령어
~$peer version   [option] [flags]   // 피어의 버전 등의 정보를 디스플레이하는 명령어 
```

### ```peer channel``` 관련 명령어

#### Syntax

```peer channel``` 명령어는 채널에 조인하거나, 피어가 조인한 채널 목록과 같이 피어에서 채널과 관련한 동작을 수행한다.
```peer channel``` 명령어가 가지는 ```option```은 다음과 같다. 

* ```ceate``` : 채널을 생성하고 genesis block을 파일에 저장 
* ```fetch``` : 특정 블록을 패치하여 파일에 저장
* ```getinfo``` : 특정 채널에 대한 블록체인 정보 취득 (채널 이름을 명시해야 하므로 ```-c``` 플래그가 필요)
* ```join``` : 피어를 채널에 조인
* ```list``` : 피어가 조인한 채널 목록 취득
* ```signconfigtx``` : 파일 시스템에 제공된 configtx update 파일에 서명 (```-f``` 플래그가 필요) 
* ```update``` : 제공된 configtx update 파일을 사인하고 채널에 전송 (```-f, -o, -c``` 플래그가 필요)

##### ```create``` option 예제

```shell
~$peer channel create -c mychannel -f ./createchannel.tx --orderer orderer.example.com:7050
```

블록체인 네트워크에 대해 ```orderer.example.com:7050```의 order를 이용하여 ```mychannel```이라는 새로운 채널을 생성한다.
```./createchannel.tx```파일에는 채널을 생성하는데 요구되는 **configuration update transaction** 이 정의된다.
채널이 성공적으로 생성되면 이 채널에 대한 블록 0 (제네시스 블록)에 추가되고 피어에 반환되고 로컬 디렉토리에 ```mychannel.block```
으로 저장된다. 

##### ```join``` option 예제

```shell
~$peer channel join -b ./mychannel.genesis.block
```

```./mychannel.genesis.block``` 파일로 식별되는 제네시스 블록 내에 정의된 채널에 피어를 조인한다. 

### ```fetch``` option 예제
```newest``` option을 사용하여 가장 최근의 블록을 취득하고 로컬 파일로 ```mychannel.block```에 저장한다.

```shell
~$peer channel fetch newest mychannel.block -c mychannel --orderer orderer.example.com:7050
```
```newest``` 대신에 블록 번호(###)를 option으로 명시하면 명시한 번호의 블록을 로컬 파일 ```mychannel_###.block```
로 저장한다.

### ```getinfo``` option 예제 
채널에 대한 정보를 취득할 때 사용한다. 채널의 블록체인에 가장 최근에 추가된 블록에 대한 암호화된 해시값을 확인할 수 있다.
```shell
~$peer channel getinfo -c mychannel
```

### ```update``` option 예제 
```./updatechannel.tx``` 파일에 정의된 configuration transaction을 사용하여 채널의 구성을 업데이트한다. 다음 명령어는
```orderer.example.com:7050```를 통해 ```./updaechannel.tx```파일에 정의된 configuation transaction을 사용하여 
```mychanel```을 구성을 업데이트한다. 채널 구성의 복사본을 채널 내의 모든 피어에 업데이트하기 위해서 
configuration transaction을 orderer에 전송한다.

```shell
~$peer channel update -c mychannel -f ./updatechannel.tx -o orderer.example.com:7050
```

### ```list``` option 예제 
피어가 조인한 채널들의 목록을 얻을 수 있다. 

```shell
~$peer channel list
```

### ```signconfigtx``` option 예제 
```./updatechannel.tx``` 파일 내에 정의된 ```channel update``` 트랜잭션을 사인한다. ```./updatechannel.tx``` 파일의
크기는 configuration transaction에 성공적으로 사인 후에 변경된다. 

```shell
~$peer channel signconfigtx -f updatechannel.tx
```

## peer version 명령어 (피어 버전)
```peer version``` 명령어는 피어의 버전 정보를 디스플레이한다. 결과로 버전, Commit SHA, GO 버전, OS/아키텍처, 
체인코드 정보를 보여준다. 

```shell
~$peer version [flags]
```
```peer version``` 명령어 실행 결과의 예는 다음과 같다.

```shell
 peer:
   Version: 1.4.0
   Commit SHA: 0efc897
   Go version: go1.12.12
   OS/Arch: linux/amd64
   Chaincode:
    Base Image Version: 0.4.14
    Base Docker Namespace: hyperledger
    Base Docker Label: org.hyperledger.fabric
    Docker Namespace: hyperledger
```


## ```peer chaincode``` 명령어
```peer chaincode``` 명령어는 관리자가 체인코드 설치, 인스턴스화, 호출, 패키징, 질의, 업그레이드 등과 같은 피어와 관련한 체인코드를 실행할 수 있도록 한다.
```peer chaincode``` 명령어는 다음과 같은 ```option```을 가진다.

#### Syntax
```peer chaincode``` 하위  명령의 구문은 다음과 같다.

```shell
~$peer chaincode [options] [flags]
```
```options```에 해당하는 명령어는 다음과 같다. 

* ```install```: 피어의 파일시스템에 체인코드를 설치
* ```instantiate```: 피어가 속한 채널에서 체인코드를 인스턴스화 
* ```invoke```: 제공된 인수를 사용하여 피어에서 체인코드 기능을 호출, CLI는 거래 제안서를 피어에게
전송하여 체인코드를 호출한다. 피어는 체인코드를 실행하고 승인된 제안 응답(또는 오류)을 CLI에 전송한다.
승인된 제안응답을 받으면 CLI는 트랜잭션을 구성하여 orderer에게 보낸다. 
* ```list```: 피어에 설치된 체인코드를 나열하거나 피어가 속한 채널에서 인스턴스화된 체인코드를 나열할 수 있음
* ```package```: 체인코드 설치를 수행하는데 필요한 자료를 패키징할 수 있다. 그러므로 동일한 체인코드 패키지를 여러 피어에
일관되게 설치할 수 있다.                                                                           
* ```query```: 체인코드의 invoke 메소드를 호출하여 체인코드를 질의할 수 가능하다. query와 invoke 하위 명령의 차이점은
성공한 응답의 경우 invoke는 orderer에게 트랜잭션을 제출하도록 진행하고 query는 성공 또는 기타 응답을 표준 출력으로 출력한다.
* ```signpackage```: ```peer chaincode package``` 명령으로 작성된 체인코드 패키지에 서명을 추가한다.
* ```upgrade```: 채널에서 인스턴스화된 체인코드를 최신 버전으로 업그레이드 할 수 있다.








## References

[Hyperledger(ver.1.4) Commands Reference](https://hyperledger-fabric.readthedocs.io/en/release-1.4/command_ref.html)
