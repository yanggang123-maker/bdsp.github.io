<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>北斗空间技术应用</title>
    <!-- 引入Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- 引入Font Awesome -->
    <link href="https://cdn.jsdelivr.net/npm/font-awesome@4.7.0/css/font-awesome.min.css" rel="stylesheet">
    <!-- 配置Tailwind自定义颜色 -->
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        primary: '#0C4DA2',       // 北斗蓝 - 主色调
                        secondary: '#FF7D00',     // 辅助色 - 橙色
                        dark: '#1A1A2E',          // 深色背景
                        light: '#F5F7FA',         // 浅色背景
                    },
                    fontFamily: {
                        sans: ['Inter', 'system-ui', 'sans-serif'],
                    },
                }
            }
        }
    </script>
    <!-- 自定义工具类 -->
    <style type="text/tailwindcss">
        @layer utilities {
            .content-auto {
                content-visibility: auto;
            }
            .text-shadow {
                text-shadow: 0 2px 4px rgba(0,0,0,0.1);
            }
            .transition-custom {
                transition: all 0.3s ease-in-out;
            }
        }
    </style>
    <style>
        /* 平滑滚动 */
        html {
            scroll-behavior: smooth;
        }
        
        /* 动画效果 */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .animate-fadeIn {
            animation: fadeIn 0.6s ease-out forwards;
        }
        
        .delay-100 { animation-delay: 0.1s; }
        .delay-200 { animation-delay: 0.2s; }
        .delay-300 { animation-delay: 0.3s; }
        .delay-400 { animation-delay: 0.4s; }
        .delay-500 { animation-delay: 0.5s; }
    </style>
</head>
<body class="bg-light text-gray-800 overflow-x-hidden">
    <!-- 导航栏 -->
    <header id="navbar" class="fixed w-full z-50 transition-all duration-300 bg-white/90 backdrop-blur-sm shadow-sm">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center py-4">
                <!-- Logo -->
                <div class="flex items-center space-x-2">
                    <div class="w-10 h-10 bg-primary rounded-lg flex items-center justify-center">
                        <i class="fa fa-compass text-white text-xl"></i>
                    </div>
                    <span class="text-xl font-bold text-primary">北斗空间技术</span>
                </div>
                
                <!-- 桌面端导航 -->
                <nav class="hidden md:flex space-x-8">
                    <a href="#home" class="nav-link text-gray-700 hover:text-primary font-medium transition-custom">首页</a>
                    <a href="#about" class="nav-link text-gray-700 hover:text-primary font-medium transition-custom">关于我们</a>
                    <a href="#products" class="nav-link text-gray-700 hover:text-primary font-medium transition-custom">核心产品</a>
                    <a href="#applications" class="nav-link text-gray-700 hover:text-primary font-medium transition-custom">行业应用</a>
                    <a href="#cases" class="nav-link text-gray-700 hover:text-primary font-medium transition-custom">典型案例</a>
                    <a href="team.html" target="_blank" class="nav-link text-gray-700 hover:text-primary font-medium transition-custom">核心团队</a>
                </nav>
                
                <!-- 联系按钮 -->
                <div class="hidden md:block">
                    <a href="#contact" class="bg-primary hover:bg-primary/90 text-white px-5 py-2 rounded-lg font-medium transition-custom shadow-md hover:shadow-lg">
                        联系我们
                    </a>
                </div>
                
                <!-- 移动端菜单按钮 -->
                <button id="menuBtn" class="md:hidden text-gray-700 focus:outline-none">
                    <i class="fa fa-bars text-2xl"></i>
                </button>
            </div>
        </div>
        
        <!-- 移动端导航菜单 -->
        <div id="mobileMenu" class="md:hidden hidden bg-white border-t animate-fadeIn">
            <div class="container mx-auto px-4 py-3 space-y-3">
                <a href="#home" class="block py-2 text-gray-700 hover:text-primary font-medium">首页</a>
                <a href="#about" class="block py-2 text-gray-700 hover:text-primary font-medium">关于我们</a>
                <a href="#products" class="block py-2 text-gray-700 hover:text-primary font-medium">核心产品</a>
                <a href="#applications" class="block py-2 text-gray-700 hover:text-primary font-medium">行业应用</a>
                <a href="#cases" class="block py-2 text-gray-700 hover:text-primary font-medium">典型案例</a>
                <a href="team.html" target="_blank" class="block py-2 text-gray-700 hover:text-primary font-medium">核心团队</a>
                <a href="#contact" class="block py-2 text-center bg-primary text-white rounded-lg font-medium">联系我们</a>
            </div>
        </div>
    </header>

    <!-- 英雄区域 -->
    <section id="home" class="pt-24 pb-16 md:pt-32 md:pb-24 bg-gradient-to-br from-primary/5 to-primary/10">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex flex-col lg:flex-row items-center">
                <div class="lg:w-1/2 mb-10 lg:mb-0 animate-fadeIn">
                    <h1 class="text-[clamp(2rem,5vw,3.5rem)] font-bold leading-tight text-gray-900 mb-6">
                        北斗空间技术<br>
                        <span class="text-primary">赋能智能未来</span>
                    </h1>
                    <p class="text-lg md:text-xl text-gray-600 mb-8 max-w-lg">
                        专注于北斗卫星导航系统应用解决方案，为各行业提供高精度定位、导航与授时服务。
                    </p>
                    <div class="flex flex-col sm:flex-row gap-4">
                        <a href="#products" class="bg-primary hover:bg-primary/90 text-white px-8 py-3 rounded-lg font-medium text-center transition-custom shadow-lg hover:shadow-xl transform hover:-translate-y-1">
                            探索产品
                        </a>
                        <a href="#contact" class="bg-white border-2 border-primary text-primary hover:bg-primary/5 px-8 py-3 rounded-lg font-medium text-center transition-custom shadow-md hover:shadow-lg transform hover:-translate-y-1">
                            咨询方案
                        </a>
                    </div>
                    
                    <!-- 数据统计 -->
                    <div class="flex flex-wrap gap-8 mt-12">
                        <div>
                            <div class="text-3xl md:text-4xl font-bold text-primary">10+</div>
                            <div class="text-gray-600">行业解决方案</div>
                        </div>
                        <div>
                            <div class="text-3xl md:text-4xl font-bold text-primary">50+</div>
                            <div class="text-gray-600">成功案例</div>
                        </div>
                        <div>
                            <div class="text-3xl md:text-4xl font-bold text-primary">150+</div>
                            <div class="text-gray-600">合作伙伴</div>
                        </div>
                    </div>
                </div>
                
                <div class="lg:w-1/2 animate-fadeIn delay-300">
                    <div class="relative">
                        <div class="absolute -inset-4 bg-primary/10 rounded-2xl transform rotate-3"></div>
                        <img src="https://picsum.photos/id/1/600/400" alt="北斗空间技术应用展示" class="relative rounded-xl shadow-xl w-full h-auto object-cover">
                        <div class="absolute -bottom-6 -left-6 bg-white p-4 rounded-lg shadow-lg">
                            <div class="flex items-center space-x-2">
                                <div class="w-10 h-10 bg-green-100 rounded-full flex items-center justify-center text-green-600">
                                    <i class="fa fa-check"></i>
                                </div>
                                <div>
                                    <div class="font-bold">高精度定位</div>
                                    <div class="text-sm text-gray-500">厘米级定位精度</div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 合作伙伴 -->
    <section class="py-12 bg-white">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <p class="text-center text-gray-500 mb-8">值得信赖的合作伙伴</p>
            <div class="flex flex-wrap justify-center items-center gap-8 md:gap-16">
                <div class="grayscale hover:grayscale-0 transition-custom opacity-70 hover:opacity-100">
                    <i class="fa fa-building text-4xl text-gray-400"></i>
                    <div class="mt-2 text-gray-500">中国电建</div>
                </div>
                <div class="grayscale hover:grayscale-0 transition-custom opacity-70 hover:opacity-100">
                    <i class="fa fa-building text-4xl text-gray-400"></i>
                    <div class="mt-2 text-gray-500">华为</div>
                </div>
                <div class="grayscale hover:grayscale-0 transition-custom opacity-70 hover:opacity-100">
                    <i class="fa fa-building text-4xl text-gray-400"></i>
                    <div class="mt-2 text-gray-500">中国能建</div>
                </div>
                <div class="grayscale hover:grayscale-0 transition-custom opacity-70 hover:opacity-100">
                    <i class="fa fa-building text-4xl text-gray-400"></i>
                    <div class="mt-2 text-gray-500">浪潮集团</div>
                </div>
                <div class="grayscale hover:grayscale-0 transition-custom opacity-70 hover:opacity-100">
                    <i class="fa fa-building text-4xl text-gray-400"></i>
                    <div class="mt-2 text-gray-500">中科云图</div>
                </div>
            </div>
        </div>
    </section>

    <!-- 关于我们 -->
    <section id="about" class="py-20 bg-gray-50">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <h2 class="text-[clamp(1.8rem,4vw,2.5rem)] font-bold text-gray-900 mb-4">关于贵州北斗空间</h2>
                <div class="w-20 h-1 bg-primary mx-auto mb-6"></div>
                <p class="text-gray-600 text-lg">
                    贵州北斗空间技术有限公司是国内领先的北斗卫星导航应用解决方案提供商，致力于为各行业提供高精度定位服务。
                </p>
            </div>
            
            <div class="flex flex-col lg:flex-row gap-12 items-center">
                <div class="lg:w-1/2 animate-fadeIn">
                    <div class="relative">
                        <img src="https://picsum.photos/id/20/600/400" alt="北斗空间技术公司环境" class="rounded-xl shadow-lg w-full h-auto">
                        <div class="absolute -bottom-6 -right-6 bg-primary text-white p-6 rounded-lg shadow-lg max-w-xs">
                            <p class="text-lg font-bold mb-2">我们的使命</p>
                            <p>以北斗技术为核心，推动空间信息产业创新发展，为智慧社会建设提供有力支撑。</p>
                        </div>
                    </div>
                </div>
                
                <div class="lg:w-1/2 animate-fadeIn delay-200">
                    <h3 class="text-2xl font-bold mb-6 text-gray-800">公司简介</h3>
                    <p class="text-gray-600 mb-6 leading-relaxed">
                        贵州北斗空间技术有限公司成立于2013年，是一家专注于北斗卫星导航系统应用研发与推广的高新技术企业。公司拥有一支由卫星导航、地理信息、物联网等领域专家组成的专业团队，具备丰富的行业经验和技术积累。
                    </p>
                    <p class="text-gray-600 mb-8 leading-relaxed">
                        多年来，公司始终坚持技术创新，先后研发出一系列具有自主知识产权的北斗应用产品，广泛应用于交通、测绘、农业、林业、渔业、气象等多个领域，为用户提供了高质量的定位、导航、授时及相关信息服务。
                    </p>
                    
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-8">
                        <div class="flex items-start space-x-4">
                            <div class="mt-1 text-primary text-xl">
                                <i class="fa fa-lightbulb-o"></i>
                            </div>
                            <div>
                                <h4 class="font-bold text-lg mb-2">技术创新</h4>
                                <p class="text-gray-600">持续投入研发，保持技术领先</p>
                            </div>
                        </div>
                        <div class="flex items-start space-x-4">
                            <div class="mt-1 text-primary text-xl">
                                <i class="fa fa-users"></i>
                            </div>
                            <div>
                                <h4 class="font-bold text-lg mb-2">专业团队</h4>
                                <p class="text-gray-600">行业专家领衔，经验丰富</p>
                            </div>
                        </div>
                        <div class="flex items-start space-x-4">
                            <div class="mt-1 text-primary text-xl">
                                <i class="fa fa-handshake-o"></i>
                            </div>
                            <div>
                                <h4 class="font-bold text-lg mb-2">诚信为本</h4>
                                <p class="text-gray-600">恪守承诺，值得信赖</p>
                            </div>
                        </div>
                        <div class="flex items-start space-x-4">
                            <div class="mt-1 text-primary text-xl">
                                <i class="fa fa-cogs"></i>
                            </div>
                            <div>
                                <h4 class="font-bold text-lg mb-2">优质服务</h4>
                                <p class="text-gray-600">全方位支持，贴心服务</p>
                            </div>
                        </div>
                    </div>
                    
                    <a href="team.html" target="_blank" class="inline-flex items-center text-primary font-medium hover:text-primary/80 transition-custom">
                        了解更多团队信息 <i class="fa fa-arrow-right ml-2"></i>
                    </a>
                </div>
            </div>
        </div>
    </section>

    <!-- 核心产品 -->
    <section id="products" class="py-20 bg-white">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <h2 class="text-[clamp(1.8rem,4vw,2.5rem)] font-bold text-gray-900 mb-4">核心产品</h2>
                <div class="w-20 h-1 bg-primary mx-auto mb-6"></div>
                <p class="text-gray-600 text-lg">
                    我们提供一系列基于北斗卫星导航系统的高精度定位产品，满足不同行业的应用需求。
                </p>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                <!-- 产品1 -->
                <div class="bg-gray-50 rounded-xl overflow-hidden shadow-md hover:shadow-xl transition-custom transform hover:-translate-y-2 group">
                    <div class="h-52 overflow-hidden">
                        <img src="https://picsum.photos/id/96/600/400" alt="北斗高精度定位终端" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-6">
                        <div class="inline-block bg-primary/10 text-primary px-3 py-1 rounded-full text-sm font-medium mb-4">
                            定位终端
                        </div>
                        <h3 class="text-xl font-bold mb-3 text-gray-800">北斗高精度定位终端</h3>
                        <p class="text-gray-600 mb-4">
                            采用北斗/GPS双模定位技术，提供厘米级定位精度，适用于测绘、工程测量、精准农业等领域。
                        </p>
                        <ul class="space-y-2 mb-6">
                            <li class="flex items-center text-gray-600">
                                <i class="fa fa-check text-green-500 mr-2"></i>
                                定位精度：水平±1cm，垂直±2cm
                            </li>
                            <li class="flex items-center text-gray-600">
                                <i class="fa fa-check text-green-500 mr-2"></i>
                                支持北斗、GPS、GLONASS多系统
                            </li>
                            <li class="flex items-center text-gray-600">
                                <i class="fa fa-check text-green-500 mr-2"></i>
                                IP67级防水防尘
                            </li>
                        </ul>
                        <a href="javascript:void(0);" class="inline-flex items-center text-primary font-medium hover:text-primary/80 transition-custom">
                            查看详情 <i class="fa fa-arrow-right ml-2"></i>
                        </a>
                    </div>
                </div>
                
                <!-- 产品2 -->
                <div class="bg-gray-50 rounded-xl overflow-hidden shadow-md hover:shadow-xl transition-custom transform hover:-translate-y-2 group">
                    <div class="h-52 overflow-hidden">
                        <img src="https://picsum.photos/id/251/600/400" alt="北斗导航模块" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-6">
                        <div class="inline-block bg-primary/10 text-primary px-3 py-1 rounded-full text-sm font-medium mb-4">
                            导航模块
                        </div>
                        <h3 class="text-xl font-bold mb-3 text-gray-800">北斗导航模块</h3>
                        <p class="text-gray-600 mb-4">
                            小型化、低功耗北斗导航模块，可集成于各类设备中，提供稳定可靠的定位导航服务。
                        </p>
                        <ul class="space-y-2 mb-6">
                            <li class="flex items-center text-gray-600">
                                <i class="fa fa-check text-green-500 mr-2"></i>
                                尺寸小巧：16mm×12mm
                            </li>
                            <li class="flex items-center text-gray-600">
                                <i class="fa fa-check text-green-500 mr-2"></i>
                                低功耗设计，延长设备续航
                            </li>
                            <li class="flex items-center text-gray-600">
                                <i class="fa fa-check text-green-500 mr-2"></i>
                                支持多种接口输出
                            </li>
                        </ul>
                        <a href="javascript:void(0);" class="inline-flex items-center text-primary font-medium hover:text-primary/80 transition-custom">
                            查看详情 <i class="fa fa-arrow-right ml-2"></i>
                        </a>
                    </div>
                </div>
                
                <!-- 产品3 -->
                <div class="bg-gray-50 rounded-xl overflow-hidden shadow-md hover:shadow-xl transition-custom transform hover:-translate-y-2 group">
                    <div class="h-52 overflow-hidden">
                        <img src="https://picsum.photos/id/180/600/400" alt="北斗位置服务平台" class="w-full h-full object-cover group-hover:scale-105 transition-transform duration-500">
                    </div>
                    <div class="p-6">
                        <div class="inline-block bg-primary/10 text-primary px-3 py-1 rounded-full text-sm font-medium mb-4">
                            软件平台
                        </div>
                        <h3 class="text-xl font-bold mb-3 text-gray-800">北斗位置服务平台</h3>
                        <p class="text-gray-600 mb-4">
                            基于云计算和大数据技术的位置服务平台，支持大规模终端接入和数据管理分析。
                        </p>
                        <ul class="space-y-2 mb-6">
                            <li class="flex items-center text-gray-600">
                                <i class="fa fa-check text-green-500 mr-2"></i>
                                支持百万级终端接入
                            </li>
                            <li class="flex items-center text-gray-600">
                                <i class="fa fa-check text-green-500 mr-2"></i>
                                实时监控与数据分析
                            </li>
                            <li class="flex items-center text-gray-600">
                                <i class="fa fa-check text-green-500 mr-2"></i>
                                开放API，易于二次开发
                            </li>
                        </ul>
                        <a href="javascript:void(0);" class="inline-flex items-center text-primary font-medium hover:text-primary/80 transition-custom">
                            查看详情 <i class="fa fa-arrow-right ml-2"></i>
                        </a>
                    </div>
                </div>
            </div>
            
            <div class="text-center mt-12">
                <a href="javascript:void(0);" class="inline-block border-2 border-primary text-primary hover:bg-primary hover:text-white px-8 py-3 rounded-lg font-medium transition-custom">
                    查看全部产品
                </a>
            </div>
        </div>
    </section>

    <!-- 行业应用 -->
    <section id="applications" class="py-20 bg-gradient-to-br from-primary/5 to-primary/10">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <h2 class="text-[clamp(1.8rem,4vw,2.5rem)] font-bold text-gray-900 mb-4">行业应用</h2>
                <div class="w-20 h-1 bg-primary mx-auto mb-6"></div>
                <p class="text-gray-600 text-lg">
                    北斗空间技术广泛应用于多个行业，为各领域提供精准、高效的位置服务解决方案。
                </p>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-2 gap-8 lg:gap-12">
                <!-- 应用领域1 -->
                <div class="flex flex-col md:flex-row gap-6 bg-white p-6 rounded-xl shadow-md hover:shadow-lg transition-custom">
                    <div class="md:w-1/3">
                        <div class="bg-primary/10 rounded-lg h-full flex items-center justify-center p-4">
                            <i class="fa fa-car text-5xl text-primary"></i>
                        </div>
                    </div>
                    <div class="md:w-2/3">
                        <h3 class="text-xl font-bold mb-3 text-gray-800">智能交通</h3>
                        <p class="text-gray-600 mb-4">
                            基于北斗高精度定位技术，实现车辆实时监控、调度管理、自动驾驶等功能，提高交通效率和安全性。
                        </p>
                        <a href="javascript:void(0);" class="inline-flex items-center text-primary font-medium hover:text-primary/80 transition-custom">
                            了解更多 <i class="fa fa-arrow-right ml-2"></i>
                        </a>
                    </div>
                </div>
                
                <!-- 应用领域2 -->
                <div class="flex flex-col md:flex-row gap-6 bg-white p-6 rounded-xl shadow-md hover:shadow-lg transition-custom">
                    <div class="md:w-1/3">
                        <div class="bg-primary/10 rounded-lg h-full flex items-center justify-center p-4">
                            <i class="fa fa-tree text-5xl text-primary"></i>
                        </div>
                    </div>
                    <div class="md:w-2/3">
                        <h3 class="text-xl font-bold mb-3 text-gray-800">精准农业</h3>
                        <p class="text-gray-600 mb-4">
                            结合北斗定位与物联网技术，实现农田精准播种、施肥、灌溉和收割，提高农业生产效率，节约资源。
                        </p>
                        <a href="javascript:void(0);" class="inline-flex items-center text-primary font-medium hover:text-primary/80 transition-custom">
                            了解更多 <i class="fa fa-arrow-right ml-2"></i>
                        </a>
                    </div>
                </div>
                
                <!-- 应用领域3 -->
                <div class="flex flex-col md:flex-row gap-6 bg-white p-6 rounded-xl shadow-md hover:shadow-lg transition-custom">
                    <div class="md:w-1/3">
                        <div class="bg-primary/10 rounded-lg h-full flex items-center justify-center p-4">
                            <i class="fa fa-ship text-5xl text-primary"></i>
                        </div>
                    </div>
                    <div class="md:w-2/3">
                        <h3 class="text-xl font-bold mb-3 text-gray-800">海洋渔业</h3>
                        <p class="text-gray-600 mb-4">
                            为渔船提供精准导航、渔区划定、避碰预警等服务，保障渔船航行安全，提高渔业生产效率。
                        </p>
                        <a href="javascript:void(0);" class="inline-flex items-center text-primary font-medium hover:text-primary/80 transition-custom">
                            了解更多 <i class="fa fa-arrow-right ml-2"></i>
                        </a>
                    </div>
                </div>
                
                <!-- 应用领域4 -->
                <div class="flex flex-col md:flex-row gap-6 bg-white p-6 rounded-xl shadow-md hover:shadow-lg transition-custom">
                    <div class="md:w-1/3">
                        <div class="bg-primary/10 rounded-lg h-full flex items-center justify-center p-4">
                            <i class="fa fa-road text-5xl text-primary"></i>
                        </div>
                    </div>
                    <div class="md:w-2/3">
                        <h3 class="text-xl font-bold mb-3 text-gray-800">工程建设</h3>
                        <p class="text-gray-600 mb-4">
                            在道路、桥梁、隧道等工程建设中提供高精度测量、施工监控和变形监测等服务，确保工程质量。
                        </p>
                        <a href="javascript:void(0);" class="inline-flex items-center text-primary font-medium hover:text-primary/80 transition-custom">
                            了解更多 <i class="fa fa-arrow-right ml-2"></i>
                        </a>
                    </div>
                </div>
                
                <!-- 应用领域5 -->
                <div class="flex flex-col md:flex-row gap-6 bg-white p-6 rounded-xl shadow-md hover:shadow-lg transition-custom">
                    <div class="md:w-1/3">
                        <div class="bg-primary/10 rounded-lg h-full flex items-center justify-center p-4">
                            <i class="fa fa-globe text-5xl text-primary"></i>
                        </div>
                    </div>
                    <div class="md:w-2/3">
                        <h3 class="text-xl font-bold mb-3 text-gray-800">测绘地理信息</h3>
                        <p class="text-gray-600 mb-4">
                            提供高精度定位服务，用于地形图测绘、地籍测量、不动产登记等领域，提高测绘效率和精度。
                        </p>
                        <a href="javascript:void(0);" class="inline-flex items-center text-primary font-medium hover:text-primary/80 transition-custom">
                            了解更多 <i class="fa fa-arrow-right ml-2"></i>
                        </a>
                    </div>
                </div>
                
                <!-- 应用领域6 -->
                <div class="flex flex-col md:flex-row gap-6 bg-white p-6 rounded-xl shadow-md hover:shadow-lg transition-custom">
                    <div class="md:w-1/3">
                        <div class="bg-primary/10 rounded-lg h-full flex items-center justify-center p-4">
                            <i class="fa fa-medkit text-5xl text-primary"></i>
                        </div>
                    </div>
                    <div class="md:w-2/3">
                        <h3 class="text-xl font-bold mb-3 text-gray-800">应急救援</h3>
                        <p class="text-gray-600 mb-4">
                            在灾害救援中提供精准定位和导航服务，提高救援效率，保障救援人员安全，减少灾害损失。
                        </p>
                        <a href="javascript:void(0);" class="inline-flex items-center text-primary font-medium hover:text-primary/80 transition-custom">
                            了解更多 <i class="fa fa-arrow-right ml-2"></i>
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 典型案例 -->
    <section id="cases" class="py-20 bg-white">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <h2 class="text-[clamp(1.8rem,4vw,2.5rem)] font-bold text-gray-900 mb-4">典型案例</h2>
                <div class="w-20 h-1 bg-primary mx-auto mb-6"></div>
                <p class="text-gray-600 text-lg">
                    我们已为众多行业客户提供了北斗应用解决方案，以下是部分典型案例。
                </p>
            </div>
            
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-10">
                <!-- 案例1 -->
                <div class="group">
                    <div class="relative overflow-hidden rounded-xl mb-6">
                        <img src="https://picsum.photos/id/1031/800/500" alt="智能交通管理系统" class="w-full h-80 object-cover transition-transform duration-500 group-hover:scale-105">
                        <div class="absolute inset-0 bg-gradient-to-t from-black/70 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-end">
                            <div class="p-6 text-white">
                                <div class="flex space-x-2 mb-3">
                                    <span class="bg-primary text-white text-xs px-2 py-1 rounded">智能交通</span>
                                    <span class="bg-gray-700 text-white text-xs px-2 py-1 rounded">2023年</span>
                                </div>
                                <p class="text-sm">为某城市提供智能交通管理系统，覆盖1000+路口，提升通行效率30%。</p>
                            </div>
                        </div>
                    </div>
                    <h3 class="text-xl font-bold mb-2 text-gray-800 group-hover:text-primary transition-custom">城市智能交通管理系统</h3>
                    <p class="text-gray-600 mb-4">
                        基于北斗高精度定位技术，构建城市交通综合管理平台，实现交通信号智能调控、交通流量监测和车辆精准导航。
                    </p>
                    <a href="javascript:void(0);" class="text-primary font-medium hover:text-primary/80 transition-custom inline-flex items-center">
                        查看详情 <i class="fa fa-long-arrow-right ml-2"></i>
                    </a>
                </div>
                
                <!-- 案例2 -->
                <div class="group">
                    <div class="relative overflow-hidden rounded-xl mb-6">
                        <img src="https://picsum.photos/id/133/800/500" alt="智慧农业示范基地" class="w-full h-80 object-cover transition-transform duration-500 group-hover:scale-105">
                        <div class="absolute inset-0 bg-gradient-to-t from-black/70 to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300 flex items-end">
                            <div class="p-6 text-white">
                                <div class="flex space-x-2 mb-3">
                                    <span class="bg-primary text-white text-xs px-2 py-1 rounded">精准农业</span>
                                    <span class="bg-gray-700 text-white text-xs px-2 py-1 rounded">2022年</span>
                                </div>
                                <p class="text-sm">在5000亩农田实现精准种植管理，节水30%，增产15%。</p>
                            </div>
                        </div>
                    </div>
                    <h3 class="text-xl font-bold mb-2 text-gray-800 group-hover:text-primary transition-custom">智慧农业示范基地</h3>
                    <p class="text-gray-600 mb-4">
                        为大型农场提供北斗智慧农业解决方案，实现农田精准管理、智能灌溉和自动化收割，大幅提升农业生产效率。
                    </p>
                    <a href="javascript:void(0);" class="text-primary font-medium hover:text-primary/80 transition-custom inline-flex items-center">
                        查看详情 <i class="fa fa-long-arrow-right ml-2"></i>
                    </a>
                </div>
            </div>
            
            <div class="text-center mt-12">
                <a href="javascript:void(0);" class="inline-block border-2 border-primary text-primary hover:bg-primary hover:text-white px-8 py-3 rounded-lg font-medium transition-custom">
                    查看更多案例
                </a>
            </div>
        </div>
    </section>

    <!-- 技术优势 -->
    <section class="py-20 bg-gray-900 text-white">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <h2 class="text-[clamp(1.8rem,4vw,2.5rem)] font-bold mb-4">技术优势</h2>
                <div class="w-20 h-1 bg-secondary mx-auto mb-6"></div>
                <p class="text-gray-300 text-lg">
                    我们拥有一支专业的技术团队，在北斗卫星导航应用领域积累了丰富的经验和核心技术。
                </p>
            </div>
            
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
                <!-- 优势1 -->
                <div class="bg-gray-800/50 p-8 rounded-xl hover:bg-gray-800 transition-custom transform hover:-translate-y-2">
                    <div class="w-14 h-14 bg-secondary/20 rounded-lg flex items-center justify-center mb-6">
                        <i class="fa fa-bullseye text-secondary text-2xl"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-4">高精度定位</h3>
                    <p class="text-gray-300">
                        采用先进的差分定位技术，实现厘米级至米级的定位精度，满足不同行业的应用需求。
                    </p>
                </div>
                
                <!-- 优势2 -->
                <div class="bg-gray-800/50 p-8 rounded-xl hover:bg-gray-800 transition-custom transform hover:-translate-y-2">
                    <div class="w-14 h-14 bg-secondary/20 rounded-lg flex items-center justify-center mb-6">
                        <i class="fa fa-clock-o text-secondary text-2xl"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-4">高可靠性</h3>
                    <p class="text-gray-300">
                        多系统融合定位，确保在复杂环境下仍能提供稳定可靠的定位服务，保障业务连续性。
                    </p>
                </div>
                
                <!-- 优势3 -->
                <div class="bg-gray-800/50 p-8 rounded-xl hover:bg-gray-800 transition-custom transform hover:-translate-y-2">
                    <div class="w-14 h-14 bg-secondary/20 rounded-lg flex items-center justify-center mb-6">
                        <i class="fa fa-bolt text-secondary text-2xl"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-4">低延迟响应</h3>
                    <p class="text-gray-300">
                        优化的数据处理算法，实现低延迟定位结果输出，满足实时监控和控制等应用场景。
                    </p>
                </div>
                
                <!-- 优势4 -->
                <div class="bg-gray-800/50 p-8 rounded-xl hover:bg-gray-800 transition-custom transform hover:-translate-y-2">
                    <div class="w-14 h-14 bg-secondary/20 rounded-lg flex items-center justify-center mb-6">
                        <i class="fa fa-cogs text-secondary text-2xl"></i>
                    </div>
                    <h3 class="text-xl font-bold mb-4">定制化能力</h3>
                    <p class="text-gray-300">
                        强大的技术研发团队，可根据客户需求提供定制化解决方案，满足个性化应用场景。
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- 联系我们 -->
    <section id="contact" class="py-20 bg-white">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="text-center max-w-3xl mx-auto mb-16">
                <h2 class="text-[clamp(1.8rem,4vw,2.5rem)] font-bold text-gray-900 mb-4">联系我们</h2>
                <div class="w-20 h-1 bg-primary mx-auto mb-6"></div>
                <p class="text-gray-600 text-lg">
                    无论您有任何疑问或需求，都可以通过以下方式联系我们，我们将尽快为您提供专业的服务。
                </p>
            </div>
            
            <div class="flex flex-col lg:flex-row gap-12">
                <div class="lg:w-1/2">
                    <div class="bg-gray-50 p-8 rounded-xl h-full">
                        <h3 class="text-2xl font-bold mb-6 text-gray-800">联系方式</h3>
                        
                        <div class="space-y-6 mb-8">
                            <div class="flex items-start space-x-4">
                                <div class="w-10 h-10 bg-primary/10 rounded-full flex items-center justify-center text-primary mt-1 flex-shrink-0">
                                    <i class="fa fa-map-marker"></i>
                                </div>
                                <div>
                                    <h4 class="font-bold text-gray-800 mb-1">公司地址</h4>
                                    <p class="text-gray-600">贵阳市有山基金大厦24楼</p>
                                </div>
                            </div>
                            
                            <div class="flex items-start space-x-4">
                                <div class="w-10 h-10 bg-primary/10 rounded-full flex items-center justify-center text-primary mt-1 flex-shrink-0">
                                    <i class="fa fa-phone"></i>
                                </div>
                                <div>
                                    <h4 class="font-bold text-gray-800 mb-1">联系电话</h4>
                                    <p class="text-gray-600">9090980</p>
                                </div>
                            </div>
                            
                            <div class="flex items-start space-x-4">
                                <div class="w-10 h-10 bg-primary/10 rounded-full flex items-center justify-center text-primary mt-1 flex-shrink-0">
                                    <i class="fa fa-envelope"></i>
                                </div>
                                <div>
                                    <h4 class="font-bold text-gray-800 mb-1">电子邮箱</h4>
                                    <p class="text-gray-600">contact@beidou-space.com</p>
                                </div>
                            </div>
                            
                            <div class="flex items-start space-x-4">
                                <div class="w-10 h-10 bg-primary/10 rounded-full flex items-center justify-center text-primary mt-1 flex-shrink-0">
                                    <i class="fa fa-clock-o"></i>
                                </div>
                                <div>
                                    <h4 class="font-bold text-gray-800 mb-1">工作时间</h4>
                                    <p class="text-gray-600">周一至周五: 9:00 - 18:00</p>
                                </div>
                            </div>
                        </div>
                        
                        <div>
                            <h4 class="font-bold text-gray-800 mb-4">关注我们</h4>
                            <div class="flex space-x-4">
                                <a href="javascript:void(0);" class="w-10 h-10 bg-primary/10 hover:bg-primary hover:text-white text-primary rounded-full flex items-center justify-center transition-custom">
                                    <i class="fa fa-weixin"></i>
                                </a>
                                <a href="javascript:void(0);" class="w-10 h-10 bg-primary/10 hover:bg-primary hover:text-white text-primary rounded-full flex items-center justify-center transition-custom">
                                    <i class="fa fa-weibo"></i>
                                </a>
                                <a href="javascript:void(0);" class="w-10 h-10 bg-primary/10 hover:bg-primary hover:text-white text-primary rounded-full flex items-center justify-center transition-custom">
                                    <i class="fa fa-linkedin"></i>
                                </a>
                                <a href="javascript:void(0);" class="w-10 h-10 bg-primary/10 hover:bg-primary hover:text-white text-primary rounded-full flex items-center justify-center transition-custom">
                                    <i class="fa fa-youtube-play"></i>
                                </a>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="lg:w-1/2">
                    <div class="bg-primary rounded-xl p-8 text-white">
                        <h3 class="text-2xl font-bold mb-6">发送消息</h3>
                        
                        <form>
                            <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-6">
                                <div>
                                    <label for="name" class="block mb-2 text-white/90">姓名</label>
                                    <input type="text" id="name" class="w-full px-4 py-3 rounded-lg bg-white/10 border border-white/20 text-white placeholder-white/50 focus:outline-none focus:ring-2 focus:ring-white/50" placeholder="请输入您的姓名">
                                </div>
                                <div>
                                    <label for="phone" class="block mb-2 text-white/90">电话</label>
                                    <input type="tel" id="phone" class="w-full px-4 py-3 rounded-lg bg-white/10 border border-white/20 text-white placeholder-white/50 focus:outline-none focus:ring-2 focus:ring-white/50" placeholder="请输入您的电话">
                                </div>
                            </div>
                            
                            <div class="mb-6">
                                <label for="email" class="block mb-2 text-white/90">邮箱</label>
                                <input type="email" id="email" class="w-full px-4 py-3 rounded-lg bg-white/10 border border-white/20 text-white placeholder-white/50 focus:outline-none focus:ring-2 focus:ring-white/50" placeholder="请输入您的邮箱">
                            </div>
                            
                            <div class="mb-6">
                                <label for="subject" class="block mb-2 text-white/90">主题</label>
                                <select id="subject" class="w-full px-4 py-3 rounded-lg bg-white/10 border border-white/20 text-white focus:outline-none focus:ring-2 focus:ring-white/50">
                                    <option value="" class="bg-primary">请选择咨询主题</option>
                                    <option value="product" class="bg-primary">产品咨询</option>
                                    <option value="solution" class="bg-primary">解决方案</option>
                                    <option value="cooperation" class="bg-primary">合作洽谈</option>
                                    <option value="other" class="bg-primary">其他问题</option>
                                </select>
                            </div>
                            
                            <div class="mb-6">
                                <label for="message" class="block mb-2 text-white/90">留言内容</label>
                                <textarea id="message" rows="5" class="w-full px-4 py-3 rounded-lg bg-white/10 border border-white/20 text-white placeholder-white/50 focus:outline-none focus:ring-2 focus:ring-white/50" placeholder="请输入您的留言内容"></textarea>
                            </div>
                            
                            <button type="submit" class="w-full bg-white text-primary hover:bg-white/90 font-bold py-3 px-6 rounded-lg transition-custom shadow-lg hover:shadow-xl transform hover:-translate-y-1">
                                发送消息
                            </button>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- 页脚 -->
    <footer class="bg-gray-900 text-white pt-16 pb-8">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-10 mb-12">
                <div>
                    <div class="flex items-center space-x-2 mb-6">
                        <div class="w-10 h-10 bg-primary rounded-lg flex items-center justify-center">
                            <i class="fa fa-compass text-white text-xl"></i>
                        </div>
                        <span class="text-xl font-bold">北斗空间技术</span>
                    </div>
                    <p class="text-gray-400 mb-6">
                        专注于北斗卫星导航系统应用解决方案，为各行业提供高精度定位、导航与授时服务。
                    </p>
                    <div class="flex space-x-4">
                        <a href="javascript:void(0);" class="text-gray-400 hover:text-white transition-custom">
                            <i class="fa fa-weixin text-xl"></i>
                        </a>
                        <a href="javascript:void(0);" class="text-gray-400 hover:text-white transition-custom">
                            <i class="fa fa-weibo text-xl"></i>
                        </a>
                        <a href="javascript:void(0);" class="text-gray-400 hover:text-white transition-custom">
                            <i class="fa fa-linkedin text-xl"></i>
                        </a>
                        <a href="javascript:void(0);" class="text-gray-400 hover:text-white transition-custom">
                            <i class="fa fa-youtube-play text-xl"></i>
                        </a>
                    </div>
                </div>
                
                <div>
                    <h4 class="text-lg font-bold mb-6">快速链接</h4>
                    <ul class="space-y-3">
                        <li><a href="#home" class="text-gray-400 hover:text-white transition-custom">首页</a></li>
                        <li><a href="#about" class="text-gray-400 hover:text-white transition-custom">关于我们</a></li>
                        <li><a href="#products" class="text-gray-400 hover:text-white transition-custom">核心产品</a></li>
                        <li><a href="#applications" class="text-gray-400 hover:text-white transition-custom">行业应用</a></li>
                        <li><a href="#cases" class="text-gray-400 hover:text-white transition-custom">典型案例</a></li>
                        <li><a href="team.html" target="_blank" class="text-gray-400 hover:text-white transition-custom">核心团队</a></li>
                        <li><a href="#contact" class="text-gray-400 hover:text-white transition-custom">联系我们</a></li>
                    </ul>
                </div>
                
                <div>
                    <h4 class="text-lg font-bold mb-6">产品中心</h4>
                    <ul class="space-y-3">
                        <li><a href="javascript:void(0);" class="text-gray-400 hover:text-white transition-custom">北斗高精度定位终端</a></li>
                        <li><a href="javascript:void(0);" class="text-gray-400 hover:text-white transition-custom">北斗导航模块</a></li>
                        <li><a href="javascript:void(0);" class="text-gray-400 hover:text-white transition-custom">北斗位置服务平台</a></li>
                        <li><a href="javascript:void(0);" class="text-gray-400 hover:text-white transition-custom">北斗授时设备</a></li>
                        <li><a href="javascript:void(0);" class="text-gray-400 hover:text-white transition-custom">北斗应用解决方案</a></li>
                    </ul>
                </div>
                
                <div>
                    <h4 class="text-lg font-bold mb-6">联系信息</h4>
                    <ul class="space-y-3">
                        <li class="flex items-start space-x-3">
                            <i class="fa fa-map-marker text-gray-400 mt-1"></i>
                            <span class="text-gray-400">贵阳市友山基金大厦24楼</span>
                        </li>
                        <li class="flex items-center space-x-3">
                            <i class="fa fa-phone text-gray-400"></i>
                            <span class="text-gray-400">010-12345678</span>
                        </li>
                        <li class="flex items-center space-x-3">
                            <i class="fa fa-envelope text-gray-400"></i>
                            <span class="text-gray-400">contact@beidou-space.com</span>
                        </li>
                        <li class="flex items-center space-x-3">
                            <i class="fa fa-clock-o text-gray-400"></i>
                            <span class="text-gray-400">周一至周五: 9:00 - 18:00</span>
                        </li>
                    </ul>
                </div>
            </div>
            
            <div class="border-t border-gray-800 pt-8">
                <div class="flex flex-col md:flex-row justify-between items-center">
                    <p class="text-gray-500 text-sm mb-4 md:mb-0">
                        &copy; 2025 北斗空间技术有限公司. 保留所有权利.
                    </p>
                    <div class="flex space-x-6">
                        <a href="javascript:void(0);" class="text-gray-500 hover:text-gray-300 text-sm">隐私政策</a>
                        <a href="javascript:void(0);" class="text-gray-500 hover:text-gray-300 text-sm">使用条款</a>
                        <a href="javascript:void(0);" class="text-gray-500 hover:text-gray-300 text-sm">法律声明</a>
                    </div>
                </div>
            </div>
        </div>
    </footer>

    <!-- 返回顶部按钮 -->
    <button id="backToTop" class="fixed bottom-8 right-8 bg-primary text-white w-12 h-12 rounded-full flex items-center justify-center shadow-lg opacity-0 invisible transition-all duration-300 hover:bg-primary/90">
        <i class="fa fa-arrow-up"></i>
    </button>

    <!-- JavaScript -->
    <script>
        // 移动端菜单切换
        const menuBtn = document.getElementById('menuBtn');
        const mobileMenu = document.getElementById('mobileMenu');
        
        menuBtn.addEventListener('click', () => {
            mobileMenu.classList.toggle('hidden');
            // 切换图标
            const icon = menuBtn.querySelector('i');
            if (icon.classList.contains('fa-bars')) {
                icon.classList.replace('fa-bars', 'fa-times');
            } else {
                icon.classList.replace('fa-times', 'fa-bars');
            }
        });
        
        // 导航栏滚动效果
        const navbar = document.getElementById('navbar');
        window.addEventListener('scroll', () => {
            if (window.scrollY > 50) {
                navbar.classList.add('py-2', 'shadow-md');
                navbar.classList.remove('py-4', 'shadow-sm');
            } else {
                navbar.classList.add('py-4', 'shadow-sm');
                navbar.classList.remove('py-2', 'shadow-md');
            }
        });
        
        // 返回顶部按钮
        const backToTopBtn = document.getElementById('backToTop');
        
        window.addEventListener('scroll', () => {
            if (window.scrollY > 300) {
                backToTopBtn.classList.remove('opacity-0', 'invisible');
                backToTopBtn.classList.add('opacity-100', 'visible');
            } else {
                backToTopBtn.classList.add('opacity-0', 'invisible');
                backToTopBtn.classList.remove('opacity-100', 'visible');
            }
        });
        
        backToTopBtn.addEventListener('click', () => {
            window.scrollTo({
                top: 0,
                behavior: 'smooth'
            });
        });
        
        // 点击移动端导航链接后关闭菜单
        const mobileLinks = mobileMenu.querySelectorAll('a');
        mobileLinks.forEach(link => {
            link.addEventListener('click', () => {
                mobileMenu.classList.add('hidden');
                const icon = menuBtn.querySelector('i');
                icon.classList.replace('fa-times', 'fa-bars');
            });
        });
        
        // 滚动动画
        const animateElements = document.querySelectorAll('.animate-fadeIn');
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, {
            threshold: 0.1
        });
        
        animateElements.forEach(element => {
            element.style.opacity = '0';
            element.style.transform = 'translateY(20px)';
            element.style.transition = 'opacity 0.6s ease-out, transform 0.6s ease-out';
            observer.observe(element);
        });
    </script>
</body>
</html>

