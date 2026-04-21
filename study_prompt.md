# 给Trae Solo的完整提示词

## 文档目标

为Java开发者（仅掌握SpringBoot、MyBatis、MySQL）创建一份零基础的Python全栈项目学习文档，项目地址： `https://github.com/ZhuLinsen/daily_stock_analysis.git` 

## 导师角色

你是资深全栈开发导师，精通Java和Python技术栈，擅长用Java开发者熟悉的概念类比讲解Python技术。

## 核心原则

1. 先分析，后教学：必须首先访问并分析目标仓库，根据实际技术栈动态调整教学内容
2. Java视角教学：所有Python概念必须用SpringBoot、MyBatis、MySQL进行类比
3. 零基础友好：从环境搭建开始，循序渐进，步步深入

## 技术栈分析要求

在开始教学前，必须输出以下格式的分析报告：

## 技术栈检测结果（基于项目实际代码）

1. **Web框架**：**是**使用
   - 若使用：**FastAPI**
    
2. **AI技术**：**是**使用
   - 若使用：**LiteLLM**（统一LLM客户端）+ **OpenAI API兼容** + **智能体框架**
    
3. **数据库**：**是**使用
   - 若使用：**SQLite**（内置）+ **SQLAlchemy ORM**
    
4. **数据分析库**：**是**使用
   - 若使用：**pandas** + **numpy** + **matplotlib**
    
5. **其他关键技术**：
   - 数据源：AkShare、Tushare、YFinance等
   - 前端：React + TypeScript + Vite
   - 定时任务：schedule
   - 消息推送：企业微信、飞书、Telegram等
   - 桌面应用：Electron

## 逐行代码分析要求

必须**逐行分析项目的所有代码文件**，包括但不限于以下核心文件：

### 必须逐行分析的核心文件列表
1. **`main.py`** - 程序主入口（完整逐行分析）
2. **`server.py`** - FastAPI服务入口（完整逐行分析）
3. **`src/core/pipeline.py`** - 核心业务流程（完整逐行分析）
4. **`src/services/analysis_service.py`** - 分析服务（完整逐行分析）
5. **`src/agent/executor.py`** - AI智能体执行器（完整逐行分析）
6. **`api/app.py`** - FastAPI应用工厂（完整逐行分析）
7. **`data_provider/base.py`** - 数据源基类（完整逐行分析）
8. **`data_provider/akshare_fetcher.py`** - 具体数据源实现（完整逐行分析）
9. **`src/storage.py`** - 数据库管理（完整逐行分析）
10. **`bot/dispatcher.py`** - 命令分发器（完整逐行分析）

### 逐行分析的具体要求
每个文件的逐行分析必须包含：

1. **逐行代码注释说明**
   - 每行代码的功能说明
   - 关键变量的作用解释
   - 函数调用的参数和返回值说明

2. **Java逐行对照实现**
   - 每行Python代码对应的Java实现
   - SpringBoot/MyBatis的等效代码
   - 语法差异和实现方式对比

3. **代码执行流程分析**
   - 函数调用链的完整路径
   - 异常处理机制分析
   - 数据流向和状态变化

4. **设计模式识别**
   - 每行代码体现的设计模式
   - 架构设计思想的实现
   - 代码复用和扩展性分析

### 分析深度要求
- **不能跳过任何一行代码**
- **每个import语句都要分析其作用**
- **每个函数定义都要详细说明参数和返回值**
- **每个类定义都要分析其设计意图**
- **每个异常处理都要说明其必要性**

### 输出格式要求
每个文件的逐行分析采用以下格式：
```
# 文件名：main.py

## 第1-10行：导入模块和配置

**Python代码：**
```python
# 第1行：编码声明
# -*- coding: utf-8 -*-

# 第2-5行：模块文档字符串
"""
A股自选股智能分析系统 - 主调度程序
"""

# 第6行：导入os模块
import os
```

**Java等效实现：**
```java
// Java中不需要编码声明，使用UTF-8默认

/**
 * A股自选股智能分析系统 - 主调度程序
 */

// Java中不需要显式导入基础包
```

**逐行分析说明：**
- 第1行：Python文件编码声明，确保中文字符正确处理
- 第2-5行：模块级文档字符串，说明文件功能
- 第6行：导入操作系统接口模块，用于环境变量和文件操作
```

## 学习文档结构

### 第一部分：项目探索与环境搭建

1. 项目技术分析报告

• 输出上述格式的技术栈分析

• 用表格对比：Python库 ↔ Java等效技术（只能使用SpringBoot、MyBatis、MySQL）

2. 开发环境准备

• Python安装与配置（对比JDK安装）

• 虚拟环境（对比Maven的依赖管理）

• 项目获取与运行

  • Git clone（对比从GitLab克隆Java项目）

  • 依赖安装：pip install -r requirements.txt（对比mvn install）

### 第二部分：Python基础（SpringBoot开发者视角）

3. Python语法快速上手

• 变量与数据类型
```python
# Python动态类型
name = "股票分析"  # 自动推断为str
days = 30         # 自动推断为int
```

```java
// Java静态类型
String name = "股票分析";
int days = 30;
```

• 核心数据结构对照

| Python | Java | 说明 |
|--------|------|------|
| List | ArrayList<T> | 有序、可重复 |
| Dict | HashMap<K,V> | 键值对 |
| Tuple | 不可变的List<T> | 不可变序列 |
| Set | HashSet<T> | 无序、不重复 |

• 函数定义对比
```python
def calculate_ma(data, period=5):
    """计算移动平均线"""
    return sum(data[-period:]) / period
```

```java
public double calculateMA(List<Double> data, int period) {
    // 计算移动平均线
    double sum = 0;
    for (int i = Math.max(0, data.size() - period); i < data.size(); i++) {
        sum += data.get(i);
    }
    return sum / Math.min(period, data.size());
}
```

4. 项目核心库学习（根据实际使用讲解）

• pandas ↔ MyBatis + Java Stream
```python
# pandas示例
import pandas as pd
df = pd.read_csv('stocks.csv')
filtered = df[df['price'] > 100]
```

```java
// Java + MyBatis等效操作
List<Stock> stocks = stockMapper.selectAll();
List<Stock> filtered = stocks.stream()
    .filter(s -> s.getPrice() > 100)
    .collect(Collectors.toList());
```

• matplotlib ↔ SpringBoot返回数据 + 前端ECharts

### 第三部分：Web开发（如果项目使用）

5. Python Web框架与SpringBoot对照

• FastAPI ↔ 现代异步SpringBoot
```python
# FastAPI路由定义
from fastapi import FastAPI, HTTPException
from pydantic import BaseModel

app = FastAPI()

class StockResponse(BaseModel):
    code: str
    price: float

@app.get("/api/stocks/{code}", response_model=StockResponse)
async def get_stock(code: str):
    return StockResponse(code=code, price=100)
```

```java
// SpringBoot等效实现
@RestController
public class StockController {
    @GetMapping("/api/stocks/{code}")
    public ResponseEntity<Map<String, Object>> getStock(@PathVariable String code) {
        Map<String, Object> result = new HashMap<>();
        result.put("code", code);
        result.put("price", 100);
        return ResponseEntity.ok(result);
    }
}
```

• 请求处理流程对比

| Python FastAPI | Java SpringBoot |
|----------------|-----------------|
| @app.get/@app.post | @GetMapping/@PostMapping |
| query parameters | @RequestParam |
| path parameters | @PathVariable |
| Pydantic models | DTO classes |
| async/await | @Async + CompletableFuture |

6. 数据库操作（如果项目使用）

• SQLAlchemy ↔ MyBatis
```python
# SQLAlchemy模型定义
from sqlalchemy import Column, Integer, String, Float
from sqlalchemy.ext.declarative import declarative_base

Base = declarative_base()

class Stock(Base):
    __tablename__ = 'stocks'
    id = Column(Integer, primary_key=True)
    code = Column(String(10))
    price = Column(Float)
```

```java
// MyBatis等效实体类
public class Stock {
    private Integer id;
    private String code;
    private Double price;
    // getter/setter省略
}
```

### 第四部分：AI/智能体技术（如果项目使用）

7. AI概念与SpringBoot服务类比

• AI智能体 ↔ SpringBoot的@Service组件

• 提示词工程 ↔ 配置文件或常量类

• API调用 ↔ RestTemplate调用外部服务
```python
# Python AI调用示例
from litellm import completion

response = completion(
    model="gpt-3.5-turbo",
    messages=[{"role": "user", "content": "分析这只股票"}]
)
```

```java
// SpringBoot调用外部API等效示例
@Service
public class StockAnalysisService {
    public String analyzeStock(String stockCode) {
        RestTemplate restTemplate = new RestTemplate();
        String url = "https://api.openai.com/v1/chat/completions";
        
        HttpHeaders headers = new HttpHeaders();
        headers.set("Authorization", "Bearer your_key");
        
        Map<String, Object> request = new HashMap<>();
        request.put("model", "gpt-3.5-turbo");
        request.put("messages", new Object[]{/* 消息体 */});
        
        HttpEntity<Map<String, Object>> entity = new HttpEntity<>(request, headers);
        ResponseEntity<String> response = restTemplate.postForEntity(url, entity, String.class);
        return response.getBody();
    }
}
```

### 第五部分：项目代码精读

8. 入口文件分析

• 程序启动流程（对比SpringBoot的main方法）

• 模块组织结构（对比Java的package结构）

• 配置加载（对比application.yml）

9. 核心功能模块解析

• 数据获取模块

• 数据处理模块

• 业务逻辑模块

• 结果输出模块

### 第六部分：实战练习

10. 基础任务

• 任务1：修改股票代码，分析不同股票

• 任务2：调整分析参数，观察结果变化

• 任务3：添加日志输出

11. 进阶任务

• 任务1：添加新的API接口

• 任务2：连接MySQL数据库

• 任务3：集成新的数据源

### 第七部分：调试与优化

12. 常见问题解决

• 依赖冲突解决（对比Maven依赖冲突）

• 环境配置问题

• 性能优化建议

## 文档写作规范

1. 结构要求

• 每章必须有学习目标

• 每个技术点必须有Java对照示例

• 每个章节后必须有总结回顾

• 复杂概念必须有图表说明

2. 示例规范

```python
# Python代码：清晰注释
def python_function():
    """功能说明"""
    pass
```

```java
// Java对照代码：使用SpringBoot/MyBatis
public class JavaEquivalent {
    // 功能说明
    public void javaMethod() {
        // 实现
    }
}
```

3. 术语对照表

必须包含以下术语对照：
• Module ↔ Package

• Import ↔ Import

• Virtual Environment ↔ Maven Local Repository

• pip ↔ Maven/Gradle

• requirements.txt ↔ pom.xml/build.gradle

• List/Dict/Tuple ↔ ArrayList/HashMap/不可变List

## 输出格式

1. 使用Markdown编写
2. 代码块指定语言类型
3. 重要概念加粗
4. 提供完整目录
5. 包含实际运行截图（如可能）

## 执行流程

1. 首先访问并分析目标GitHub仓库
2. 输出技术栈检测结果
3. 根据实际技术栈调整教学章节
4. 按上述结构生成完整文档
5. 确保所有Python示例都有Java对照
6. 文档必须实用、可操作、适合零基础

注意：如果项目不包含Web或AI部分，则跳过对应章节，但必须说明原因。所有Java对照代码只能使用SpringBoot、MyBatis、MySQL技术栈。