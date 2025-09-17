# NghiepLy.github.bio
GS25 Loyalty App Game 
<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Phân Tích Luồng Marketing - GS25 Loyalty App</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <!-- Chosen Palette: Warm Neutrals with GS25 Blue Accent -->
    <!-- Application Structure Plan: The application is structured as a single-page dashboard to compare two marketing campaign concepts. The core is a tabbed interface allowing users to switch between 'Concept 1' and 'Concept 2'. This design was chosen for direct comparison, which is the main goal of the source report. Each tab displays an interactive, step-by-step flowchart built with HTML/CSS. Supporting sections for 'Prize Structure' and 'Redemption Process' provide necessary context. This user flow (Overview -> Compare -> Details) is intuitive and guides the user through the information logically. -->
    <!-- Visualization & Content Choices: Report Info: Two user flow diagrams. Goal: Compare processes. Viz: Custom HTML/CSS flowcharts to avoid forbidden SVG/Mermaid. Interaction: Tab switching to flip between concepts; hover effects on flowchart steps for detail. Justification: Flowcharts are ideal for process visualization; HTML/CSS implementation ensures compliance and custom styling. Report Info: Prize list. Goal: Inform. Viz: Styled content cards. Justification: More visually engaging than a plain list. Report Info: Redemption steps. Goal: Inform. Viz: Numbered step-by-step guide. Justification: Clear and easy to follow. A new interactive canvas-based lucky wheel is added for visual engagement, representing the core game concept. -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Inter', sans-serif;
        }
        .flow-connector {
            position: relative;
            width: 2px;
            background-color: #d1d5db;
            margin: 0 auto;
        }
        .flow-connector::after {
            content: '▼';
            position: absolute;
            bottom: -1px;
            left: 50%;
            transform: translateX(-50%);
            color: #d1d5db;
            font-size: 1.2rem;
        }
        .flow-card {
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }
        .flow-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
        }
        .tab-button.active {
            border-color: #007AC2;
            color: #007AC2;
            background-color: #eff6ff;
        }
        .wheel-container {
            position: relative;
            width: 100%;
            max-width: 400px;
            height: 400px;
            margin: 0 auto;
        }
    </style>
     <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
</head>
<body class="bg-gray-50 text-gray-800">

    <div class="container mx-auto p-4 md:p-8 max-w-7xl">
        <header class="text-center mb-10">
            <h1 class="text-3xl md:text-4xl font-bold text-gray-900">Phân Tích Luồng Tương Tác</h1>
            <p class="text-lg text-gray-600 mt-2">Chương Trình Marketing cho Thành Viên GS25 Loyalty App</p>
        </header>

        <section class="bg-white p-6 rounded-xl shadow-sm mb-8">
            <h2 class="text-2xl font-bold text-[#007AC2] mb-4">Tổng Quan Chương Trình</h2>
            <p class="text-gray-700 leading-relaxed">
                Ứng dụng này trực quan hóa và so sánh hai concept cho chương trình marketing "Vòng Quay May Mắn" dành cho thành viên của GS25. Mục tiêu là phân tích chi tiết luồng tương tác của người dùng, từ lúc mua hàng, tham gia trò chơi, cho đến khi nhận và đổi thưởng. Điều kiện tham gia là thành viên có hóa đơn từ <strong>500,000 VND</strong> và chứa các sản phẩm được chỉ định.
            </p>
        </section>

        <section class="bg-white p-6 rounded-xl shadow-sm mb-8">
            <h2 class="text-2xl font-bold text-[#007AC2] mb-4">Cơ Cấu Giải Thưởng</h2>
            <p class="text-gray-700 mb-6">Vòng quay may mắn bao gồm nhiều loại phần thưởng hấp dẫn để tăng tính tương tác và giá trị cho khách hàng thành viên.</p>
            <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4 text-center">
                <div class="bg-blue-50 p-4 rounded-lg">
                    <div class="text-4xl mb-2">🎁</div>
                    <h3 class="font-semibold">Sản phẩm miễn phí</h3>
                    <p class="text-sm text-gray-600">Barcode sản phẩm</p>
                </div>
                <div class="bg-green-50 p-4 rounded-lg">
                    <div class="text-4xl mb-2">⭐</div>
                    <h3 class="font-semibold">Điểm thưởng</h3>
                    <p class="text-sm text-gray-600">Cộng trực tiếp vào tài khoản</p>
                </div>
                <div class="bg-yellow-50 p-4 rounded-lg">
                    <div class="text-4xl mb-2">💰</div>
                    <h3 class="font-semibold">Voucher tiền mặt</h3>
                    <p class="text-sm text-gray-600">Giảm giá cho lần mua sau</p>
                </div>
                 <div class="bg-purple-50 p-4 rounded-lg">
                    <div class="text-4xl mb-2">🎟️</div>
                    <h3 class="font-semibold">Voucher sản phẩm</h3>
                    <p class="text-sm text-gray-600">Đổi sản phẩm chỉ định</p>
                </div>
                 <div class="bg-red-50 p-4 rounded-lg">
                    <div class="text-4xl mb-2">😊</div>
                    <h3 class="font-semibold">Lời chúc may mắn</h3>
                    <p class="text-sm text-gray-600">Thêm niềm vui cho khách</p>
                </div>
            </div>
        </section>

        <section>
            <div class="mb-8">
                <div class="flex justify-center border-b border-gray-200">
                    <button id="tab1" class="tab-button text-lg font-semibold py-4 px-6 border-b-2 transition-colors duration-300 active">Concept 1: Vòng Quay May Mắn</button>
                    <button id="tab2" class="tab-button text-lg font-semibold py-4 px-6 border-b-2 border-transparent text-gray-500 transition-colors duration-300">Concept 2: Transaction Game</button>
                </div>
            </div>

            <div id="content1" class="tab-content">
                <p class="text-center text-gray-700 max-w-3xl mx-auto mb-10 leading-relaxed">
                    Đây là luồng người dùng khi trò chơi vòng quay may mắn được tích hợp dưới dạng một webgame bên ngoài. Người dùng sẽ nhận được thông báo sau khi hoàn tất giao dịch đủ điều kiện và có thể truy cập game thông qua một nút bấm trên ứng dụng GS25.
                </p>
                <section class="bg-white p-6 rounded-xl shadow-sm mb-8 max-w-2xl mx-auto">
                    <h2 class="text-2xl font-bold text-[#007AC2] mb-4 text-center">Mô Phỏng Vòng Quay May Mắn</h2>
                    <p class="text-gray-700 leading-relaxed text-center mb-6">Nhấn "Quay Ngay!" để xem mô phỏng cách vòng quay hoạt động và hiển thị phần thưởng. Vòng quay này được xây dựng hoàn toàn bằng Canvas để đảm bảo tính tương tác cao và tối ưu hóa hiệu suất.</p>
                    <div class="wheel-container">
                        <canvas id="luckyWheelCanvas" class="w-full h-full"></canvas>
                        <div class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 w-16 h-16 rounded-full bg-white shadow-xl flex items-center justify-center border-4 border-blue-400">
                            <span class="text-2xl">🎯</span>
                        </div>
                    </div>
                    <div class="text-center mt-6">
                        <button id="spinButton" class="bg-blue-600 hover:bg-blue-700 text-white font-bold py-3 px-8 rounded-full shadow-lg transition transform hover:scale-105 duration-300">
                            Quay Ngay!
                        </button>
                        <p id="prizeMessage" class="mt-4 text-lg font-semibold text-gray-700"></p>
                    </div>
                </section>
                <div class="flex flex-col items-center">
                    <div class="flow-card bg-white p-4 rounded-lg shadow-md w-full max-w-sm text-center">
                        <span class="text-sm font-bold text-gray-500">Bắt đầu</span>
                        <p class="font-semibold mt-1">Member đến cửa hàng GS25 để mua sắm và thực hiện giao dịch tại quầy POS.</p>
                    </div>
                    <div class="flow-connector h-12"></div>
                    <div class="flow-card border-2 border-yellow-400 bg-yellow-50 p-4 rounded-lg shadow-md w-full max-w-sm text-center">
                        <p class="font-semibold">Hóa đơn đủ điều kiện chơi game?</p>
                        <p class="text-sm text-gray-600">(Bill ≥ 500,000 VND và có sản phẩm chỉ định)</p>
                    </div>
                    <div class="relative w-full max-w-sm flex justify-between my-4 h-12 items-center">
                        <div class="absolute top-1/2 left-0 w-1/2 border-t-2 border-dashed border-gray-300"></div>
                        <div class="absolute top-1/2 right-0 w-1/2 border-t-2 border-dashed border-gray-300"></div>
                        <span class="absolute top-0 left-1/4 -mt-3 bg-gray-50 px-2 text-red-500 font-semibold">Không</span>
                        <span class="absolute top-0 right-1/4 -mt-3 bg-gray-50 px-2 text-green-500 font-semibold">Có</span>
                    </div>
                    <div class="w-full flex justify-around items-start">
                        <div class="w-1/2 flex justify-center">
                             <div class="flow-card bg-red-50 p-4 rounded-lg shadow-md w-full max-w-xs text-center">
                                <span class="text-sm font-bold text-red-500">Kết thúc</span>
                                <p class="font-semibold mt-1">Giao dịch kết thúc không có lượt chơi.</p>
                            </div>
                        </div>
                        <div class="w-1/2 flex flex-col items-center">
                            <div class="flow-card bg-white p-4 rounded-lg shadow-md w-full max-w-xs text-center">
                                <p class="font-semibold">Member scan QR code trên loyalty app.</p>
                            </div>
                            <div class="flow-connector h-12"></div>
                             <div class="flow-card bg-white p-4 rounded-lg shadow-md w-full max-w-xs text-center">
                                <p class="font-semibold">POS xác nhận member ID và giao dịch hợp lệ.</p>
                            </div>
                            <div class="flow-connector h-12"></div>
                             <div class="flow-card bg-blue-50 p-4 rounded-lg shadow-md w-full max-w-xs text-center">
                                <p class="font-semibold">Hệ thống POS & Game Backend xử lý, tạo 1 lượt chơi mới cho member.</p>
                            </div>
                             <div class="flow-connector h-12"></div>
                            <div class="flow-card bg-white p-4 rounded-lg shadow-md w-full max-w-xs text-center">
                                <p class="font-semibold">Member nhận thông báo trên app và nhấn nút "Vòng quay may mắn" để mở webgame.</p>
                            </div>
                             <div class="flow-connector h-12"></div>
                             <div class="flow-card bg-white p-4 rounded-lg shadow-md w-full max-w-xs text-center">
                                <p class="font-semibold">Webgame hiển thị vòng quay, member thực hiện quay và nhận thưởng.</p>
                            </div>
                            <div class="flow-connector h-12"></div>
                            <div class="flow-card bg-green-50 p-4 rounded-lg shadow-md w-full max-w-xs text-center">
                                <span class="text-sm font-bold text-green-500">Hoàn tất</span>
                                <p class="font-semibold mt-1">Quà tặng (voucher, điểm...) được ghi nhận vào tài khoản member.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <div id="content2" class="tab-content hidden">
                <p class="text-center text-gray-700 max-w-3xl mx-auto mb-10 leading-relaxed">
                    Đây là luồng người dùng khi trò chơi được tích hợp trực tiếp vào quá trình giao dịch. Ngay sau khi giao dịch đủ điều kiện được xác nhận, một animation sẽ hiển thị phần thưởng ngay tại quầy hoặc trên ứng dụng.
                </p>
                 <div class="flex flex-col items-center">
                    <div class="flow-card bg-white p-4 rounded-lg shadow-md w-full max-w-sm text-center">
                        <span class="text-sm font-bold text-gray-500">Bắt đầu</span>
                        <p class="font-semibold mt-1">Member đến cửa hàng GS25 để mua sắm và thực hiện giao dịch tại quầy POS.</p>
                    </div>
                    <div class="flow-connector h-12"></div>
                    <div class="flow-card border-2 border-yellow-400 bg-yellow-50 p-4 rounded-lg shadow-md w-full max-w-sm text-center">
                        <p class="font-semibold">Hóa đơn đủ điều kiện chơi game?</p>
                        <p class="text-sm text-gray-600">(Bill ≥ 500,000 VND và có sản phẩm chỉ định)</p>
                    </div>
                    <div class="relative w-full max-w-sm flex justify-between my-4 h-12 items-center">
                        <div class="absolute top-1/2 left-0 w-1/2 border-t-2 border-dashed border-gray-300"></div>
                        <div class="absolute top-1/2 right-0 w-1/2 border-t-2 border-dashed border-gray-300"></div>
                        <span class="absolute top-0 left-1/4 -mt-3 bg-gray-50 px-2 text-red-500 font-semibold">Không</span>
                        <span class="absolute top-0 right-1/4 -mt-3 bg-gray-50 px-2 text-green-500 font-semibold">Có</span>
                    </div>
                    <div class="w-full flex justify-around items-start">
                         <div class="w-1/2 flex justify-center">
                             <div class="flow-card bg-red-50 p-4 rounded-lg shadow-md w-full max-w-xs text-center">
                                <span class="text-sm font-bold text-red-500">Kết thúc</span>
                                <p class="font-semibold mt-1">Giao dịch kết thúc không có lượt chơi.</p>
                            </div>
                        </div>
                        <div class="w-1/2 flex flex-col items-center">
                             <div class="flow-card bg-white p-4 rounded-lg shadow-md w-full max-w-xs text-center">
                                <p class="font-semibold">Member scan QR code trên loyalty app.</p>
                            </div>
                            <div class="flow-connector h-12"></div>
                            <div class="flow-card bg-white p-4 rounded-lg shadow-md w-full max-w-xs text-center">
                                <p class="font-semibold">POS xác nhận member ID và giao dịch hợp lệ.</p>
                            </div>
                             <div class="flow-connector h-12"></div>
                            <div class="flow-card bg-blue-50 p-4 rounded-lg shadow-md w-full max-w-xs text-center">
                                <p class="font-semibold">POS backend tạo mã chơi game và gọi webgame với thông tin giao dịch.</p>
                                <p class="text-sm text-gray-600">(transid + membercode + url)</p>
                            </div>
                            <div class="flow-connector h-12"></div>
                             <div class="flow-card bg-white p-4 rounded-lg shadow-md w-full max-w-xs text-center">
                                <p class="font-semibold">Webgame thực hiện animation hiển thị quà tặng may mắn ngay lập tức.</p>
                            </div>
                            <div class="flow-connector h-12"></div>
                            <div class="flow-card bg-white p-4 rounded-lg shadow-md w-full max-w-xs text-center">
                                <p class="font-semibold">Thông tin quà tặng được hiển thị trên màn hình POS và/hoặc app của member.</p>
                            </div>
                             <div class="flow-connector h-12"></div>
                            <div class="flow-card bg-green-50 p-4 rounded-lg shadow-md w-full max-w-xs text-center">
                                <span class="text-sm font-bold text-green-500">Hoàn tất</span>
                                <p class="font-semibold mt-1">Quà tặng (voucher, điểm...) được ghi nhận vào tài khoản member.</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section class="bg-white p-6 rounded-xl shadow-sm mt-8">
            <h2 class="text-2xl font-bold text-[#007AC2] mb-4">Quy Trình Đổi Thưởng</h2>
            <p class="text-gray-700 mb-6">Sau khi nhận thưởng, thành viên có thể dễ dàng sử dụng quà tặng của mình thông qua các bước sau.</p>
            <div class="flex flex-col md:flex-row gap-4">
                <div class="flex-1 bg-gray-50 p-4 rounded-lg">
                    <h3 class="font-semibold text-lg mb-2">Đối với Điểm thưởng</h3>
                    <ol class="list-decimal list-inside text-gray-600 space-y-2">
                        <li>Điểm được tự động cộng vào tài khoản của user.</li>
                        <li>User vào mục "My Reward" trên app.</li>
                        <li>Chọn sản phẩm muốn đổi và sử dụng điểm.</li>
                    </ol>
                </div>
                <div class="flex-1 bg-gray-50 p-4 rounded-lg">
                     <h3 class="font-semibold text-lg mb-2">Đối với Voucher</h3>
                     <ol class="list-decimal list-inside text-gray-600 space-y-2">
                        <li>Voucher được lưu trong mục "Tủ Quà Tặng / My Gifts".</li>
                        <li>User mở voucher để hiển thị QR Code.</li>
                        <li>Quét QR code tại quầy POS để áp dụng.</li>
                    </ol>
                </div>
            </div>
        </section>
    </div>

    <script>
        const tabs = document.querySelectorAll('.tab-button');
        const contents = document.querySelectorAll('.tab-content');

        tabs.forEach(tab => {
            tab.addEventListener('click', () => {
                tabs.forEach(item => {
                    item.classList.remove('active');
                });
                tab.classList.add('active');

                const target = tab.id.replace('tab', 'content');
                contents.forEach(content => {
                    if (content.id === target) {
                        content.classList.remove('hidden');
                    } else {
                        content.classList.add('hidden');
                    }
                });
            });
        });

        const canvas = document.getElementById('luckyWheelCanvas');
        const ctx = canvas.getContext('2d');
        const spinButton = document.getElementById('spinButton');
        const prizeMessage = document.getElementById('prizeMessage');

        const prizes = [
            { text: "Điểm Thưởng", color: "#fcd34d" },
            { text: "Voucher Cash", color: "#60a5fa" },
            { text: "Sản Phẩm A", color: "#f87171" },
            { text: "Lời Chúc", color: "#a78bfa" },
            { text: "Điểm Thưởng", color: "#fcd34d" },
            { text: "Voucher Sản Phẩm", color: "#4ade80" },
            { text: "Điểm Thưởng", color: "#fcd34d" },
            { text: "Sản Phẩm B", color: "#fb923c" },
        ];
        
        const arc = Math.PI / (prizes.length / 2);
        let rotation = 0;
        let isSpinning = false;
        let spinVelocity = 0;
        const initialVelocity = 5;

        function drawWheel() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            ctx.save();
            ctx.translate(canvas.width / 2, canvas.height / 2);
            ctx.rotate(rotation);

            prizes.forEach((prize, i) => {
                const angle = arc * i;
                ctx.beginPath();
                ctx.fillStyle = prize.color;
                ctx.moveTo(0, 0);
                ctx.arc(0, 0, canvas.width / 2, angle, angle + arc);
                ctx.lineTo(0, 0);
                ctx.fill();

                ctx.save();
                ctx.rotate(angle + arc / 2);
                ctx.textAlign = "center";
                ctx.fillStyle = "#fff";
                ctx.font = "bold 16px Inter";
                ctx.fillText(prize.text, canvas.width / 3, 10);
                ctx.restore();
            });

            ctx.restore();
        }

        function animate() {
            if (isSpinning) {
                rotation += spinVelocity;
                spinVelocity *= 0.99;
                if (spinVelocity < 0.01) {
                    isSpinning = false;
                    spinButton.disabled = false;
                    const finalAngle = (rotation % (2 * Math.PI));
                    const prizeIndex = Math.floor(prizes.length - (finalAngle / arc) - 0.5) % prizes.length;
                    prizeMessage.textContent = `Chúc mừng bạn đã nhận được: ${prizes[prizeIndex].text}!`;
                }
            }
            drawWheel();
            requestAnimationFrame(animate);
        }

        spinButton.addEventListener('click', () => {
            if (!isSpinning) {
                isSpinning = true;
                spinButton.disabled = true;
                prizeMessage.textContent = "Đang quay...";
                spinVelocity = initialVelocity + Math.random() * 2;
                setTimeout(() => {
                    const finalStop = Math.random() * (2 * Math.PI);
                    const currentRot = rotation % (2 * Math.PI);
                    let targetRot = (Math.ceil(currentRot / (2 * Math.PI)) * 2 * Math.PI) + finalStop + (2 * Math.PI) * 5;
                    spinVelocity = (targetRot - currentRot) / 300;
                }, 500);
            }
        });

        window.onload = function() {
            const size = Math.min(canvas.offsetWidth, canvas.offsetHeight);
            canvas.width = size;
            canvas.height = size;
            animate();
        };

        window.addEventListener('resize', () => {
            const size = Math.min(canvas.offsetWidth, canvas.offsetHeight);
            canvas.width = size;
            canvas.height = size;
            drawWheel();
        });
    </script>
</body>
</html>
