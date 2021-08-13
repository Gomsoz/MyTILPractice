# Properties

CountOfPlayers
-----
- 접속한 인원 수

CountOfRooms
-----
- 방 개수

CountOfPlayersInRooms
-----
- 모든 방에 있는 인원 수

InLobby
-----
- 플레이어가 방에 있는지 체크

IsConnected
-----
- 플레이어가 서버에 연결되어 있는지 체크

Player[] PlayerList
-----
- 현재 방에 있는 플레이어의 리스트를 반환한다.

# Function

ConnectUsingSetting
-----
- Photon 서버와 연결


CreateRoom(string roomName, RoomOptions roomOptions = null, TypedLobby typedLobby = null, string[] expectedUsers = null)
-----
- 방 만들기
  - roomName : 방 이름은 중복이 안되어야 하며, Null 이거나, "" 일 경우 자동으로 이름을 생성한다.
  - roomOptions : 최대 인원을 설정한다던지와 같은 방의 옵션을 정의한다.
  - typedLobby : null 일 경우 현재 로비에 방을 생성한다.
- 방이 성공적으로 만들어지면 OnCreatedRoom(), OnJoinedRoom() 을 호출한다.

### → RoomOptions

JoinRoom(string roomName)
-----
- 방 이름을 통해 방에 참가한다.

JoinOrCreateRoom(string roomName, RoomOptions roomOptions = null, TypedLobby typedLobby = null, string[] expectedUsers = null)
-----
- 방 이름이 없으면 생성하고, 있다면 참가한다.

JoinRandomRoom()
-----
- 랜덤한 방에 입장한다.

LeaveRoom()
-----
- 방을 떠난다.

JoinLobby
-----
- 로비에 접속한다.


# Callback Function

OnConnectedToMaster()
-----
- 서버에 성공적으로 접속했을 때 호출

OnDisconnected(DisconnectCause cause)
-----
- 서버와 연결이 끊겼을 때 호출

### → enum DisconnectCause

OnJoinLobby()
-----
- 로비에 성공적으로 들어갔을 때 호출

OnCreatedRoom()
-----

OnJoinedRoom()
-----

virtual OnCreateRoomFailed(short returnCode, string message)
-----
- 방 만들기를 실패했을 때 호출

virtual OnJoinRoomFailed(short returnCode, string message)
-----
- 방 접속이 실패했을 때 호출

virtual OnJoinRandomFailed(short returnCode, string message)
- 방 랜덤 참가에 실패했을 때 호출

OnPlayerEnterRoom(Player newPlayer)
- 플레이어가 방에 들어왔을 때 호출
