subgraph Initial_Screening_Phase["初筛阶段"]
    方向 TB
        Rad1(“放射科”)
        B1["初步检查：MRI"]
        A1[“完成疾病史采集、神经系统查体”]
        实验室1(“检验科”)
        C1["血液/脑脊液检查"]
  结尾
 subgraph Multimodal_Assessment_Phase["多模态评估阶段"]
    方向 TB
        Rad2["高分辨率MRI：T2/FLAIR/DWI"]
        Rad3["推断推理、增强扫描"]
        Lab2["抗体检测：AQP4-IgG、MOG-IgG"]
        Lab3["寡克隆带、IgG指数"]
        Neuro2["评估占位效应"]
        神经外科
  结尾
 subgraph Core_MDT_Consultation["MDT会诊核心阶段"]
        诊断[“诊断诊断：MS/NMOSD/ADEM/感染/肿瘤”]
        整合[“整合临床-影像-实验室数据”]
        方案[《制定个体化诊疗方案》]
  结尾
 subgraph Staged_Treatment_Phase["分型治疗阶段"]
        缓解[“缓解期选择：免疫抑制/抗体类药物”]
        Acute["急性期：冲击洪水/替代"]
        血液科[“需血液科协作”]
        干细胞["干细胞移植评估"]
  结尾
 subgraph Dynamic_Monitoring_System["动态体系监测"]
        FollowUp["放射科定期影像检查：每6-12个月"]
        Monitor[“科监测药物污染物：血液经常/肝肾功能”]
  结尾
 subgraph Rehab_FollowUp["康复与意义"]
        康复[“神经功能缺损康复治疗”]
        心理干预
        教育["患者教育及预警"]
  结尾
    A1 -- 启动 --> B1
    B1 -- 协作 --> Rad1
    B1-->C1
    C1 -- 协作 --> Lab1
    辐射1-->辐射2
    辐射2-->辐射3
    实验室1 --> 实验室2
    实验室2 --> 实验室3
    神经-->神经2
    整合-->诊断
    诊断 --> 计划
    急性-->缓解
    缓解期 -- 特殊病例 --> 干细胞
    干细胞-->血液学
    Rad3 --> 后续
    Lab3 --> 监控
    初步筛选阶段 --> 多模式评估阶段
    多模态评估阶段 --> 核心多模态治疗咨询
    核心MDT会诊-->分阶段治疗阶段
    分阶段治疗阶段-->动态监测系统
    动态监控系统 --> 康复跟进
