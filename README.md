flowchart TB
    subgraph 科室职责
        neu[神经内科]:::neuro
        rad[放射科]:::radio
        lab[检验科]:::lab
        sur[神经外科]:::surgery
        hem[血液科]:::hemato
        path[病理科]:::patho
    end

    %% 初筛阶段
    neu --> a1[病史采集+神经系统查体]
    neu --> a2[开具MRI检查] --> rad
    neu --> a3[开具血液/脑脊液检查] --> lab

    %% 多模态评估
    rad --> b1[高分辨率MRI\nT2/FLAIR/DWI]
    rad --> b2[脊髓成像+增强扫描]
    lab --> b3[AQP4-IgG/MOG-IgG检测]
    lab --> b4[寡克隆带/IgG指数]
    sur --> b5[手术/活检评估]

    %% MDT会诊
    neu & rad & lab & sur --> c1[[MDT会诊]]:::mdt
    c1 --> c2[整合数据]
    c2 --> c3{鉴别诊断：\nMS/NMOSD/ADEM/肿瘤}

    %% 分型治疗
    c3 -->|急性期| d1[激素冲击/血浆置换] --> neu
    c3 -->|缓解期| d2[免疫抑制剂/单抗类] --> neu
    c3 -->|特殊病例| d3[干细胞移植评估] --> hem

    %% 动态监测
    rad --> e1[影像随访\n每6-12个月]
    lab --> e2[药物副作用监测]
    path --> e3[非典型病例再评估]

    %% 康复随访
    neu --> f1[神经功能康复]
    neu --> f2[认知/心理干预]
    neu --> f3[患者教育+复发预警]

    classDef neuro fill:#FFF2CC,stroke:#F1C40F;
    classDef radio fill:#DAE8FC,stroke:#3498DB;
    classDef lab fill:#D5E8D4,stroke:#2E8B57;
    classDef surgery fill:#E1D5E7,stroke:#9B59B6;
    classDef hemato fill:#F8CECC,stroke:#E74C3C;
    classDef patho fill:#F5D5A0,stroke:#D35400;
    classDef mdt fill:#FFD700,stroke:#FF8C00;
