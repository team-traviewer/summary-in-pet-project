# summary-in-pet-project

```mermaid
graph LR
    %% ====== CLUSTERS ======
    subgraph A["👥 사용자 관리"]
        U[("users<br><small>유저 정보</small>")]
        R[("roles<br><small>권한 목록</small>")]
        UR[("user_roles<br><small>유저-권한 매핑</small>")]
    end

    subgraph B["🏠 보호소 및 동물"]
        S[("shelters<br><small>보호소</small>")]
        A1[("animals<br><small>보호 중인 동물</small>")]
    end

    subgraph C["📋 기록 관리"]
        I[("intake_records<br><small>입소/구조 기록</small>")]
        M[("medical_records<br><small>의료 기록</small>")]
        F[("foster_care<br><small>임시보호 관리</small>")]
    end

    subgraph D["💌 입양 절차"]
        AP[("adoption_applications<br><small>입양 신청</small>")]
        AD[("adoptions<br><small>입양 계약</small>")]
    end

    %% ====== RELATIONSHIPS ======

    %% USERS
    U --> UR
    R --> UR

    %% SHELTER & ANIMALS
    S --> A1

    %% RECORDS
    A1 --> I
    A1 --> M
    A1 --> F
    U --> F

    %% ADOPTION FLOW
    A1 --> AP
    U --> AP
    AP --> AD
    U --> AD
    A1 --> AD

    %% ====== STYLES ======
    classDef entity fill:#fdf6e3,stroke:#b58900,stroke-width:1px,color:#333,border-radius:10px;
    classDef cluster fill:#fdfdfd,stroke:#d0d0d0,stroke-width:1px,color:#555,font-weight:bold;
    class U,R,UR,S,A1,I,M,F,AP,AD entity;


