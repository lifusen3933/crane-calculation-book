# 🏗️ 起重机智能验算决策系统

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Streamlit](https://img.shields.io/badge/Streamlit-WebApp-red.svg)](https://streamlit.io/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Standard](https://img.shields.io/badge/Standard-GB%2FT%203811--2008-orange.svg)]()

基于实际工程案例（100吨电动双梁桥式起重机）的完整起重机设计计算和验算系统。

## 📋 系统特性

### ✨ 核心功能

- 🔗 **钢丝绳计算** - 直径选择、安全系数校核
- ⚡ **电机选择** - 功率计算、型号选择
- 🛑 **制动器计算** - 制动力矩、制动器选型
- 🌀 **卷筒设计** - 直径、长度、容绳量设计
- 🛡️ **安全保护装置** - 智能配置、合规检查
- 💪 **结构强度** - 弯曲应力、安全系数
- ⚖️ **稳定性验算** - 抗倾覆稳定性分析
- 🔄 **疲劳验算** - 疲劳强度、寿命分析
- 📊 **载荷分析** - 载荷组合、动载系数
- 📖 **标准查询** - 48个标准文档检索

### 🎯 技术特点

- ✅ **基于真实案例** - 100吨起重机实际计算书
- ✅ **符合国家标准** - GB/T 3811-2008、GB/T 6067-2010
- ✅ **交互式计算** - 实时结果、图形化界面
- ✅ **自动选型** - 基于数据库智能推荐
- ✅ **合规检查** - 自动验证设计完整性
- ✅ **多格式报告** - Markdown、Word、PDF三种格式
- ✅ **交互式查看** - 章节选择+查看按钮模式
- ✅ **彩色状态标识** - ✅绿色PASS、❌红色FAIL、⚠️橙色WARNING
- ✅ **时间戳记录** - 计算时间和下载时间追溯
- ✅ **标准资料** - 48个PDF标准、26个参数、16个公式

## 📊 数据规模

| 类别 | 数量 | 说明 |
|------|------|------|
| 计算模块 | 8个 | 覆盖设计全流程 |
| 页面功能 | 8个 | Streamlit多页面应用 |
| 标准文档 | 48个 | PDF格式标准文件 |
| 安全装置 | 21项必需 + 5项可选 | 完整安全保护装置库 |
| 参数数据 | 26个 | 起重机标准参数 |
| 计算公式 | 16个 | 核心计算公式 |
| 代码行数 | ~8000行 | 完整系统代码 |

## 🚀 快速开始

### 环境要求

- Python 3.8+
- 依赖包：
  - streamlit
  - pandas
  - numpy
  - openpyxl

### 安装依赖

```bash
pip install streamlit pandas numpy openpyxl
```

### 启动系统

#### 方式一：使用启动脚本（推荐）

```bash
# 使用Shell脚本
bash scripts/RUN_APP.sh

# 或使用Python脚本
python scripts/start.py
```

#### 方式二：直接启动Streamlit

```bash
# 启动导航主页（推荐）
streamlit run pages/01_home.py --server.port 8501

# 启动快速计算页面
streamlit run pages/02_calculator.py --server.port 8501
```

#### 方式三：启动主入口

```bash
# 启动主入口（会重定向到导航主页）
streamlit run app/main.py --server.port 8501
```

### 访问系统

启动后在浏览器中打开：

- **导航主页**: http://localhost:8501/01_home
- **快速计算**: http://localhost:8501/02_calculator
- **项目管理**: http://localhost:8501/05_project_management
- **标准问答**: http://localhost:8501/06_qa_system
- **报告生成**: http://localhost:8501/03_report_generator
- **PDF查看**: http://localhost:8501/04_pdf_viewer
- **增强计算器**: http://localhost:8501/07_modular_calculator

> **💡 提示**: 首次使用建议从导航主页开始，它提供了完整的页面导航和快速访问功能。

### 快速演示

```bash
# 安全保护装置演示
python3 demo_safety_protection.py

# 标准资料调用演示
python3 demo_standard_usage.py
```

## 📁 项目结构

```
crane-calculation-book/
├── app.py                          # 主入口文件
├── core/calculations/              # 核心计算模块
│   ├── wire_rope.py                # 钢丝绳计算
│   ├── motor_selector.py           # 电机选择
│   ├── drum_brake_design.py        # 卷筒制动器设计
│   ├── load_analysis.py            # 载荷分析
│   ├── structure_strength.py       # 结构强度
│   └── safety_protection_system.py # 安全保护装置
├── pages/                          # Streamlit页面
│   ├── 00_welcome.py               # 欢迎页
│   ├── 01_home.py                  # 主页
│   ├── 02_calculator.py            # 快速计算
│   ├── 03_report_generator.py      # 报告生成
│   ├── 04_pdf_viewer.py            # PDF查看
│   ├── 05_project_management.py    # 项目管理
│   ├── 06_qa_system.py             # 标准问答
│   └── 07_modular_calculator.py    # 模块化计算
├── reports/                        # 报告模板
│   ├── calculation_book_template.py # 计算书模板
│   ├── sample_calculation_book.md   # 示例报告
│   └── sample_calculation_book.json # 示例数据
├── standards/                      # 标准资料
│   ├── standard_manager.py         # 标准管理器
│   ├── docs/                       # 标准文档 (48个PDF)
│   └── data/                       # 数据文件
│       ├── standards_index.xlsx    # 标准索引
│       ├── crane_parameters.xlsx   # 参数数据库
│       └── calculation_formulas.xlsx # 公式数据库
└── demo_*.py                       # 演示程序
```

## 💡 使用指南

### 1. 快速计算

1. 进入"快速计算"页面
2. 输入基本参数：
   - 起重机类型：桥式/门式/半门式
   - 额定载荷：0.1-1000 t
   - 跨度：1-100 m
   - 工作级别：A1-A8
3. 选择计算类型：
   - 载荷分析
   - 钢丝绳计算
   - 电机选择
   - 制动器计算
   - 卷筒设计
   - 安全保护装置
   - 结构强度
   - 稳定性验算
   - 疲劳验算
4. 查看实时计算结果
5. 下载计算报告

### 2. 安全保护装置设计

1. 选择"安全保护装置"计算类型
2. 配置基本参数：
   - ✅ 电气化
   - ✅ 起升机构
   - ✅ 小车运行
   - ✅ 大车运行
   - ✅ 室外作业
   - ✅ 多台起重机
3. 查看系统推荐的必需安全保护装置
4. 选择可选安全保护装置
5. 查看合规性评估结果
6. 生成并下载安全报告

### 3. 标准查询

1. 进入"标准问答"页面
2. 输入关键词（如"起重机"、"安全"、"载荷"）
3. 查看匹配的标准文档
4. 查看标准条款和说明
5. 参考标准进行设计

### 4. 计算书生成

1. 进入"报告生成"页面
2. 选择要包含的计算模块
3. 输入项目信息
4. 点击"生成计算书"
5. 下载Markdown或JSON格式报告

## 📚 标准依据

本系统严格遵循以下国家标准：

- **GB/T 3811-2008** 起重机设计规范
- **GB/T 6067.1-2010** 起重机械安全规程 第1部分：总则
- **GB 6067.5-2014** 起重机械安全规程 第5部分：桥式和门式起重机
- **GB/T 14405-2011** 通用桥式起重机
- **GB/T 14406-2011** 通用门式起重机

## 📊 计算示例

### 示例：100吨桥式起重机

**输入参数**：
- 起重机类型：桥式
- 额定载荷：100 t
- 跨度：31.5 m
- 工作级别：A5
- 起升高度：20 m
- 起升速度：4 m/min

**计算结果**：
- 钢丝绳：28NT 6X19W+FC 1870，安全系数5.33 ✅
- 电机：YZP315S-6，81kW，960r/min ✅
- 制动器：ED121/6，1600N·m ✅
- 卷筒：直径800mm，长度1492mm ✅
- 安全装置：21项必需装置 ✅

## 🔧 API使用

### 在代码中调用计算模块

```python
from core.calculations.safety_protection_system import (
    SafetyProtectionCalculator,
    CraneType,
    WorkClass
)

# 创建计算器
calculator = SafetyProtectionCalculator()

# 计算必需的安全保护装置
result = calculator.calculate_required_devices(
    crane_type=CraneType.BRIDGE,
    work_class=WorkClass.A5,
    span_m=31.5,
    rated_load_t=100.0,
    electrical_ready=True,
    has_multiple_cranes=True,
    outdoor_operation=True
)

print(f"必需装置: {result['total_required']} 项")
```

### 标准资料调用

```python
from standards.standard_manager import StandardManager

# 初始化管理器
manager = StandardManager('/path/to/project')

# 查找标准
info = manager.get_standard_info('GB/T 3811-2008')

# 获取参数
params = manager.get_all_parameters()

# 获取公式
formulas = manager.load_formula_data()
```

## 📈 应用场景

### 1. 工程设计
- 起重机初步设计计算
- 方案比选和优化
- 设计验证和校核
- 技术方案评审

### 2. 教学培训
- 起重机设计课程教学
- 学生课程设计
- 毕业设计指导
- 工程师培训

### 3. 科研开发
- 新型起重机研发
- 设计方法研究
- 标准规范验证
- 技术创新验证

### 4. 质量控制
- 设计文件审查
- 产品检验验收
- 安全评估分析
- 事故分析复盘

## 🤝 贡献指南

欢迎提交Issue和Pull Request来改进本项目！

### 贡献方式

1. Fork本项目
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 开启Pull Request

### 报告问题

如果您发现问题或有改进建议，请在GitHub上创建Issue。

## 📄 许可证

本项目采用MIT许可证 - 查看 [LICENSE](LICENSE) 文件了解详情。

## 👨‍💻 作者

**Claude Code Assistant** - 智能代码助手

## 🙏 致谢

- 感谢所有标准制定者和维护者
- 感谢Python和Streamlit开源社区
- 感谢所有贡献者和使用者

## 📞 联系我们

- 项目主页: https://github.com/your-repo/crane-calculation-book
- 问题反馈: https://github.com/your-repo/crane-calculation-book/issues
- 文档: https://your-docs-site.com

---

⭐ 如果这个项目对您有帮助，请给我们一个Star！

**版本**: v2.0.0  
**最后更新**: 2025-12-13
