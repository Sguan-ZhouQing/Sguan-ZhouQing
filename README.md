<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>星必尘Sguan · 电机控制/FOC 主页</title>
    <!-- 干净科技感字体，现代嵌入式风 -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(145deg, #f0f5fa 0%, #e9f0f7 100%);
            font-family: 'Plus Jakarta Sans', sans-serif;
            color: #1a2e3f;
            line-height: 1.5;
            padding: 2rem 1.5rem;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .github-card {
            max-width: 1300px;
            width: 100%;
            margin: 0 auto;
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border-radius: 3.5rem;
            box-shadow: 0 30px 60px -20px rgba(0, 30, 60, 0.3), inset 0 1px 2px rgba(255,255,255,0.8);
            border: 1px solid rgba(255,255,255,0.6);
            overflow: hidden;
            padding: 2.5rem 2.8rem;
            transition: all 0.2s ease;
        }

        /* 头部区域 — 动态签名 + 昵称/邮箱 */
        .hero {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 2.5rem;
            border-bottom: 2px dashed rgba(0, 110, 230, 0.15);
            padding-bottom: 1.8rem;
        }

        .typing-block {
            font-size: 1.8rem;
            font-weight: 600;
            background: linear-gradient(135deg, #003057, #1b4f8b);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .typing-block span {
            background: #0b2b44;
            color: white;
            font-size: 1.1rem;
            font-weight: 500;
            padding: 0.35rem 1.2rem;
            border-radius: 40px;
            margin-left: 1rem;
            letter-spacing: 0.3px;
            box-shadow: 0 4px 8px rgba(0,70,150,0.15);
            background: linear-gradient(145deg, #173e5f, #0f2f4a);
            -webkit-text-fill-color: white;
        }

        .contact-badge {
            display: flex;
            gap: 2rem;
            align-items: center;
            background: rgba(255,255,255,0.5);
            padding: 0.6rem 2rem 0.6rem 1.8rem;
            border-radius: 60px;
            border: 1px solid rgba(0,110,230,0.2);
            box-shadow: 0 6px 14px rgba(0,30,60,0.08);
        }

        .contact-badge a {
            text-decoration: none;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 8px;
            color: #1f4973;
            transition: 0.2s;
        }

        .contact-badge a:hover {
            color: #0077be;
            transform: translateY(-2px);
        }

        .contact-badge .email {
            background: #0b2f4e;
            color: white !important;
            padding: 0.4rem 1.2rem;
            border-radius: 40px;
            font-size: 0.95rem;
            box-shadow: 0 4px 10px rgba(0,100,200,0.3);
        }

        .contact-badge .email:hover {
            background: #134872;
            color: white;
        }

        /* 徽章海 (技术栈) — 沿用灵动风格 + 常用软件 */
        .tech-badges {
            margin: 2rem 0 1.8rem 0;
            display: flex;
            flex-wrap: wrap;
            gap: 0.4rem 0.7rem;
            align-items: center;
            background: rgba(255, 255, 255, 0.4);
            padding: 1.2rem 1.8rem;
            border-radius: 48px;
            border: 1px solid rgba(0,80,150,0.1);
            backdrop-filter: blur(4px);
        }

        .badge {
            display: inline-block;
            padding: 0.3rem 1.1rem;
            border-radius: 40px;
            font-size: 0.85rem;
            font-weight: 600;
            letter-spacing: 0.02em;
            background: white;
            color: #1a3a5e;
            box-shadow: 0 2px 6px rgba(0, 40, 70, 0.1);
            border: 1px solid rgba(0,110,230,0.2);
            transition: 0.15s;
        }

        .badge.foc {
            background: #0a2647;
            color: white;
            border-color: #2e5a9c;
        }

        .badge.ide {
            background: #eef4ff;
            border-color: #a0c4ff;
        }

        .badge:hover {
            transform: scale(1.02);
            box-shadow: 0 5px 12px rgba(0,110,230,0.2);
        }

        /* 布局：左列(简介+项目) / 右列(技能+履历亮点) — 采用grid */
        .main-grid {
            display: grid;
            grid-template-columns: 1.6fr 1fr;
            gap: 2rem;
            margin: 2rem 0 1.5rem;
        }

        /* 左侧项目卡片 */
        .project-section h2, .right-panel h2 {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 1.4rem;
            display: flex;
            align-items: center;
            gap: 10px;
            color: #113355;
            letter-spacing: -0.02em;
        }

        .project-section h2 i, .right-panel h2 i {
            font-size: 1.9rem;
            background: #0b2b44;
            color: white;
            width: 40px;
            height: 40px;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            border-radius: 14px;
        }

        .project-card {
            background: rgba(255,255,255,0.7);
            backdrop-filter: blur(4px);
            border-radius: 2rem;
            padding: 1.8rem;
            margin-bottom: 1.5rem;
            border: 1px solid rgba(255,255,255,0.8);
            box-shadow: 0 10px 20px -10px rgba(0,30,60,0.15);
            transition: all 0.2s;
        }

        .project-card:hover {
            background: rgba(255,255,255,0.85);
            box-shadow: 0 20px 28px -12px #1a4b77;
        }

        .project-title {
            font-size: 1.5rem;
            font-weight: 700;
            display: flex;
            align-items: center;
            gap: 12px;
            margin-bottom: 0.8rem;
        }

        .project-title .tag {
            background: #2b5f8a;
            color: white;
            font-size: 0.75rem;
            font-weight: 600;
            padding: 0.2rem 1rem;
            border-radius: 20px;
        }

        .project-desc {
            color: #1f3a54;
            margin: 1rem 0 1.2rem;
            font-size: 0.98rem;
            font-weight: 400;
            line-height: 1.6;
            padding-left: 0.5rem;
            border-left: 3px solid #3f8ab3;
            background: rgba(230, 244, 255, 0.3);
            padding: 1rem 1.4rem;
            border-radius: 1rem;
        }

        .foc-highlight {
            background: #0d2b44;
            color: #e1f0ff;
            border-radius: 1rem;
            padding: 1.2rem 1.5rem;
            margin-top: 1rem;
            border: 1px solid #316994;
        }

        .foc-highlight a {
            color: #b6dcff;
            text-decoration: underline;
            font-weight: 500;
        }

        /* 右侧面板 */
        .right-panel {
            display: flex;
            flex-direction: column;
            gap: 1.8rem;
        }

        .info-box {
            background: rgba(255,255,255,0.6);
            backdrop-filter: blur(4px);
            border-radius: 2rem;
            padding: 1.8rem 1.6rem;
            border: 1px solid rgba(255,255,255,0.7);
            box-shadow: 0 6px 14px rgba(0,30,50,0.06);
        }

        .info-box h3 {
            font-size: 1.3rem;
            margin-bottom: 1.5rem;
            font-weight: 700;
            display: flex;
            align-items: center;
            gap: 8px;
            color: #113355;
            border-bottom: 2px solid rgba(0,100,200,0.2);
            padding-bottom: 0.5rem;
        }

        .skill-pills {
            display: flex;
            flex-wrap: wrap;
            gap: 0.6rem;
        }

        .skill-pill {
            background: white;
            border-radius: 40px;
            padding: 0.4rem 1.2rem;
            font-size: 0.85rem;
            font-weight: 600;
            border: 1px solid #b5d0f0;
            color: #1d4a76;
            box-shadow: 0 2px 4px rgba(0,30,80,0.05);
        }

        .skill-pill.foc {
            background: #0a2647;
            color: white;
            border: none;
        }

        .software-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 0.6rem;
            margin-top: 1rem;
        }

        .software-item {
            background: #edf4fd;
            padding: 0.4rem 1rem;
            border-radius: 30px;
            font-size: 0.8rem;
            font-weight: 500;
            display: flex;
            align-items: center;
            gap: 4px;
            border: 1px solid #cddefa;
        }

        /* 小logo行 (之前md里的动感图标) */
        .icon-strip {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: center;
            gap: 20px;
            margin: 2rem 0 0.5rem;
            padding: 1.2rem 0.5rem;
            border-top: 2px dashed rgba(0,100,200,0.2);
            border-bottom: 2px dashed rgba(0,100,200,0.2);
        }

        .icon-strip img {
            width: 60px;
            height: 60px;
            object-fit: contain;
            filter: drop-shadow(0 4px 6px rgba(0,30,80,0.1));
            transition: 0.2s;
            border-radius: 16px;
            background: rgba(255,255,255,0.6);
            padding: 8px;
        }

        .icon-strip img:hover {
            transform: scale(1.1);
            background: white;
        }

        /* 比赛荣誉 */
        .award-banner {
            background: linear-gradient(105deg, #112f4b, #1a4975);
            color: white;
            border-radius: 2rem;
            padding: 1.2rem 2rem;
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-top: 1rem;
        }

        .award-banner span {
            font-size: 1.4rem;
            font-weight: 700;
            letter-spacing: 0.5px;
        }

        .footer-note {
            text-align: right;
            font-size: 0.9rem;
            margin-top: 2rem;
            color: #2e5570;
            border-top: 1px solid rgba(0,60,120,0.15);
            padding-top: 1.5rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .footer-note .gh-link {
            background: #0b2b44;
            color: white;
            padding: 0.4rem 1.8rem;
            border-radius: 40px;
            text-decoration: none;
            font-weight: 500;
        }

        /* 响应式 */
        @media (max-width: 850px) {
            .main-grid {
                grid-template-columns: 1fr;
            }
            .github-card {
                padding: 2rem 1.5rem;
            }
        }
    </style>
</head>
<body>
    <div class="github-card">
        <!-- 头部：动态名称 + 联系方式（邮箱/昵称） -->
        <div class="hero">
            <div class="typing-block">
                <span style="background: transparent; box-shadow: none; padding:0;">/* 星必尘Sguan */</span>
                <span>FOC · 电机控制</span>
            </div>
            <div class="contact-badge">
                <a href="#" class="email">📧 3464647102@qq.com</a>
                <a href="https://github.com/Sguan-ZhouQing" target="_blank">🐙 GitHub/Sguan-ZhouQing</a>
                <a href="https://oshwhub.com/sguan606" target="_blank">⚡ 开源硬件 sguan606</a>
            </div>
        </div>

        <!-- 技术徽章（常用软件 + FOC突出） 包含履历里所有IDE及软件 -->
        <div class="tech-badges">
            <span class="badge foc">FOC 无感控制</span>
            <span class="badge foc">SMO/PLL/HFI</span>
            <span class="badge foc">PID+ADRC</span>
            <!-- 常用软件 IDE 列表 (完全按您提供) -->
            <span class="badge ide">Keil uVision5</span>
            <span class="badge ide">STM32CubeMX</span>
            <span class="badge ide">MounRiver Studio</span>
            <span class="badge ide">EmbeddedBuilder</span>
            <span class="badge ide">Thonny</span>
            <span class="badge ide">CCS IDE</span>
            <span class="badge ide">VS Code</span>
            <span class="badge ide">Arduino IDE</span>
            <span class="badge ide">HBuilder X</span>
            <span class="badge ide">NanoEdge AI Studio</span>
            <span class="badge ide">SOLIDWORKS</span>
            <span class="badge ide">嘉立创EDA</span>
            <span class="badge ide">MATLAB</span>
            <span class="badge ide">Mathematica</span>
            <span class="badge">FreeRTOS/UCOS</span>
            <span class="badge">SIMULINK</span>
        </div>

        <!-- 核心网格：左侧项目经历(重点FOC) + 右侧个人档案/技能 -->
        <div class="main-grid">
            <!-- 左侧区域：SguanFOC库 + 仿生蝴蝶 + 智能药仓 -->
            <div class="project-section">
                <h2><i>⚡</i> 核心·电机控制工程</h2>
                <!-- SguanFOC库 v3.0 (最突出) -->
                <div class="project-card" style="border-left: 6px solid #1f69b0;">
                    <div class="project-title">
                        <span>SguanFOC 库 v3.0</span>
                        <span class="tag">无感FOC 开源</span>
                    </div>
                    <div class="project-desc">
                        独立设计模块化、高实时性电机控制算法库，覆盖无感位置观测到多闭环控制。分层架构：数学运算(Sguan_math)、无感算法(Sguan_Sensorsless)、闭环PID、状态管理、通信协议。完整FOC链 (Clarke/Park/SVPWM/PLL) ，支持7种控制模式，电流环20kHz/状态环1kHz硬实时调度。适配STM32G4/GD32/DSP28335等。
                    </div>
                    <div class="foc-highlight">
                        🔧 定点数Q31 / 巴特沃斯滤波 / 抗饱和PID / 上位机JustFloat · <a href="https://github.com/Sguan-ZhouQing/SguanFOC_Library" target="_blank">github.com/Sguan-ZhouQing/SguanFOC_Library ⏎</a>
                    </div>
                </div>

                <!-- 仿生蝴蝶四轴扑翼 -->
                <div class="project-card" style="border-left: 6px solid #2d8c6b;">
                    <div class="project-title">
                        🦋 仿生蝴蝶四轴扑翼 · 机械创新设计大赛
                        <span class="tag">STM32F1/磁编码器</span>
                    </div>
                    <div class="project-desc">
                        独立全栈开发：双AT8833C驱动四路空心杯，磁编码器反馈+PID闭环实现扑翼频率/幅度精准调节。MPU6050姿态解算与电机控制线程同步，实现俯仰/偏航/滚转稳定控制。自研26x15.5mm双层驱动板(PCB设计)，集成无线通信与电源管理。
                    </div>
                </div>

                <!-- 智能药仓 (嵌入式大赛) -->
                <div class="project-card" style="border-left: 6px solid #b45f3b;">
                    <div class="project-title">
                        💊 一体化智能药仓 · 嵌入式芯片与系统设计大赛
                        <span class="tag">国二 · STM32F4+G4</span>
                    </div>
                    <div class="project-desc">
                        双MCU架构：主控F4负责任务处理，电控G4通过PID闭环控制步进+舵机实现药品抓取；多传感器融合(红外/压力/温湿度/IMU)，I2C/SPI/CAN/FreeRTOS多任务调度；自研PCB原理图/Layout，集成LVGL触控交互。
                    </div>
                </div>

                <!-- 额外突出 比赛经历 -->
                <div class="award-banner">
                    <span>🏆 2025 全国大学生嵌入式芯片与系统设计竞赛 国家二等奖</span>
                    <span>⚙️ 带队攻克FOC 姿态联动</span>
                </div>
            </div>

            <!-- 右侧面板：基本信息 + 自我评价浓缩 + 核心技能/软件 -->
            <div class="right-panel">
                <!-- 基本信息卡片 -->
                <div class="info-box">
                    <h3>👤 星必尘Sguan (周庆)</h3>
                    <div style="display: flex; flex-direction: column; gap: 0.5rem; margin-bottom: 1.5rem;">
                        <div><span style="font-weight:600; width:70px; display:inline-block;">学校</span> 江苏科技大学 · 智能制造工程  (2027届)</div>
                        <div><span style="font-weight:600;">主修</span> 机械/控制/嵌入式/C++/Verilog/电机拖动</div>
                        <div><span style="font-weight:600;">年龄</span> 21岁 · 汉族</div>
                    </div>
                    <h3 style="margin-top: 0.5rem;">🎯 定向·电机控制算法 (FOC)</h3>
                    <div class="skill-pills" style="margin-bottom:1.2rem;">
                        <span class="skill-pill foc">BLDC/PMSM无感FOC</span>
                        <span class="skill-pill foc">HFI/高频注入</span>
                        <span class="skill-pill foc">SMO滑模+PLL</span>
                        <span class="skill-pill foc">弱磁控制</span>
                        <span class="skill-pill foc">PID/LADRC整定</span>
                        <span class="skill-pill foc">MTPA</span>
                        <span class="skill-pill">现代控制理论</span>
                        <span class="skill-pill">Simulink仿真</span>
                    </div>
                </div>

                <!-- 嵌入式/硬件能力 精炼 -->
                <div class="info-box">
                    <h3>⚙️ 嵌入式&硬件栈</h3>
                    <div style="display:flex; flex-wrap: wrap; gap: 1rem;">
                        <div style="min-width:140px;"><span style="font-weight:600;">MCU</span> STM32F/G4, GD32, DSP28335, RISC-V</div>
                        <div style="min-width:140px;"><span style="font-weight:600;">总线</span> CAN/CANopen, EtherCAT, Modbus, I2C/SPI</div>
                        <div style="min-width:140px;"><span style="font-weight:600;">RTOS</span> FreeRTOS, UCOS, 实时调度/看门狗</div>
                    </div>
                    <div class="software-grid" style="margin-top: 1.2rem;">
                        <!-- 罗列关键IDE/工具 略 但更丰富 -->
                        <span class="software-item">Keil</span>
                        <span class="software-item">STM32CubeMX</span>
                        <span class="software-item">MounRiver</span>
                        <span class="software-item">CCS</span>
                        <span class="software-item">EmbeddedBuilder</span>
                        <span class="software-item">VS Code</span>
                        <span class="software-item">Arduino</span>
                        <span class="software-item">HBuilder X</span>
                        <span class="software-item">NanoEdge AI</span>
                        <span class="software-item">嘉立创EDA</span>
                        <span class="software-item">SOLIDWORKS</span>
                        <span class="software-item">MATLAB/Simulink</span>
                        <span class="software-item">Mathematica</span>
                        <span class="software-item">Thonny</span>
                    </div>
                </div>

                <!-- 自我评价精华 (电机/控制/硬件/团队) 小卡片 -->
                <div class="info-box">
                    <h3>🧠 自我评价亮点</h3>
                    <ul style="list-style-type: none; display: flex; flex-direction: column; gap: 0.7rem;">
                        <li>✅ <strong>电机深度</strong> — BLDC/PMSM无感FOC、HFI/SMO/PLL、弱磁控制，实践验证</li>
                        <li>✅ <strong>控制理论</strong> — 自控/现控理论，PID/LADRC参数整定，Simulink建模</li>
                        <li>✅ <strong>嵌入式全栈</strong> — ARM/DSP/RISC-V平台，C解决工程难题，PCB Layout(双层高密度)</li>
                        <li>✅ <strong>工业通信</strong> — CAN/CANopen/CIA402，Modbus，EtherCAT原理，CANoe调试</li>
                        <li>✅ <strong>团队/心态</strong> — 多次担任队长，跨部门整合，乐观抗压，善于调用AI提效</li>
                    </ul>
                </div>

                <!-- 硬件开源链接 -->
                <div style="background: #fff; border-radius: 1.5rem; padding: 1rem 1.5rem; border: 1px solid #c7e0ff;">
                    🔗 硬件开源: <a href="https://oshwhub.com/sguan606" target="_blank">oshwhub.com/sguan606</a>  ·  仿生蝴蝶驱动板/智能药仓PCB
                </div>
            </div>
        </div>

        <!-- 动态图标行 (参考原md里面的风格) 增加趣味性 -->
        <div class="icon-strip">
            <img src="https://camo.githubusercontent.com/7b53063801ebbc1af5a5fb495c7e0b138779d7408c8866c2e874de22548d85c9/68747470733a2f2f63646e2e6a7364656c6976722e6e65742f67682f73756e3032323553554e2f73756e3032323553554e2f6173736574732f696d616765732f72656163742e77656270" alt="react-icon" onerror="this.style.display='none'">
            <img src="https://camo.githubusercontent.com/17579b2740bd9ea1ee0826115b8e27ae8e688f8ad6f1e062aa428840c410024b/68747470733a2f2f63646e2e6a7364656c6976722e6e65742f67682f73756e3032323553554e2f73756e3032323553554e2f6173736574732f696d616765732f7675652e77656270" alt="vue-icon" onerror="this.style.display='none'">
            <img src="https://camo.githubusercontent.com/efb82778b8ffbd24804d371180f159511ac14e21ef8c6c21c08a22c5de47e921/68747470733a2f2f63646e2e6a7364656c6976722e6e65742f67682f73756e3032323553554e2f73756e3032323553554e2f6173736574732f696d616765732f6a732e77656270" alt="js-icon" onerror="this.style.display='none'">
            <img src="https://camo.githubusercontent.com/add047372b66b72c90bf7bda61bf0f9e23a749eadb573bdc494697b6550e2dca/68747470733a2f2f63646e2e6a7364656c6976722e6e65742f67682f73756e3032323553554e2f73756e3032323553554e2f6173736574732f696d616765732f6769746875622e77656270" alt="github-icon" onerror="this.style.display='none'">
            <!-- 添加额外电机控制示意图标 (文本形式) -->
            <span style="font-size: 2.2rem; font-weight: 600; background: #0f3a5e; color:white; padding: 0.2rem 1rem; border-radius: 50px;">FOC</span>
        </div>

        <!-- footer -->
        <div class="footer-note">
            <div>✧ 基于真实履历· 电机控制算法方向 (FOC)  · 星必尘Sguan</div>
            <a href="https://github.com/Sguan-ZhouQing" class="gh-link" target="_blank">📌 Sguan-ZhouQing · GitHub</a>
        </div>
    </div>
</body>
</html>
