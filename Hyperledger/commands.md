# Commands in Hyperledger

## commands related peer (피어와 관련한 명령어)

```peer```관련 명령어는 다섯 영역의 명령어군으로 구성되며 이 명령어를 통해 관리자는 피어와 관련한 작업을 수행할 수 있다. 
```peer``` 관련 명령어의 다섯 영역은 다음과 같다. 명령ㅇ

```shell
~$peer chaincode [option] [flags]   // 스마트 컨트렉트 관련 명령어
~$peer channel   [option] [flags]   // 채널 관련 명령어 
~$peer logging   [option] [flags]   // 피어의 로그 레벨을 동적으로 설정하고 볼 수 있는 명령어 
~$peer node      [option] [flags]   // 피어 노드와 관련한 명령어
~$peer version   [option] [flags]   // 피어의 버전 등의 정보를 디스플레이하는 명령어 
```
f

`### ``peer channel``` 관련 명령어

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

##### ```create```` option 예제

```shell
~$peer channel create -c mychannel -f ./createchannel.tx --orderer orderer.example.com:7050
```

블록체인 네트워크에 대해 ```orderer.example.com:7050```의 order를 이용하여 ```mychannel```이라는 새로운 채널을 생성한다.
```./createchannel.tx```파일에는 채널을 생성하는데 요구되는 **configuration update transaction** 이 정의된다.

##### ```join```` option 예제

```shell
$peer channel join -b ./mychannel.genesis.block
```
```./mychannel.genesis.block``` 파일로 식별되는 제네시스 블록내에 정의된 채널에 피어를 조인한다. 






## References

[Hyperledger(ver.1.4) Commands Reference](https://hyperledger-fabric.readthedocs.io/en/release-1.4/command_ref.html)
