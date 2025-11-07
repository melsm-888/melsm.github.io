# melsm.github.io
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>订单管理系统</title>
  <!-- 引入Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- 引入Font Awesome -->
  <link href="https://cdn.jsdelivr.net/npm/font-awesome@4.7.0/css/font-awesome.min.css" rel="stylesheet">
  
  <!-- 配置Tailwind自定义颜色和字体 -->
  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            primary: '#165DFF',
            secondary: '#36CFC9',
            danger: '#F53F3F',
            warning: '#FF7D00',
            success: '#00B42A',
            neutral: {
              100: '#F2F3F5',
              200: '#E5E6EB',
              300: '#C9CDD4',
              400: '#86909C',
              500: '#4E5969',
              600: '#272E3B',
              700: '#1D2129',
            }
          },
          fontFamily: {
            inter: ['Inter', 'system-ui', 'sans-serif'],
          },
        },
      }
    }
  </script>
  
  <style type="text/tailwindcss">
    @layer utilities {
      .content-auto {
        content-visibility: auto;
      }
      .card-shadow {
        box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
      }
      .card-hover {
        transition: all 0.3s ease;
      }
      .card-hover:hover {
        transform: translateY(-5px);
        box-shadow: 0 8px 30px rgba(0, 0, 0, 0.12);
      }
      .btn-effect {
        transition: all 0.2s ease;
      }
      .btn-effect:active {
        transform: scale(0.96);
      }
    }
  </style>
</head>

<body class="bg-neutral-100 font-inter text-neutral-700 min-h-screen">
  <!-- 顶部导航栏 -->
  <header class="bg-white shadow-sm sticky top-0 z-10">
    <div class="container mx-auto px-4 py-4 flex justify-between items-center">
      <div class="flex items-center space-x-2">
        <i class="fa fa-shopping-bag text-primary text-2xl"></i>
        <h1 class="text-xl font-bold text-neutral-700">订单管理系统</h1>
      </div>
      <div class="flex items-center space-x-4">
        <button class="text-neutral-500 hover:text-primary transition-colors">
          <i class="fa fa-search text-lg"></i>
        </button>
        <button class="text-neutral-500 hover:text-primary transition-colors">
          <i class="fa fa-bell text-lg"></i>
        </button>
        <div class="h-8 w-8 rounded-full bg-primary/10 flex items-center justify-center text-primary">
          <i class="fa fa-user"></i>
        </div>
      </div>
    </div>
  </header>

  <!-- 主内容区 -->
  <main class="container mx-auto px-4 py-8">
    <!-- 页面标题和筛选 -->
    <div class="mb-8 flex flex-col md:flex-row justify-between items-start md:items-center">
      <div>
        <h2 class="text-[clamp(1.5rem,3vw,2rem)] font-bold text-neutral-700">鞋服订单列表</h2>
        <p class="text-neutral-400 mt-1">共 <span class="text-primary font-medium">5</span> 个订单</p>
      </div>
      <div class="mt-4 md:mt-0 flex space-x-3">
        <select class="border border-neutral-200 rounded-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-primary/30 focus:border-primary">
          <option>全部状态</option>
          <option>已发货</option>
          <option>未发货</option>
          <option>已完成</option>
          <option>已取消</option>
        </select>
        <button class="bg-primary text-white px-4 py-2 rounded-lg flex items-center space-x-2 btn-effect">
          <i class="fa fa-filter"></i>
          <span>筛选</span>
        </button>
      </div>
    </div>

    <!-- 订单列表 -->
    <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">
      <!-- 订单1 -->
      <div class="bg-white rounded-xl p-6 card-shadow card-hover">
        <div class="flex justify-between items-start mb-4">
          <div>
            <span class="bg-primary/10 text-primary text-xs px-2 py-1 rounded-full">已发货</span>
            <p class="text-neutral-500 text-sm mt-1">订单编号: OD20230512001</p>
          </div>
          <p class="text-neutral-400 text-sm">2023-05-12</p>
        </div>
        
        <div class="flex gap-4 mb-6">
          <img src="https://picsum.photos/id/96/100/100" alt="运动鞋" class="w-20 h-20 object-cover rounded-lg">
          <div>
            <h3 class="font-semibold text-neutral-700">专业跑步运动鞋</h3>
            <p class="text-neutral-500 text-sm mt-1">货号: SP2023001</p>
            <p class="text-neutral-500 text-sm">材质: 飞织网面 + 橡胶底</p>
            <p class="text-primary font-semibold mt-1">¥399.00</p>
          </div>
        </div>
        
        <div class="flex justify-between items-center pt-4 border-t border-neutral-100">
          <div>
            <span class="text-neutral-500 text-sm">数量: 1</span>
            <span class="text-neutral-500 text-sm ml-4">尺码: 42</span>
          </div>
          <div class="flex gap-2">
            <button class="text-danger border border-danger px-3 py-1 rounded-lg text-sm flex items-center gap-1 btn-effect hover:bg-danger/5">
              <i class="fa fa-undo"></i> 退货
            </button>
            <button class="text-warning border border-warning px-3 py-1 rounded-lg text-sm flex items-center gap-1 btn-effect hover:bg-warning/5">
              <i class="fa fa-exchange"></i> 换货
            </button>
            <button class="text-success border border-success px-3 py-1 rounded-lg text-sm flex items-center gap-1 btn-effect hover:bg-success/5">
              <i class="fa fa-money"></i> 补差
            </button>
          </div>
        </div>
      </div>

      <!-- 订单2 -->
      <div class="bg-white rounded-xl p-6 card-shadow card-hover">
        <div class="flex justify-between items-start mb-4">
          <div>
            <span class="bg-success/10 text-success text-xs px-2 py-1 rounded-full">已完成</span>
            <p class="text-neutral-500 text-sm mt-1">订单编号: OD20230510008</p>
          </div>
          <p class="text-neutral-400 text-sm">2023-05-10</p>
        </div>
        
        <div class="flex gap-4 mb-6">
          <img src="https://picsum.photos/id/21/100/100" alt="休闲夹克" class="w-20 h-20 object-cover rounded-lg">
          <div>
            <h3 class="font-semibold text-neutral-700">男士休闲夹克</h3>
            <p class="text-neutral-500 text-sm mt-1">货号: JA2023015</p>
            <p class="text-neutral-500 text-sm">材质: 聚酯纤维 + 棉</p>
            <p class="text-primary font-semibold mt-1">¥599.00</p>
          </div>
        </div>
        
        <div class="flex justify-between items-center pt-4 border-t border-neutral-100">
          <div>
            <span class="text-neutral-500 text-sm">数量: 1</span>
            <span class="text-neutral-500 text-sm ml-4">尺码: L</span>
          </div>
          <div class="flex gap-2">
            <button class="text-danger border border-danger px-3 py-1 rounded-lg text-sm flex items-center gap-1 btn-effect hover:bg-danger/5">
              <i class="fa fa-undo"></i> 退货
            </button>
            <button class="text-warning border border-warning px-3 py-1 rounded-lg text-sm flex items-center gap-1 btn-effect hover:bg-warning/5">
              <i class="fa fa-exchange"></i> 换货
            </button>
            <button class="text-success border border-success px-3 py-1 rounded-lg text-sm flex items-center gap-1 btn-effect hover:bg-success/5">
              <i class="fa fa-money"></i> 补差
            </button>
          </div>
        </div>
      </div>

      <!-- 订单3 -->
      <div class="bg-white rounded-xl p-6 card-shadow card-hover">
        <div class="flex justify-between items-start mb-4">
          <div>
            <span class="bg-primary/10 text-primary text-xs px-2 py-1 rounded-full">已发货</span>
            <p class="text-neutral-500 text-sm mt-1">订单编号: OD20230508012</p>
          </div>
          <p class="text-neutral-400 text-sm">2023-05-08</p>
        </div>
        
        <div class="flex gap-4 mb-6">
          <img src="https://picsum.photos/id/65/100/100" alt="牛仔裤" class="w-20 h-20 object-cover rounded-lg">
          <div>
            <h3 class="font-semibold text-neutral-700">修身牛仔裤</h3>
            <p class="text-neutral-500 text-sm mt-1">货号: PT2023042</p>
            <p class="text-neutral-500 text-sm">材质: 棉 + 氨纶</p>
            <p class="text-primary font-semibold mt-1">¥299.00</p>
          </div>
        </div>
        
        <div class="flex justify-between items-center pt-4 border-t border-neutral-100">
          <div>
            <span class="text-neutral-500 text-sm">数量: 2</span>
            <span class="text-neutral-500 text-sm ml-4">尺码: 30, 32</span>
          </div>
          <div class="flex gap-2">
            <button class="text-danger border border-danger px-3 py-1 rounded-lg text-sm flex items-center gap-1 btn-effect hover:bg-danger/5">
              <i class="fa fa-undo"></i> 退货
            </button>
            <button class="text-warning border border-warning px-3 py-1 rounded-lg text-sm flex items-center gap-1 btn-effect hover:bg-warning/5">
              <i class="fa fa-exchange"></i> 换货
            </button>
            <button class="text-success border border-success px-3 py-1 rounded-lg text-sm flex items-center gap-1 btn-effect hover:bg-success/5">
              <i class="fa fa-money"></i> 补差
            </button>
          </div>
        </div>
      </div>

      <!-- 订单4 -->
      <div class="bg-white rounded-xl p-6 card-shadow card-hover">
        <div class="flex justify-between items-start mb-4">
          <div>
            <span class="bg-neutral-200 text-neutral-500 text-xs px-2 py-1 rounded-full">未发货</span>
            <p class="text-neutral-500 text-sm mt-1">订单编号: OD20230505027</p>
          </div>
          <p class="text-neutral-400 text-sm">2023-05-05</p>
        </div>
        
        <div class="flex gap-4 mb-6">
          <img src="https://picsum.photos/id/26/100/100" alt="T恤" class="w-20 h-20 object-cover rounded-lg">
          <div>
            <h3 class="font-semibold text-neutral-700">纯棉短袖T恤</h3>
            <p class="text-neutral-500 text-sm mt-1">货号: TS2023068</p>
            <p class="text-neutral-500 text-sm">材质: 100%棉</p>
            <p class="text-primary font-semibold mt-1">¥129.00</p>
          </div>
        </div>
        
        <div class="flex justify-between items-center pt-4 border-t border-neutral-100">
          <div>
            <span class="text-neutral-500 text-sm">数量: 3</span>
            <span class="text-neutral-500 text-sm ml-4">尺码: M, L, XL</span>
          </div>
          <div class="flex gap-2">
            <button class="text-danger border border-danger px-3 py-1 rounded-lg text-sm flex items-center gap-1 btn-effect hover:bg-danger/5">
              <i class="fa fa-undo"></i> 退货
            </button>
            <button class="text-warning border border-warning px-3 py-1 rounded-lg text-sm flex items-center gap-1 btn-effect hover:bg-warning/5">
              <i class="fa fa-exchange"></i> 换货
            </button>
            <button class="text-success border border-success px-3 py-1 rounded-lg text-sm flex items-center gap-1 btn-effect hover:bg-success/5">
              <i class="fa fa-money"></i> 补差
            </button>
          </div>
        </div>
      </div>

      <!-- 订单5 -->
      <div class="bg-white rounded-xl p-6 card-shadow card-hover">
        <div class="flex justify-between items-start mb-4">
          <div>
            <span class="bg-success/10 text-success text-xs px-2 py-1 rounded-full">已完成</span>
            <p class="text-neutral-500 text-sm mt-1">订单编号: OD20230501036</p>
          </div>
          <p class="text-neutral-400 text-sm">2023-05-01</p>
        </div>
        
        <div class="flex gap-4 mb-6">
          <img src="https://picsum.photos/id/103/100/100" alt="运动鞋" class="w-20 h-20 object-cover rounded-lg">
          <div>
            <h3 class="font-semibold text-neutral-700">篮球运动鞋</h3>
            <p class="text-neutral-500 text-sm mt-1">货号: SP2023019</p>
            <p class="text-neutral-500 text-sm">材质: 合成革 + 橡胶底</p>
            <p class="text-primary font-semibold mt-1">¥699.00</p>
          </div>
        </div>
        
        <div class="flex justify-between items-center pt-4 border-t border-neutral-100">
          <div>
            <span class="text-neutral-500 text-sm">数量: 1</span>
            <span class="text-neutral-500 text-sm ml-4">尺码: 44</span>
          </div>
          <div class="flex gap-2">
            <button class="text-danger border border-danger px-3 py-1 rounded-lg text-sm flex items-center gap-1 btn-effect hover:bg-danger/5">
              <i class="fa fa-undo"></i> 退货
            </button>
            <button class="text-warning border border-warning px-3 py-1 rounded-lg text-sm flex items-center gap-1 btn-effect hover:bg-warning/5">
              <i class="fa fa-exchange"></i> 换货
            </button>
            <button class="text-success border border-success px-3 py-1 rounded-lg text-sm flex items-center gap-1 btn-effect hover:bg-success/5">
              <i class="fa fa-money"></i> 补差
            </button>
          </div>
        </div>
      </div>
    </div>
  </main>

  <!-- 页脚 -->
  <footer class="bg-white mt-12 py-6 border-t border-neutral-200">
    <div class="container mx-auto px-4 text-center text-neutral-500 text-sm">
      <p>© 2023 订单管理系统 版权所有</p>
    </div>
  </footer>

  <!-- 操作提示模态框 (默认隐藏) -->
  <div id="modal" class="fixed inset-0 bg-black/50 flex items-center justify-center z-50 hidden">
    <div class="bg-white rounded-xl p-6 w-full max-w-md mx-4 transform transition-all">
      <h3 class="text-lg font-semibold text-neutral-700 mb-4" id="modalTitle">操作提示</h3>
      <p class="text-neutral-500 mb-6" id="modalContent">确认执行此操作吗？</p>
      <div class="flex justify-end gap-3">
        <button id="cancelBtn" class="border border-neutral-300 px-4 py-2 rounded-lg text-neutral-600 btn-effect">取消</button>
        <button id="confirmBtn" class="bg-primary text-white px-4 py-2 rounded-lg btn-effect">确认</button>
      </div>
    </div>
  </div>

  <script>
    // 获取模态框元素
    const modal = document.getElementById('modal');
    const modalTitle = document.getElementById('modalTitle');
    const modalContent = document.getElementById('modalContent');
    const cancelBtn = document.getElementById('cancelBtn');
    const confirmBtn = document.getElementById('confirmBtn');
    
    // 存储当前操作的订单信息
    let currentOperation = '';
    let currentOrder = '';
    
    // 为所有操作按钮添加点击事件
    document.querySelectorAll('.flex.gap-2 button').forEach(button => {
      button.addEventListener('click', function() {
        // 获取操作类型和订单信息
        currentOperation = this.textContent.trim();
        const orderCard = this.closest('.card-shadow');
        currentOrder = orderCard.querySelector('h3').textContent;
        
        // 设置模态框内容
        modalTitle.textContent = `${currentOperation}操作`;
        modalContent.textContent = `您确定要对 "${currentOrder}" 执行${currentOperation}操作吗？`;
        
        // 显示模态框
        modal.classList.remove('hidden');
        // 添加动画效果
        setTimeout(() => {
          modal.querySelector('div').classList.add('scale-100');
          modal.querySelector('div').classList.remove('scale-95');
        }, 10);
      });
    });
    
    // 关闭模态框的函数
    function closeModal() {
      modal.querySelector('div').classList.remove('scale-100');
      modal.querySelector('div').classList.add('scale-95');
      setTimeout(() => {
        modal.classList.add('hidden');
      }, 200);
    }
    
    // 取消按钮点击事件
    cancelBtn.addEventListener('click', closeModal);
    
    // 确认按钮点击事件
    confirmBtn.addEventListener('click', function() {
      // 这里可以添加实际的操作逻辑
      alert(`已确认对 "${currentOrder}" 执行${currentOperation}操作`);
      closeModal();
    });
    
    // 点击模态框背景关闭模态框
    modal.addEventListener('click', function(e) {
      if (e.target === modal) {
        closeModal();
      }
    });
  </script>
</body>
</html>
