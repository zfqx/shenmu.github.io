# shenmu.github.io
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>乡村建设智慧监管平台 - 首页</title>
    <!-- 引入Tailwind CSS（轻量化样式框架，无需额外写大量CSS） -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- 引入图标库 -->
    <link href="https://cdn.jsdelivr.net/npm/font-awesome@4.7.0/css/font-awesome.min.css" rel="stylesheet">
    <style>
        /* 自定义动画效果 */
        .card-hover {
            transition: all 0.5s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            transform: translateY(0);
        }
        .card-hover:hover {
            transform: translateY(-15px) scale(1.02);
            box-shadow: 0 25px 30px -10px rgba(0, 0, 0, 0.25), 0 15px 15px -5px rgba(0, 0, 0, 0.1);
        }
        .nav-scroll {
            transition: background-color 0.3s ease, box-shadow 0.3s ease;
        }
        /* 模态框动画 */
        .modal-fade {
            animation: fadeIn 0.3s ease;
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        .modal-slide {
            animation: slideDown 0.3s ease;
        }
        @keyframes slideDown {
            from { transform: translateY(-30px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }
        /* 模块数字标记 */
        .module-badge {
            position: absolute;
            top: -15px;
            right: -15px;
            width: 44px;
            height: 44px;
            border-radius: 50%;
            background-color: white;
            color: #333;
            font-weight: 900;
            font-size: 22px;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 6px 8px -2px rgba(0, 0, 0, 0.25);
            border: 4px solid white;
            z-index: 10;
        }
        /* 渐变背景 */
        .card-gradient-blue {
            background: linear-gradient(135deg, #2563eb, #3b82f6);
        }
        .card-gradient-green {
            background: linear-gradient(135deg, #16a34a, #22c55e);
        }
        .card-gradient-orange {
            background: linear-gradient(135deg, #ea580c, #f97316);
        }
        .card-gradient-purple {
            background: linear-gradient(135deg, #9333ea, #a855f7);
        }
        .card-gradient-yellow {
            background: linear-gradient(135deg, #ca8a04, #eab308);
        }
    </style>
</head>
<body class="bg-gray-100 font-sans text-gray-800">
    <!-- 导航栏 -->
    <header class="nav-scroll fixed w-full top-0 z-50 bg-white shadow-md">
        <div class="container mx-auto px-5 py-4 flex justify-between items-center">
            <!-- 平台Logo -->
            <a href="page1.html" class="flex items-center gap-3">
                <i class="fa fa-building-o text-blue-600 text-3xl"></i>
                <span class="text-2xl md:text-3xl font-black text-blue-700">乡村建设智慧监管平台</span>
            </a>

            <!-- 桌面端导航 -->
            <nav class="hidden md:flex items-center gap-8">
                <a href="page1.html" class="font-bold text-blue-700 border-b-4 border-blue-700 py-2 text-xl">首页</a>
                <a href="page2.html" class="font-bold text-gray-600 hover:text-blue-700 transition-colors text-xl">项目公示</a>
                <a href="page3.html" class="font-bold text-gray-600 hover:text-blue-700 transition-colors text-xl">意见征集</a>
                <a href="page4.html" class="font-bold text-gray-600 hover:text-blue-700 transition-colors text-xl">进度跟踪</a>
                <a href="page5.html" class="font-bold text-gray-600 hover:text-blue-700 transition-colors text-xl">资金监管&积分商城</a>
                <!-- 登录/用户信息区域 -->
                <div class="flex items-center gap-5">
                    <!-- 未登录状态 -->
                    <button id="loginBtn" class="hidden font-bold text-gray-600 hover:text-blue-700 transition-colors flex items-center gap-2 text-xl">
                        <i class="fa fa-user-o text-2xl"></i> 登录
                    </button>
                    <!-- 已登录状态 -->
                    <div id="userInfo" class="hidden flex items-center gap-3">
                        <img src="https://picsum.photos/id/64/50/50" alt="用户头像" class="w-12 h-12 rounded-full object-cover border-3 border-blue-100">
                        <span class="font-bold text-gray-700 text-xl" id="userName">游客</span>
                        <button id="logoutBtn" class="text-red-500 hover:text-red-700 transition-colors text-2xl">
                            <i class="fa fa-sign-out"></i>
                        </button>
                    </div>
                </div>
            </nav>

            <!-- 移动端汉堡菜单 + 登录按钮 -->
            <div class="md:hidden flex items-center gap-5">
                <button id="mobileLoginBtn" class="text-gray-600">
                    <i class="fa fa-user-o text-3xl"></i>
                </button>
                <button id="menuBtn" class="text-gray-600 text-3xl">
      
