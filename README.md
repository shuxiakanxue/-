# -graph LR
    subgraph 参与科室
    N[神经内科]:::neuro
    R[放射科]:::radio
    L[检验科]:::lab
    S[神经外科]:::surgery
    H[血液科]:::hemato
    P[病理科]:::patho
    end

    %% 初筛阶段
    N --> A1[病史采集+神经系统查体]:::step
    N --> A2[开具MRI检查]:::step
    A2 -.-> R
    N --> A3[开具血液/脑脊液检查]:::step
    A3 -.-> L

    %% 多模态评估
    R --> B1[高分辨率MRI<br>(T2/FLAIR/DWI)]:::step
    R --> B2[脊髓成像+增强扫描]:::step
    L --> B3[AQP4-IgG/MOG-IgG检测]:::step
    L --> B4[寡克隆带/IgG指数]:::step
    S --> B5[手术/活检评估]:::step

    %% MDT会诊
    N & R & L & S --> C1[整合临床-影像-实验室数据]:::critical
    C1 --> C2[鉴别诊断：<br>MS/NMOSD/ADEM/肿瘤]:::critical
    C2 --> C3[制定个体化方案]:::critical

    %% 分型治疗
    C3 --> D1{治疗分型}:::decision
    D1 -->|急性期| D2[激素冲击/血浆置换]:::step
    D1 -->|缓解期| D3[免疫抑制剂/单抗类]:::step
    D1 -->|特殊病例| D4[干细胞移植评估]:::step
    D4 -.-> H

    %% 动态监测
    R --> E1[每6-12个月影像随访]:::monitor
    L --> E2[血常规/肝肾功能监测]:::monitor
    P --> E3[非典型病例再评估]:::monitor

    %% 康复随访
    N --> F1[神经功能康复]:::followup
    N --> F2[认知/心理干预]:::followup
    N --> F3[患者教育+复发预警]:::followup

    classDef neuro fill:#F9E79F,stroke:#F1C40F;
    classDef radio fill:#AED6F1,stroke:#3498DB;
    classDef lab fill:#A2D9CE,stroke:#1ABC9C;
    classDef surgery fill:#D2B4DE,stroke:#9B59B6;
    classDef hemato fill:#F5B7B1,stroke:#E74C3C;
    classDef patho fill:#E59866,stroke:#D35400;
    classDef step fill:#FFFFFF,stroke:#333,stroke-width:1px;
    classDef critical fill:#FFD700,stroke:#FF8C00;
    classDef decision fill:#FFA07A,stroke:#CD5C5C,stroke-dasharray:5;
    classDef monitor fill:#98FB98,stroke:#2E8B57;
    classDef followup fill:#DDA0DD,stroke:#9932CC;
