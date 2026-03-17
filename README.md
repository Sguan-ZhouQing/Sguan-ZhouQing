<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>星必尘Sguan · 技能图谱</title>
    <!-- 干净字体，图标聚焦 -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,400;14..32,500;14..32,600;14..32,700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(145deg, #edf3fa 0%, #e3eef9 100%);
            font-family: 'Inter', system-ui, -apple-system, sans-serif;
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 1.5rem;
        }

        /* 主页卡片 — 简洁、通透、聚焦 */
        .profile-card {
            max-width: 1000px;
            width: 100%;
            background: rgba(255, 255, 255, 0.8);
            backdrop-filter: blur(14px);
            -webkit-backdrop-filter: blur(14px);
            border-radius: 3.5rem;
            padding: 2.5rem 2.8rem;
            box-shadow: 0 30px 50px -25px rgba(0, 45, 80, 0.3),
                        inset 0 1px 2px rgba(255,255,255,0.7);
            border: 1px solid rgba(255,255,255,0.6);
        }

        /* 头部区域：动态标语 + 联系方式 */
        .hero {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 2.5rem;
            border-bottom: 2px dashed rgba(0, 102, 204, 0.2);
            padding-bottom: 1.8rem;
        }

        .name-title {
            font-size: 2.2rem;
            font-weight: 700;
            background: linear-gradient(135deg, #103956, #1e5a8b);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .name-title span {
            background: #123e5e;
            color: white;
            font-size: 1.1rem;
            font-weight: 500;
            padding: 0.3rem 1.2rem;
            border-radius: 40px;
            -webkit-text-fill-color: white;
            letter-spacing: 0.3px;
        }

        .quick-contact {
            display: flex;
            gap: 1.2rem;
            align-items: center;
            background: rgba(255,255,255,0.6);
            padding: 0.5rem 1.8rem 0.5rem 1.5rem;
            border-radius: 60px;
            border: 1px solid rgba(0,110,230,0.15);
            font-size: 0.95rem;
        }

        .quick-contact a {
            text-decoration: none;
            font-weight: 500;
            color: #1f4a72;
            display: inline-flex;
            align-items: center;
            gap: 6px;
        }

        .email-chip {
            background: #0f334d;
            color: white !important;
            padding: 0.3rem 1.2rem;
            border-radius: 40px;
        }

        /* 能力介绍卡片 — 纯文字简介 + 技能集群 */
        .capabilities {
            background: rgba(255,255,255,0.5);
            border-radius: 2.5rem;
            padding: 2rem 2.2rem;
            margin: 2rem 0 2.2rem;
            border: 1px solid rgba(255,255,255,0.8);
            box-shadow: 0 8px 18px -10px rgba(0,60,120,0.2);
        }

        .bio-statement {
            font-size: 1.2rem;
            line-height: 1.6;
            color: #173f5c;
            margin-bottom: 2rem;
            font-weight: 400;
            padding: 0 0.5rem;
            border-left: 5px solid #2b6c9e;
            padding-left: 1.5rem;
            background: rgba(230, 244, 255, 0.4);
            border-radius: 0 1.5rem 1.5rem 0;
        }

        .skill-clusters {
            display: flex;
            flex-direction: column;
            gap: 1.8rem;
        }

        .cluster h3 {
            font-size: 1.3rem;
            font-weight: 600;
            color: #0f3b5c;
            margin-bottom: 1.2rem;
            display: flex;
            align-items: center;
            gap: 8px;
            border-bottom: 2px solid rgba(0,110,230,0.2);
            padding-bottom: 0.4rem;
        }

        .skill-tag-list {
            display: flex;
            flex-wrap: wrap;
            gap: 0.7rem 0.9rem;
        }

        .skill-tag {
            background: white;
            padding: 0.4rem 1.3rem;
            border-radius: 40px;
            font-size: 0.95rem;
            font-weight: 500;
            color: #1e4d77;
            box-shadow: 0 2px 6px rgba(0,40,70,0.08);
            border: 1px solid rgba(0,110,230,0.2);
            transition: 0.1s ease;
        }

        .skill-tag.foc {
            background: #0f334d;
            color: white;
            border: none;
            font-weight: 600;
        }

        .skill-tag:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 14px -8px #1e5a8b;
        }

        /* 软件图标大展 — 重点！使用常用软件列表 */
        .software-icons {
            margin: 2.5rem 0 1rem;
        }

        .software-icons h2 {
            font-size: 1.6rem;
            font-weight: 600;
            color: #103956;
            margin-bottom: 1.6rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .icon-grid {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: center;
            gap: 22px 28px;
            background: rgba(255, 255, 255, 0.4);
            padding: 2rem 2rem;
            border-radius: 4rem;
            border: 1px solid rgba(255,255,255,0.8);
        }

        .icon-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 6px;
            font-size: 0.8rem;
            font-weight: 500;
            color: #1f4a6e;
            min-width: 70px;
        }

        .icon-item img {
            width: 52px;
            height: 52px;
            object-fit: contain;
            filter: drop-shadow(0 6px 10px rgba(0,50,90,0.15));
            transition: transform 0.2s;
            background: white;
            border-radius: 16px;
            padding: 8px;
            border: 1px solid rgba(0,110,230,0.2);
        }

        .icon-item img:hover {
            transform: scale(1.1);
            background: #f0f8ff;
            border-color: #4090d0;
        }

        /* fallback 文字图标 (部分图标可能无法加载，显示文字) */
        .icon-item .fallback {
            width: 52px;
            height: 52px;
            background: #d9e9ff;
            border-radius: 16px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            font-size: 0.8rem;
            color: #1f4a72;
            border: 1px solid #a0c4ff;
        }

        .footer-hint {
            margin-top: 2rem;
            text-align: center;
            font-size: 0.9rem;
            color: #2f5a7a;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-top: 1px dashed rgba(0,80,150,0.25);
            padding-top: 1.5rem;
        }

        .footer-hint a {
            background: #123e5e;
            color: white;
            padding: 0.3rem 2rem;
            border-radius: 40px;
            text-decoration: none;
            font-weight: 500;
        }
    </style>
</head>
<body>
    <div class="profile-card">
        <!-- 头部：昵称 + 联系方式 (无项目说明) -->
        <div class="hero">
            <div class="name-title">
                星必尘Sguan <span>FOC / 电机控制</span>
            </div>
            <div class="quick-contact">
                <a href="#" class="email-chip">📧 3464647102@qq.com</a>
                <a href="https://github.com/Sguan-ZhouQing" target="_blank">🐙 GitHub</a>
                <a href="https://oshwhub.com/sguan606" target="_blank">⚡ 硬件开源</a>
            </div>
        </div>

        <!-- 个人能力介绍 (精炼, 无项目经历) -->
        <div class="capabilities">
            <div class="bio-statement">
                ▍ 扎实电机理论 · 专注永磁同步电机无感控制 (FOC) 。<br>
                ▍ 嵌入式全栈：ARM/DSP/RISC-V，C解决工程难题；PCB设计、总线通信、实时系统。<br>
                ▍ 控制理论深度：自控/现控，PID/LADRC整定，Simulink仿真。团队队长，乐观抗压，AI提效。
            </div>

            <div class="skill-clusters">
                <!-- 领域专长集群 (无项目，只有能力标签) -->
                <div class="cluster">
                    <h3>⚡ 电机·控制专长</h3>
                    <div class="skill-tag-list">
                        <span class="skill-tag foc">BLDC/PMSM 无感FOC</span>
                        <span class="skill-tag foc">HFI 高频注入</span>
                        <span class="skill-tag foc">SMO 滑模观测器</span>
                        <span class="skill-tag foc">PLL 锁相环</span>
                        <span class="skill-tag foc">弱磁控制 (FW)</span>
                        <span class="skill-tag foc">MTPA</span>
                        <span class="skill-tag">PID / LADRC 整定</span>
                        <span class="skill-tag">巴特沃斯滤波</span>
                        <span class="skill-tag">状态机调度</span>
                        <span class="skill-tag">Simulink 仿真</span>
                    </div>
                </div>

                <div class="cluster">
                    <h3>🔧 嵌入式 & 硬件</h3>
                    <div class="skill-tag-list">
                        <span class="skill-tag">STM32F1/F4/G4</span>
                        <span class="skill-tag">GD32</span>
                        <span class="skill-tag">DSP28335</span>
                        <span class="skill-tag">RISC-V</span>
                        <span class="skill-tag">FreeRTOS/UCOS</span>
                        <span class="skill-tag">CAN/CANopen CIA402</span>
                        <span class="skill-tag">Modbus / EtherCAT</span>
                        <span class="skill-tag">I2C/SPI/USART</span>
                        <span class="skill-tag">PCB 原理图/Layout</span>
                        <span class="skill-tag">LVGL 交互</span>
                        <span class="skill-tag">看门狗/互斥锁</span>
                    </div>
                </div>

                <div class="cluster">
                    <h3>📐 设计 & 仿真</h3>
                    <div class="skill-tag-list">
                        <span class="skill-tag">SOLIDWORKS</span>
                        <span class="skill-tag">嘉立创EDA</span>
                        <span class="skill-tag">MATLAB/Simulink</span>
                        <span class="skill-tag">Mathematica</span>
                        <span class="skill-tag">NanoEdge AI</span>
                    </div>
                </div>
            </div>
        </div>

        <!-- ★ 重点：软件图标展示区 (按照提供列表，完全展示) -->
        <div class="software-icons">
            <h2>🛠️ 日常工具箱 · 软件与环境</h2>
            <div class="icon-grid">
                <!-- 使用本地fallback, 但保留图标地址。若无法加载则显示文字。每个都包装为icon-item -->
                <!-- Keil uVision5 -->
                <div class="icon-item">
                    <img src="https://cdn.jsdelivr.net/gh/sun0225SUN/sun0225SUN/assets/images/keil.webp" alt="Keil" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                    <div class="fallback" style="display: none;">Keil</div>
                    <span>Keil uVision5</span>
                </div>
                <!-- STM32CubeMX -->
                <div class="icon-item">
                    <img src="https://cdn.jsdelivr.net/gh/sun0225SUN/sun0225SUN/assets/images/stm32cubemx.webp" alt="CubeMX" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                    <div class="fallback" style="display: none;">CubeMX</div>
                    <span>STM32CubeMX</span>
                </div>
                <!-- MounRiver Studio -->
                <div class="icon-item">
                    <div class="fallback" style="display: flex;">MounRiver</div>
                    <span>MounRiver Studio</span>
                </div>
                <!-- EmbeddedBuilder -->
                <div class="icon-item">
                    <div class="fallback" style="display: flex;">EmbeddedBuilder</div>
                    <span>EmbeddedBuilder</span>
                </div>
                <!-- Thonny -->
                <div class="icon-item">
                    <div class="fallback" style="display: flex;">Thonny</div>
                    <span>Thonny</span>
                </div>
                <!-- CCS IDE -->
                <div class="icon-item">
                    <img src="https://cdn.jsdelivr.net/gh/sun0225SUN/sun0225SUN/assets/images/ccs.webp" alt="CCS" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                    <div class="fallback" style="display: none;">CCS</div>
                    <span>CCS IDE</span>
                </div>
                <!-- VS Code -->
                <div class="icon-item">
                    <img src="https://cdn.jsdelivr.net/gh/sun0225SUN/sun0225SUN/assets/images/vscode.webp" alt="VS Code" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                    <div class="fallback" style="display: none;">VS Code</div>
                    <span>VS Code</span>
                </div>
                <!-- Arduino IDE -->
                <div class="icon-item">
                    <img src="https://cdn.jsdelivr.net/gh/sun0225SUN/sun0225SUN/assets/images/arduino.webp" alt="Arduino" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                    <div class="fallback" style="display: none;">Arduino</div>
                    <span>Arduino IDE</span>
                </div>
                <!-- HBuilder X -->
                <div class="icon-item">
                    <div class="fallback" style="display: flex;">HBuilder X</div>
                    <span>HBuilder X</span>
                </div>
                <!-- NanoEdge AI Studio -->
                <div class="icon-item">
                    <div class="fallback" style="display: flex;">NanoEdge AI</div>
                    <span>NanoEdge AI Studio</span>
                </div>
                <!-- SOLIDWORKS -->
                <div class="icon-item">
                    <img src="https://cdn.jsdelivr.net/gh/sun0225SUN/sun0225SUN/assets/images/solidworks.webp" alt="SOLIDWORKS" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                    <div class="fallback" style="display: none;">SW</div>
                    <span>SOLIDWORKS</span>
                </div>
                <!-- 嘉立创EDA -->
                <div class="icon-item">
                    <div class="fallback" style="display: flex;">嘉立创EDA</div>
                    <span>嘉立创EDA</span>
                </div>
                <!-- MATLAB -->
                <div class="icon-item">
                    <img src="https://cdn.jsdelivr.net/gh/sun0225SUN/sun0225SUN/assets/images/matlab.webp" alt="MATLAB" onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
                    <div class="fallback" style="display: none;">MATLAB</div>
                    <span>MATLAB</span>
                </div>
                <!-- Mathematica -->
                <div class="icon-item">
                    <div class="fallback" style="display: flex;">Mathematica</div>
                    <span>Mathematica</span>
                </div>
                <!-- 额外补一个通用的FOC标识, 可以不放软件但作为氛围 -->
                <div class="icon-item">
                    <div class="fallback" style="background:#0f334d; color:white; border:none;">FOC</div>
                    <span>核心算法</span>
                </div>
            </div>
        </div>

        <!-- 非常轻的脚注，仅包含指向性，没有项目描述 -->
        <div class="footer-hint">
            <div>⚡ 电机控制 · 无感FOC 深度实践 · 星必尘Sguan</div>
            <a href="https://github.com/Sguan-ZhouQing?tab=repositories" target="_blank">📌 更多仓库</a>
        </div>
    </div>

    <script>
        // 后备显示：如果图片加载失败，显示fallback文本
        document.querySelectorAll('.icon-item img').forEach(img => {
            img.addEventListener('error', function() {
                this.style.display = 'none';
                const fallback = this.nextElementSibling;
                if (fallback && fallback.classList.contains('fallback')) {
                    fallback.style.display = 'flex';
                }
            });
        });
    </script>
</body>
</html>
