```mermaid
flowchart TB
    A[开始] --> B{是否渲染?}
    B -->|是| C[成功]
    B -->|否| D[检查语法]
```
