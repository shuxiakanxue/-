%%{init: {'theme': 'base', 'themeVariables': { 'primaryColor': '#dbeafe', 'edgeLabelBackground':'#ffffff', 'tertiaryColor': '#f0f9ff' }}}%%
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

    subgraph 神经内科
        A1[初筛阶段\n- 病史采集\n- 查体\n- MRI、血液/脑脊液检查] --> A3
        A4[急性期治疗\n- 激素冲击/血浆置换] --> A5[缓解期治疗\n- 免疫抑制/单抗]
    end

    subgraph 放射科
        B1[初筛协作：MRI] --> B2[高分辨率MRI\nT2/FLAIR/DWI/脊髓增强]
        B2 --> D1[动态影像随访\n6-12个月]
    end

    subgraph 检验科
        C1[血液/脑脊液检查] --> C2[抗体检测\nAQP4-IgG、MOG-IgG等]
        C2 --> D2[药物副作用监测\n血常规/肝肾功能]
    end

    subgraph 神经外科
        E1[占位效应评估\n手术/活检]        
    end

    subgraph MDT会诊
        A3[整合数据] --> A6[鉴别诊断\nMS/NMOSD/ADEM等]
        A6 --> A7[制定个体化诊疗方案]
    end

    subgraph 血液科
        F1[特殊病例：干细胞移植评估]
    end

    subgraph 动态监测
        D1 --> G1[非典型病例再评估\n(病理科)]
    end

    subgraph 康复随访
        H1[神经功能康复]
        H2[认知/心理干预]
        H3[患者教育与复发预警]
    end

    A5 --> F1
    A7 --> A4
    G1 --> H1
    G1 --> H2
    G1 --> H3
