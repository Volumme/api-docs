# API LIST - 12.13

IP : 13.124.123.95, Port : 8080

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
            "username": "2362092738",
            "provider": "kakao",
            "nickname": "dragon",
            "gender": "male",
            "height": 183.0,
            "weight": 75.0,
            "bodyFatPer": 0.0,
            "musclePer": 100.0,
            "refreshToken": "eyJhbGciOiJIUzI1NiJ9.eyJpYXQiOjE2Njk3OTAwNTMsImV4cCI6MTY3NDk3NDA1M30.tZc2MKFc0Lk_UvNFXuHnWzW8zh1NORJzhq-ryBLlf2U",
            "newbie": false
        },
        {
            "id": 2,
            "username": "2434926300",
            "provider": "kakao",
            "nickname": null,
            "gender": "male",
            "height": 177.2,
            "weight": 87.2,
            "bodyFatPer": 18.0,
            "musclePer": 40.3,
            "refreshToken": "eyJhbGciOiJIUzI1NiJ9.eyJpYXQiOjE2NjkxMzE1NzYsImV4cCI6MTY3NDMxNTU3Nn0.CGlVi4XtpGAcKPI7XxUySNEeYbhfw08fodjJsb0ng8M",
            "newbie": false
        },
        {
            "id": 3,
            "username": "2387972969",
            "provider": "kakao",
            "nickname": "JefferyKakao",
            "gender": "female",
            "height": 0.0,
            "weight": 0.0,
            "bodyFatPer": 0.0,
            "musclePer": 0.0,
            "refreshToken": "eyJhbGciOiJIUzI1NiJ9.eyJpYXQiOjE2NzAwOTIxMzQsImV4cCI6MTY3NTI3NjEzNH0.98X3h8LBRvgjEy4SHBqVxtyTT7cAzT0_OpAyf7uwskc",
            "newbie": false
        },
        {
            "id": 4,
            "username": "2411221773",
            "provider": "kakao",
            "nickname": "",
            "gender": "female",
            "height": 0.0,
            "weight": 0.5,
            "bodyFatPer": 0.0,
            "musclePer": 0.0,
            "refreshToken": "eyJhbGciOiJIUzI1NiJ9.eyJpYXQiOjE2NzA5MDM1OTEsImV4cCI6MTY3NjA4NzU5MX0.Jorj64HScp1RXIdGBu5kRXO50435TElMSHuaiax80m8",
            "newbie": false
        },
        {
            "id": 5,
            "username": "2560502589",
            "provider": "kakao",
            "nickname": null,
            "gender": null,
            "height": null,
            "weight": null,
            "bodyFatPer": null,
            "musclePer": null,
            "refreshToken": "eyJhbGciOiJIUzI1NiJ9.eyJpYXQiOjE2NzA4NjkzOTQsImV4cCI6MTY3NjA1MzM5NH0.hdMPMKJSRt3Xm199LxMjh1WhSFWAQmDDC8KUHpQFwro",
            "newbie": false
        },
        {
            "id": 6,
            "username": "CsNtIcUqFaPNFlvmjBTkG-Z9bW-qMIQMEiIAOgvK5IM",
            "provider": "naver",
            "nickname": null,
            "gender": null,
            "height": null,
            "weight": null,
            "bodyFatPer": null,
            "musclePer": null,
            "refreshToken": "eyJhbGciOiJIUzI1NiJ9.eyJpYXQiOjE2NzA4NjQ3NTIsImV4cCI6MTY3NjA0ODc1Mn0.nEMTn8yCkp3REPrAewAR5yiQmnvlqmeZvhCkuALmZCA",
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
        "response": "User Registered!!"
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
        "id": 47
    }
    ```
    
    - request
    
    ```json
    {
            "name": "6 days a week",
    				"isRecommended":"true",
    				"description":"for test2",
            "category":"test"
        }
    ```
    
9. /subRoutine
    - POST
    - DB에 SubRoutine 저장
    - 해당 user에 저장되어있는 routineName을 넣어줘야함
    - return
    
    ```json
    {
        "id": 68
    }
    ```
    
    - request
    
    ```json
    {
            "routineId":8,
            "subRoutineName":"day 5"
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
            "username": "Uu",
            "routineName": "3 days a week routine for newbie",
            "routineId": 8,
            "description": null,
            "category": null
        },
        {
            "username": "Uu",
            "routineName": "4 days a week routine for newbie",
            "routineId": 9,
            "description": null,
            "category": null
        },
        {
            "username": "Uu",
            "routineName": "5 days a week routine for newbie",
            "routineId": 10,
            "description": null,
            "category": null
        },
        {
            "username": "Uu",
            "routineName": "testroutine",
            "routineId": 11,
            "description": "for newbie",
            "category": null
        }
    ]
    ```
    
11. /subroutines?routineId=8
    - return
    
    ```jsx
    [
        {
            "routineName": "3 days a week routine for newbie",
            "subRoutineId": 65,
            "subRoutineName": "day 1"
        },
        {
            "routineName": "3 days a week routine for newbie",
            "subRoutineId": 66,
            "subRoutineName": "day 2"
        },
        {
            "routineName": "3 days a week routine for newbie",
            "subRoutineId": 67,
            "subRoutineName": "day 3"
        }
    ]
    ```
    
12. /subSets?workSetId=worksetid
    - GET
    - return
    
    ```json
    [
        {
            "subSetId": 1,
            "workSetId": 1,
            "setNo": 2,
            "count": 10,
            "weight": 110
        },
        {
            "subSetId": 2,
            "workSetId": 1,
            "setNo": 1,
            "count": 10,
            "weight": 100
        }
    ]
    ```
    
13. /subSet
    - POST
    - request
    
    ```jsx
    {
        "workSetId": 66,
    		"setNo": 1,
        "count": 10,
        "weight": 100
    }
    ```
    
    - return
    
    ```json
    {
        "id": 7
    }
    ```
    
14. /subRoutine?routineId={param}
    - GET
    - DB에서 해당 아이디를 가진 루틴의 서브루틴들을 전부 반환
    - 해당 사용자의 SubRoutine들만 반환
    - return
    
    ```json
    [
        {
            "routineName": "3 days a week routine for newbie",
            "subRoutineId": 65,
            "subRoutineName": "day 1"
        },
        {
            "routineName": "3 days a week routine for newbie",
            "subRoutineId": 66,
            "subRoutineName": "day 2"
        },
        {
            "routineName": "3 days a week routine for newbie",
            "subRoutineId": 67,
            "subRoutineName": "day 3"
        },
        {
            "routineName": "3 days a week routine for newbie",
            "subRoutineId": 68,
            "subRoutineName": "day 5"
        }
    ]
    ```
    
15. /routines/recommended
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
    
    /
    
16. /routines/description?description={description}
    - GET
    - DB에서 desciption 검색 반환
    - return
    
    ```json
    [
        {
            "username": null,
            "routineName": "3 days a week",
            "routineId": 1,
            "description": "for newbie",
            "category": null
        },
        {
            "username": null,
            "routineName": "3 days a week",
            "routineId": 2,
            "description": "for newbie",
            "category": null
        },
        {
            "username": null,
            "routineName": "3 days a week",
            "routineId": 3,
            "description": "for newbie",
            "category": null
        },
        {
            "username": "JefferyKakao",
            "routineName": "testroutine",
            "routineId": 4,
            "description": "for newbie",
            "category": null
        },
        {
            "username": "JefferyKakao",
            "routineName": "testroutine",
            "routineId": 5,
            "description": "for newbie",
            "category": null
        }
    ]
    ```
    
17. /routines/category?category={category}
    - GET
    - DB에서 카테고리 검색 반환
    - return
    
    ```json
    [
        {
            "username": null,
            "routineName": "3 days a week",
            "routineId": 1,
            "description": "for newbie",
            "category": null
        },
        {
            "username": null,
            "routineName": "3 days a week",
            "routineId": 2,
            "description": "for newbie",
            "category": null
        },
        {
            "username": null,
            "routineName": "3 days a week",
            "routineId": 3,
            "description": "for newbie",
            "category": null
        },
        {
            "username": "JefferyKakao",
            "routineName": "testroutine",
            "routineId": 4,
            "description": "for newbie",
            "category": null
        },
        {
            "username": "JefferyKakao",
            "routineName": "testroutine",
            "routineId": 5,
            "description": "for newbie",
            "category": null
        },
        {
            "username": "JefferyKakao",
            "routineName": "testroutine",
            "routineId": 6,
            "description": "for newbie",
            "category": null
        }
    ]
    ```
    
18. /refresh
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
        
19. /workouts
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
    
20. /workout
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
    
21. /workout/bodypart?bodyPart={param}
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
    
22. /workout/machine?machine={param}
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
    
23. /workSets?subRoutineId=1
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
    
24. /workSet
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
    
25. /subSets?workSetId=1
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
    
26. /subSet
    - POST
    - DB에 subSet 저장
    - return
    
    ```json
    {
        "id": 1
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
    
27. /statics?name={param}
    - GET
    - request param “workSetId”
    - 파일을 반환
28. /statics
    - POST
    - 정적 데이터 업로드 API
    - json이 아닌 form-data로 보내야 함
    - request body(form-data)
    
    ![Untitled](API%20LIST%20-%2012%2013%200522786b03964e148f64a757c4562754/Untitled.png)
    
    - return
    
    ```json
    {
        "id": "efc634a6-3dc1-4c3d-bac8-b2d9c3b6c369",
        "name": "swift.png",
        "format": "png",
        "path": "images/efc634a6-3dc1-4c3d-bac8-b2d9c3b6c369.png",
        "bytes": 14925,
        "createdAt": "2022-10-02T08:31:30.515821781"
    }
    ```
    
29. /ai/count
    - 모델에 값을 넣고 횟수 측정
    - request
    
    ```jsx
    { 
        "data" : [[0,0,0,0],[1,0,1,0],[2,0,2,0],[3,0,3,0],[4,0,3,0],[5,0,2,0],[6,0,1,0],[7,0,0,0],[8,0,0,0],[9,0,0,0]],
        "startTime" : 202211171102,
        "workOut" : "benchPress"
    }
    ```
    
    - response
    
    ```jsx
    {data=0}
    ```
    
30. /subRoutines/all?subRoutineId=1
    - subRoutineId를 보내면 그 안에 있는 운동 세트들 전부 반환
    - response
    
    ```jsx
    [
        {
            "workOut": "pull up",
            "subSets": [
                {
                    "subSetId": 1,
                    "workSetId": 1,
                    "setNo": 2,
                    "count": 10,
                    "weight": 110
                },
                {
                    "subSetId": 2,
                    "workSetId": 1,
                    "setNo": 1,
                    "count": 10,
                    "weight": 100
                }
            ]
        }
    ]
    ```