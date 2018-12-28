# 블록체인기반 음원 스트리밍 서비스  
CTS2018 team4 EOS dapp  
EOS : dawn 4.2  
eosjs : 13.0.0  
scatter : 4.0.3  

### EOS 블록체인, 웹, scatter(chrome extension) 을 이용한 음원 스트리밍 서비스  
### Architecture  
![](https://github.com/ene5135/EOSdapp_mEOSic_2018_Spring_prj/blob/master/architecture.jpg)  
### 홈 화면  
![](https://github.com/ene5135/EOSdapp_mEOSic_2018_Spring_prj/blob/master/home.jpg)  
### Scatter 사용  
![](https://github.com/ene5135/EOSdapp_mEOSic_2018_Spring_prj/blob/master/scatter.jpg)  
### Upload 화면  
![](https://github.com/ene5135/EOSdapp_mEOSic_2018_Spring_prj/blob/master/upload.jpg)  
### Search 화면  
![](https://github.com/ene5135/EOSdapp_mEOSic_2018_Spring_prj/blob/master/search.jpg)  

더 자세한 사항은 [보고서](https://github.com/ene5135/eosdapp/blob/master/final_report.pdf)를 참고하세요.

### 작동법 (Local network, Local blockchain)  
1. EOS 빌드 및 nodeos 구동 : EOS 튜토리얼 참고 (빌드 후 build 폴더에서 sudo make install 까지 해줘야함)  
1-1. nodeos config 설정 : 주석처리되어있는 Allow-access-Origin 옵션 값 *로 변경
2. 프론트 서버 구동 : frontend/music_web 폴더에서 npm install 후 npm start
3. 크롬 extension Scatter 설치
4. scatter에 네트워크 등록 : 프론트 서버 구동 후 켜진 localhost:3000 페이지에서 add network 누르고 켜진 창에서 accept
5. scatter에 키페어 등록 : cloes로 키페어 하나 생성 후 scatter -> key pairs -> new 해서 등록
6. 어카운트 생성 : localhost:3000 페이지에서 account name : music, public key : 위에서 생성한 public key 로 하여 생성
7. identity 등록 : scatter -> identity -> new -> 127.0.0.1:8888 네트워크 선택, 아까 등록한 키페어 선택, import 하고 music account 선택(@Active) -> save
8. smart contract 등록 : 터미널에서 cleos set contract music [wast와 abi가 있는 폴더 경로] music.wast music.abi
9. 웹페이지에서 파일 업로드 및 검색 해보기
