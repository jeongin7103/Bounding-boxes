# Bounding-boxes
Codes for convert the coordinates of bounding box

## 디렉토리 구조
```
📦 Desktop
├─ 망고
│  ├─ images
│  └─ labels
└─ 멜론
   ├─ images
   └─ labels
```
images 와 labels 에는 jpg, json 파일이 500개씩 들어있습니다.

기존 json 파일에 들어있는 좌표는 `W, H, x_min, y_min` 값이 상대좌표로 들어있었습니다. 

예시:

`"W": "0.578867"`,
`"H": "0.816689"`,
`"Point(x,y)": "0.490215,0.581089"`

![image](https://github.com/jeongin7103/Bounding-boxes/assets/127823391/aae6d2aa-ea12-47ad-8a39-192e657d0469)


상대좌표는 fractional form 이라고도 하는데, 일반적으로 `(x_min, y_min, width, height)` 형식으로 표현됩니다. 

여기서 `x_min`, `y_min`은 bounding box의 상단 왼쪽 모서리의 상대적인 위치를 나타내고, 

`width`와 `height`는 bounding box의 상대적인 너비와 높이를 나타냅니다. 

상대적인 너비/높이란 전체 이미지 중 bounding box가 차지하는 비율을 말합니다. 

그렇기 때문에 상대 위치인 `x_min`, `y_min` 또한 상단 왼쪽 모서리를 `(0,0)`, 하단 오른쪽 모서리를 `(1,1)`로 지정하고 비율을 계산한 값입니다.

하단 오른쪽 좌표인 `x_max`, `y_max`는 각각 `x_min` 값에 `width`, `y_min` 값에 `height`를 더한것 입니다.
