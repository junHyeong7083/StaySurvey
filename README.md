# StaySurvay
AI 기반 청년 정신건강 앱 클라이언트 개발


### 프로젝트 흐름 ###
1. 시작화면에서 이름 입력 -> DB테이블 생성
2. 10가지 질문표시
  - 각 질문마다 [녹음하기] 버튼 클릭
  - Whisper STT로 음성을 텍스트 변환
  - 변환된 텍스트를 DB 'Index'에 저장
3. 모든 질문 완료 시 -> 결과 저장 및 출력(고민중)


## 아키텍처 다이어그램
```mermaid
%%{init: {"theme": "default", "themeVariables": { "background":"transparent"}}}%%
flowchart TD
    A([Start Title])
    B[[이름 입력]]
    C[(DB 테이블 생성)]
    D{{질문 1 ~ 10 표시}}
    E([녹음하기 버튼])
    F([Whisper STT 변환])
    G[[텍스트 변환 결과]]
    H[(DB 저장: Index 1~10)]
    I{{모든 질문 완료}}
    J([결과 저장/출력])

    A --> B --> C --> D --> E --> F --> G --> H --> I --> J

    %% 스타일
    classDef io fill:#eef,stroke:#669,stroke-width:2px,rx:10;
    classDef process fill:#efe,stroke:#6a6,stroke-width:2px,rx:10;
    classDef db fill:#fff3cd,stroke:#c99,stroke-width:2px,rx:8;

    class A,B,E,F,G,J io;
    class D,I process;
    class C,H db;
