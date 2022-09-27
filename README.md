# API LIST - 09.27

IP : 43.200.120.78, Port : 8080

1. /oauth/*
    - POST
    - 각 SNS 토큰을 헤더에 추가해서 요청
    - return
    
    ```json
    {
        "accessToken": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJrYWthbyIsImlzcyI6IjIzNjIwOTI3MzgiLCJpYXQiOjE2NjIwMjU3NzEsImV4cCI6MTY2MjA2ODk3MX0.etY-Xa0KG6wBVcBtiME_wWJIqLjOMouwZ-dfu_dhJoA",
        "refreshToken": "eyJhbGciOiJIUzI1NiJ9.eyJpYXQiOjE2NjIwMjU3NzEsImV4cCI6MTY2NzIwOTc3MX0.EY4kpGnV8iKtFTyQDZygDXDACLymjR97bxaH1p8WUHY"
    }
    ```
    
2. /
    - GET
    - return
    
    ```json
    {
        "response": "Server Running!!"
    }
    ```
    
3. /users
    - GET
    - DB에 저장되어 있는 유저 정보 전부 반환
    - return - register 하기 전
    
    ```json
    [
        {
            "id": 1,
            "username": "V3JM4GTY8RkyqSgYjeAYkJQTDWMXgUmii992pnQKQ90",
            "provider": "naver",
            "nickname": null,
            "gender": null,
            "height": null,
            "weight": null,
            "bodyFatPer": null,
            "musclePer": null,
            "refreshToken": "eyJhbGciOiJIUzI1NiJ9.eyJpYXQiOjE2NjIwMDYyMTEsImV4cCI6MTY2NzE5MDIxMX0.juAyTlRV1tcVXOGRiXIzRgzTch5VpjaMpYQr-kM__t0",
            "newbie": false
        },
        {
            "id": 2,
            "username": "2362092738",
            "provider": "kakao",
            "nickname": null,
            "gender": null,
            "height": null,
            "weight": null,
            "bodyFatPer": null,
            "musclePer": null,
            "refreshToken": "eyJhbGciOiJIUzI1NiJ9.eyJpYXQiOjE2NjIwMDY0MDcsImV4cCI6MTY2NzE5MDQwN30.T_jiXxBLSLBWElqg_uLjwGiKTrMD1TmQyaC7Rikmf8Q",
            "newbie": false
        },
        {
            "id": 3,
            "username": "116192766613493245373",
            "provider": "google",
            "nickname": null,
            "gender": null,
            "height": null,
            "weight": null,
            "bodyFatPer": null,
            "musclePer": null,
            "refreshToken": "eyJhbGciOiJIUzI1NiJ9.eyJpYXQiOjE2NjIwMDYyMjUsImV4cCI6MTY2NzE5MDIyNX0.nd5q6gjWQSLtzKgjqSgkXYiWajzv-IR1toIC8lRrsxs",
            "newbie": false
        }
    ]
    ```
    
4. /user?nickname=cat
    - GET
    - request param “nickname”
    - return
    
    ```json
    {
        "nickname": "cat",
        "gender": "female",
        "height": 170.0,
        "weight": 60.0,
        "bodyFatPer": 0.05,
        "musclePer": 95.5,
        "newbie": false
    }
    ```
    
5. /user/refreshToken?refreshToken=””
    - GET
    - request param “refreshToken”
    - return
    
    ```json
    {
        "nickname": "cat",
        "gender": "female",
        "height": 170.0,
        "weight": 60.0,
        "bodyFatPer": 0.05,
        "musclePer": 95.5,
        "newbie": false
    }
    ```
    
6. /register
    - POST
    - DB에 유저 객체 저장
    - return
    
    ```json
    {
        "response": "User Registered!!"
    }
    ```
    
    - requset body
    
    ```json
    {
    	"nickname":"cat",
    	"isNewbie":"true",
    	"gender":"female",
    	"height":170.0,
    	"weight":60.0,
    	"bodyFatPer":0.05,
    	"musclePer":95.5
    }
    ```
    
7. /session
    - GET
    - SecurityContextHolder의 context 반환 - Json 아님 테스트용
    
    ```json
    {"authorities":[],"details":null,"authenticated":true,"principal":{"provider":"kakao","username":"2362092738","authorities":null,"locked":false,"enabled":true,"expired":false},"credential":null,"credentials":null,"name":"Alpha.alphaspring.DTO.UserDetails@5f18853"}
    ```
    
8. /routine
    - POST
    - DB에 Routine 저장
    - return
    
    ```json
    {
        "response": "Routine Registered!!"
    }
    ```
    
    - request
    
    ```json
    {
            "name": "3 days a week",
    				"isRecommended":"true",
    				"description":"for newbie"
    }
    ```
    
9. /subRoutine
    - POST
    - DB에 SubRoutine 저장
    - 해당 user에 저장되어있는 routineName을 넣어줘야함
    - return
    
    ```json
    {
        "response": "SubRoutine Registered!!"
    }
    ```
    
    - request
    
    ```json
    {
            "routineId":1,
            "subRoutineName":"first day"
    }
    ```
    
10. /routines
    - GET
    - DB에서 모든 Routine들 반환
    - 해당 사용자의 Routine들만 반환
    - return
    
    ```json
    [
        {
            "username": "dragon",
            "routineName": "3 days a week",
            "routineId": 1,
    				"description":"for newbie"
        }
    ]
    ```
    
11. /subRoutines
    - GET
    - DB에서 모든 SubRoutine들 반환
    - 해당 사용자의 SubRoutine들만 반환
    - return
    
    ```json
    [
        {
            "routineName": "3 days a week",
            "subRoutineId": 1,
            "subRoutineName": "first day"
        },
        {
            "routineName": "3 days a week",
            "subRoutineId": 3,
            "subRoutineName": "Second day"
        }
    ]
    ```
    
12. /subRoutine?routineId={param}
    - GET
    - DB에서 해당 아이디를 가진 루틴의 서브루틴들을 전부 반환
    - 해당 사용자의 SubRoutine들만 반환
    - return
    
    ```json
    [
        {
            "routineName": "3 days a week",
            "subRoutineId": 1,
            "subRoutineName": "first day"
        },
        {
            "routineName": "3 days a week",
            "subRoutineId": 3,
            "subRoutineName": "Second day"
        }
    ]
    ```
    
13. /routines/recommended
    - GET
    - DB에서 추천 루틴을 전부 반환
    - return
    
    ```json
    [
        {
            "username": "dragon",
            "routineName": "3 days a week",
            "routineId": 1,
    				"description":"for newbie"
        }
    ]
    ```
    
14. /refresh
    - POST
    - accessToken refresh
    - return
    
    ```json
    {
        "accessToken": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiIyMzYyMDkyNzM4IiwiaXNzIjoia2FrYW8iLCJpYXQiOjE2NjIyOTkxNDEsImV4cCI6MTY2MjM0MjM0MX0.rvfcjwCeH_SFaOLh3nzMoFtOPlkOV2-PQBvH7_wQKKw",
        "refreshToken": "eyJhbGciOiJIUzI1NiJ9.eyJpYXQiOjE2NjIyOTkxNDEsImV4cCI6MTY2NzQ4MzE0MX0.Zcz7fRAbNryUhylUaNv5NlceEewQFzIm1eKoSWtrCOA"
    }
    ```
    
    - request(body)
    
    ```json
    {
        "refreshToken":"eyJhbGciOiJIUzI1NiJ9.eyJpYXQiOjE2NjIyOTkxMzIsImV4cCI6MTY2NzQ4MzEzMn0.59KpNqz7owpNraZvrKMcmE80jmBUnyIUxfBWwP2uwck"
    }
    ```
    
15. /workouts
    - GET
    - DB에서 운동들을 전부 반환
    - return
    
    ```json
    [
        {
            "id": 1,
            "name": "bench press",
            "machineName": "flat bench",
            "bodyPart": "chest"
        },
        {
            "id": 3,
            "name": "military press",
            "machineName": "power rack",
            "bodyPart": "shoulder"
        }
    ]
    ```
    
16. /workout
    - POST
    - DB에 운동을 저장
    - return
    
    ```json
    {
        "response": "WorkOut registered!!"
    }
    ```
    
    - request
    
    ```json
    {
        "name": "bench press",
    		"machineName": "flat bench",
    		"bodyPart": "chest"
    }
    ```
    
17. /workout/bodypart?bodyPart={param}
    - GET
    - request param “bodyPart”
    - return
    
    ```json
    [
        {
            "id": 1,
            "name": "bench press",
            "machineName": "flat bench",
            "bodyPart": "chest"
        }
    ]
    ```
    
18. /workout/machine?machine={param}
    - GET
    - request param “machine”
    - return
    
    ```json
    [
        {
            "id": 1,
            "name": "bench press",
            "machineName": "flat bench",
            "bodyPart": "chest"
        }
    ]
    ```
    
19. /workSets?subRoutineId=1
    - GET
    - request param “subRoutineId”
    - return
    
    ```json
    [
        {
            "workSetId": 1,
            "subRoutineName": "first day",
            "workOutName": "military press"
        }
    ]
    ```
    
20. /workSet
    - POST
    - DB에 workSet 저장
    - return
    
    ```json
    {
        "response": "WorkSet registered"
    }
    ```
    
    - request
    
    ```json
    {
        "workOutName": "military press",
    	  "subRoutineId": "1"
    }
    ```
    
21. /subSets?workSetId=1
    - GET
    - request param “workSetId”
    - return
    
    ```json
    [
        {
            "subSetId": 1,
            "workSetId": 1,
            "setNo": 1,
            "count": 10,
            "weight": 100
        },
        {
            "subSetId": 2,
            "workSetId": 1,
            "setNo": 2,
            "count": 10,
            "weight": 110
        }
    ]
    ```
    
22. /subSet
    - POST
    - DB에 subSet 저장
    - return
    
    ```json
    {
        "response": "SubSet registered"
    }
    ```
    
    - request
    
    ```json
    {
        "workSetId": 1,
    		"setNo": 2,
        "count": 10,
        "weight": 110
    }
    ```