<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Ali 쿠폰 모음</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    body {
      font-family: 'NanumSquareNeo', sans-serif;
    }
    .fade-in {
      opacity: 0;
      transform: translateY(20px);
      animation: fadeInUp 0.6s ease-out forwards;
    }
    @keyframes fadeInUp {
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
    .point {
      color: #f97316;
    }
    .bg-point {
      background-color: #f97316;
    }
    .hover\:bg-point-dark:hover {
      background-color: #ea580c;
    }
  </style>
  <link href="https://cdn.jsdelivr.net/gh/wan2land/d2coding-web@latest/d2coding.css" rel="stylesheet">
  <link href="https://cdn.jsdelivr.net/gh/projectnoonnu/naver-fonts@1.0/NanumSquareNeo.css" rel="stylesheet">
  <script>
    function showToast(message) {
      const toast = document.getElementById('toast');
      toast.innerText = message;
      toast.classList.remove('hidden');
      setTimeout(() => toast.classList.add('hidden'), 2000);
    }

    function copyCouponAndRedirect(code) {
      const url = "https://s.click.aliexpress.com/e/_oldQ7ct";
      navigator.clipboard.writeText(code).then(() => {
        showToast(`쿠폰 코드 "${code}"가 복사되었습니다!`);
        window.open(url, '_blank');
      });
    }
  </script>
</head>
<body class="bg-gradient-to-br from-white to-blue-50 text-gray-800">
  <div id="toast" class="hidden fixed top-4 left-1/2 transform -translate-x-1/2 bg-point text-white text-sm font-medium px-4 py-2 rounded shadow-lg z-50"></div>

  <header class="bg-white shadow-md p-4 sticky top-0 z-40">
    <div class="container mx-auto flex justify-between items-center">
      <h1 class="text-3xl font-extrabold point">AliCoupon</h1>
      <nav class="space-x-4">
        <a href="#coupons" class="text-gray-700 hover:text-point font-medium">오늘의 쿠폰</a>
        <a href="#hot" class="text-gray-700 hover:text-point font-medium">핫딜</a>
        <a href="#event" class="text-gray-700 hover:text-point font-medium">이벤트</a>
        <a href="#mart" class="text-gray-700 hover:text-point font-medium">₩1 마트</a>
      </nav>
    </div>
  </header>

  <section class="bg-yellow-50 py-6 px-4 border-b border-yellow-200">
    <div class="container mx-auto flex flex-col md:flex-row justify-between items-center gap-4 fade-in">
      <div>
        <h2 class="text-lg md:text-xl font-bold text-yellow-800">☀️ 여름 할인 이벤트 진행 중!</h2>
        <p class="text-sm text-yellow-700 mt-1">지금 사용하면 추가 혜택! $50 이상 구매 시 $10 할인</p>
      </div>
      <button onclick="copyCouponAndRedirect('SUMMER10')"
              class="px-5 py-2 bg-point text-white rounded-full font-semibold hover:bg-point-dark transition duration-300">
        쿠폰 받기 →
      </button>
    </div>
  </section>

  <section id="event" class="container mx-auto px-6 py-8">
    <h2 class="text-xl font-bold text-gray-800 mb-4">🎉 진행 중인 이벤트</h2>
    <div class="grid gap-4 md:grid-cols-2">
      <div class="bg-white rounded-lg shadow p-4">
        <h3 class="text-lg font-semibold text-point">여름맞이 브랜드 특가</h3>
        <p class="text-sm text-gray-700 mt-1">브랜드 제품 최대 60% 할인! 한정 수량으로 서둘러 참여하세요.</p>
      </div>
      <div class="bg-white rounded-lg shadow p-4">
        <h3 class="text-lg font-semibold text-point">무료배송 혜택 이벤트</h3>
        <p class="text-sm text-gray-700 mt-1">지정된 상품 구매 시 무료배송 적용! 조건 확인 필수.</p>
      </div>
    </div>
  </section>

  <section id="mart" class="container mx-auto px-6 py-8">
    <h2 class="text-xl font-bold text-gray-800 mb-4">🛒 천원 마트 추천</h2>
    <p class="text-sm text-gray-600 mb-2">₩1에 득템할 수 있는 놀라운 마트 상품!</p>
    <a href="https://s.click.aliexpress.com/e/_₩1mart" target="_blank" class="inline-block px-6 py-2 bg-point text-white rounded-lg font-semibold hover:bg-point-dark transition">천원 마트 보러가기 →</a>
  </section>

  <section class="container mx-auto px-6 py-10">
    <h2 class="text-xl font-bold text-gray-800 mb-4">🛍️ 인기 상품 추천</h2>
    <div class="overflow-x-auto">
      <div id="product-list" class="flex gap-6 w-max pb-4">
      </div>
    </div>
  </section>

  <section id="coupons" class="container mx-auto px-6 py-10">
    <h2 class="text-xl font-bold text-gray-800 mb-4">🎟️ 오늘의 쿠폰</h2>
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
      <div class="bg-white rounded-xl shadow-md p-6 flex flex-col gap-2 fade-in">
        <span class="inline-block px-3 py-1 text-xs bg-blue-100 text-blue-600 rounded-full w-max">전 세계 배송</span>
        <h3 class="text-lg font-bold">$20 이상 구매 시 $3 할인</h3>
        <p class="text-sm text-gray-600">모든 사용자에게 적용 가능</p>
        <button onclick="copyCouponAndRedirect('ALI3OFF')"
                class="mt-auto px-4 py-2 bg-blue-500 hover:bg-blue-600 text-white font-semibold rounded-lg transition">
          코드 복사
        </button>
      </div>
      <div class="bg-white rounded-xl shadow-md p-6 flex flex-col gap-2 fade-in">
        <span class="inline-block px-3 py-1 text-xs bg-green-100 text-green-600 rounded-full w-max">신규 회원 전용</span>
        <h3 class="text-lg font-bold">첫 구매 시 $5 할인</h3>
        <p class="text-sm text-gray-600">신규 사용자 한정 쿠폰</p>
        <button onclick="copyCouponAndRedirect('WELCOME5')"
                class="mt-auto px-4 py-2 bg-green-500 hover:bg-green-600 text-white font-semibold rounded-lg transition">
          코드 복사
        </button>
      </div>
    </div>
  </section>

  <script>
    const products = [
      {
        title: "여름 남성 반팔 티셔츠",
        price: "$9.99",
        image: "https://ae01.alicdn.com/kf/SampleImage1.jpg",
        link: "https://www.aliexpress.com/item/100500"
      },
      {
        title: "USB 선풍기 미니 탁상용",
        price: "$5.25",
        image: "https://ae01.alicdn.com/kf/SampleImage2.jpg",
        link: "https://www.aliexpress.com/item/100501"
      },
      {
        title: "여성용 샌들 여름 필수템",
        price: "$12.30",
        image: "https://ae01.alicdn.com/kf/SampleImage3.jpg",
        link: "https://www.aliexpress.com/item/100502"
      },
      {
        title: "휴대용 블루투스 스피커",
        price: "$15.90",
        image: "https://ae01.alicdn.com/kf/SampleImage4.jpg",
        link: "https://www.aliexpress.com/item/100503"
      }
    ];

    const productList = document.getElementById('product-list');

    products.forEach(p => {
      const el = document.createElement('div');
      el.className = "bg-white rounded-xl shadow p-4 transition hover:shadow-md w-60 flex-shrink-0";
      el.innerHTML = `
        <a href="${p.link}" target="_blank" class="block text-center">
          <img src="${p.image}" alt="${p.title}" class="w-full h-40 object-cover rounded mb-2" />
          <h3 class="text-sm font-semibold text-gray-700">${p.title}</h3>
          <p class="point font-bold mt-1">${p.price}</p>
        </a>
      `;
      productList.appendChild(el);
    });
  </script>
</body>
</html>
