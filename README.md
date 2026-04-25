# zhuaji-web
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>爪迹——校园流浪动物关怀平台</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: "Microsoft YaHei", sans-serif;
        }
        body {
            background-color: #fdf8f4;
            color: #333;
            line-height: 1.6;
        }
        header {
            background-color: #ff9a76;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        .nav-container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
        }
        .logo {
            font-size: 24px;
            font-weight: bold;
            color: #fff;
        }
        nav ul {
            display: flex;
            list-style: none;
            gap: 30px;
        }
        nav ul li a {
            color: #fff;
            text-decoration: none;
            font-size: 16px;
            padding: 8px 12px;
            border-radius: 20px;
            transition: all 0.3s ease;
        }
        nav ul li a:hover {
            background-color: #fff;
            color: #ff9a76;
        }
        .banner {
            height: 500px;
            background: linear-gradient(rgba(0,0,0,0.2), rgba(0,0,0,0.2)), url('https://pic.baike.soso.com/ugc/baikepic2/21915/cut-012808020110581113332.jpg/0');
            background-size: cover;
            background-position: center;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            color: #fff;
            text-align: center;
            gap: 20px;
        }
        .banner h1 {
            font-size: 48px;
            text-shadow: 2px 2px 10px rgba(0,0,0,0.3);
        }
        .banner p {
            font-size: 18px;
            max-width: 600px;
        }
        .banner-btn {
            padding: 12px 30px;
            background-color: #ff9a76;
            color: #fff;
            border: none;
            border-radius: 30px;
            font-size: 16px;
            cursor: pointer;
            transition: transform 0.3s ease;
        }
        .banner-btn:hover {
            transform: scale(1.05);
        }
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 50px auto;
        }
        .section-title {
            text-align: center;
            font-size: 32px;
            color: #ff7f50;
            margin-bottom: 40px;
            position: relative;
        }
        .section-title::after {
            content: '';
            width: 80px;
            height: 3px;
            background-color: #ff9a76;
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
        }
        .intro-content {
            display: flex;
            gap: 40px;
            align-items: center;
            background: #fff;
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }
        .intro-text {
            flex: 1;
        }
        .intro-text p {
            font-size: 16px;
            margin-bottom: 15px;
        }
        .cat-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        .cat-card {
            background: #fff;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            cursor: pointer;
        }
        .cat-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        }
        .cat-card img {
            width: 100%;
            height: 250px;
            object-fit: cover;
        }
        .cat-info {
            padding: 20px;
        }
        .cat-info h3 {
            color: #ff7f50;
            margin-bottom: 10px;
        }
        .cat-info p {
            color: #666;
            margin-bottom: 5px;
        }
        .process-box {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 20px;
        }
        .process-item {
            flex: 1;
            min-width: 200px;
            background: #fff;
            padding: 30px 20px;
            border-radius: 20px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .process-item:hover {
            background-color: #ff9a76;
            color: #fff;
        }
        .process-item h4 {
            margin-top: 15px;
            font-size: 18px;
        }
        .form-box {
            background: #fff;
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }
        .form-tab {
            display: flex;
            gap: 20px;
            margin-bottom: 30px;
        }
        .tab-btn {
            padding: 10px 25px;
            border: 2px solid #ff9a76;
            background: #fff;
            color: #ff9a76;
            border-radius: 30px;
            cursor: pointer;
            transition: all 0.3s ease;
        }
        .tab-btn.active, .tab-btn:hover {
            background: #ff9a76;
            color: #fff;
        }
        .form-content {
            display: none;
        }
        .form-content.show {
            display: block;
        }
        .form-group {
            margin-bottom: 20px;
        }
        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: bold;
            color: #333;
        }
        .form-group input, .form-group textarea {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid #eee;
            border-radius: 10px;
            font-size: 16px;
            outline: none;
            transition: border 0.3s ease;
        }
        .form-group input:focus, .form-group textarea:focus {
            border-color: #ff9a76;
        }
        .submit-btn {
            padding: 12px 40px;
            background: #ff9a76;
            color: #fff;
            border: none;
            border-radius: 30px;
            font-size: 16px;
            cursor: pointer;
            transition: transform 0.3s ease;
        }
        .submit-btn:hover {
            transform: scale(1.05);
        }
        footer {
            background-color: #ff9a76;
            color: #fff;
            text-align: center;
            padding: 30px 0;
            margin-top: 50px;
        }
    </style>
</head>
<body>

<header>
    <div class="nav-container">
        <div class="logo">爪迹</div>
        <nav>
            <ul>
                <li><a href=" " onclick="scrollToSection('intro')">项目介绍</a ></li>
                <li><a href="#cat" onclick="scrollToSection('cat')">猫咪图鉴</a ></li>
                <li><a href="#process" onclick="scrollToSection('process')">救助流程</a ></li>
                <li><a href="#apply" onclick="scrollToSection('apply')">领养/志愿</a ></li>
            </ul>
        </nav>
    </div>
</header>

<section class="banner">
    <h1>爪迹——让流浪不再无助</h1>
    <p>用温暖守护校园流浪生灵，用行动传递生命善意，共建有爱校园</p >
    <button class="banner-btn" onclick="scrollToSection('apply')">立即参与</button>
</section>

<section class="container" id="intro">
    <h2 class="section-title">项目介绍</h2>
    <div class="intro-content">
        <div class="intro-text">
            <p>“爪迹”是四川电力职业技术学院校园流浪动物关怀与公共教育平台，以微信公众号、小程序为核心载体，聚焦校园流浪猫狗救助，打造“发现—记录—照护—绝育—领养”的完整公益闭环。</p >
            <p>我们致力于解决校园流浪动物生存难题，同时开展生命教育与科学救助科普，号召全校师生参与公益行动，让每一只流浪小动物都能被温柔以待，助力构建和谐、有温度的校园生态。</p >
            <p>项目秉承公益初心，实现规范化、可持续化运营，未来将向周边高校推广，打造高校流浪动物公益示范项目。</p >
        </div>
    </div>
</section>

<section class="container" id="cat">
    <h2 class="section-title">校园猫咪图鉴</h2>
    <div class="cat-grid">
        <div class="cat-card" onclick="showCatDetail('橘座')">
            < img src="https://pic.baike.soso.com/ugc/baikepic2/27996/cut-118193514777191113332.jpg/0" alt="橘座">
            <div class="cat-info">
                <h3>橘座</h3>
                <p>性别：公猫</p >
                <p>状态：已绝育、已驱虫</p >
                <p>常驻点：实训楼附近</p >
                <p>性格：温顺黏人，不怕生人</p >
            </div>
        </div>
        <div class="cat-card" onclick="showCatDetail('奶糖')">
            < img src="https://pic.baike.soso.com/ugc/baikepic2/17890/cut-212808020110581113332.jpg/0" alt="奶糖">
            <div class="cat-info">
                <h3>奶糖</h3>
                <p>性别：母猫</p >
                <p>状态：已绝育、已驱虫</p >
                <p>常驻点：教学楼旁</p >
                <p>性格：胆小温柔，爱吃零食</p >
            </div>
        </div>
        <div class="cat-card" onclick="showCatDetail('小黑')">
            < img src="https://pic.baike.soso.com/ugc/baikepic2/24328/cut-118193514777191113332.jpg/0" alt="小黑">
            <div class="cat-info">
                <h3>小黑</h3>
                <p>性别：公猫</p >
                <p>状态：已绝育、已驱虫</p >
                <p>常驻点：宿舍楼下</p >
                <p>性格：活泼好动，亲人亲近</p >
            </div>
        </div>
    </div>
</section>

<section class="container" id="process">
    <h2 class="section-title">救助流程</h2>
    <div class="process-box">
        <div class="process-item" onclick="showProcessTip(1)">
            <h4>发现上报</h4>
            <p>小程序一键上报流浪动物信息</p >
        </div>
        <div class="process-item" onclick="showProcessTip(2)">
            <h4>建档记录</h4>
            <p>完善动物信息，全程跟踪记录</p >
        </div>
        <div class="process-item" onclick="showProcessTip(3)">
            <h4>医疗救助</h4>
            <p>绝育、驱虫、伤病治疗</p >
        </div>
        <div class="process-item" onclick="showProcessTip(4)">
            <h4>领养安置</h4>
            <p>审核领养人，安置温暖新家</p >
        </div>
    </div>
</section>

<section class="container" id="apply">
    <h2 class="section-title">领养/志愿者</h2>
    <div class="form-box">
        <div class="form-tab">
            <button class="tab-btn active" onclick="switchTab('adopt')">领养申请</button>
            <button class="tab-btn" onclick="switchTab('volunteer')">志愿者</button>
        </div>

        <div class="form-content show" id="adopt">
            <div class="form-group">
                <label>姓名</label>
                <input type="text" placeholder="请输入您的姓名">
            </div>
            <div class="form-group">
                <label>手机号</label>
                <input type="tel" placeholder="请输入您的手机号">
            </div>
            <div class="form-group">
                <label>领养猫咪</label>
                <input type="text" placeholder="请填写想领养的猫咪名字">
            </div>
            <div class="form-group">
                <label>个人情况</label>
                <textarea rows="4" placeholder="请说明居住环境、养宠经验等"></textarea>
            </div>
            <button class="submit-btn" onclick="submitForm('领养申请')">提交申请</button>
        </div>

        <div class="form-content" id="volunteer">
            <div class="form-group">
                <label>姓名</label>
                <input type="text" placeholder="请输入您的姓名">
            </div>
            <div class="form-group">
                <label>手机号</label>
                <input type="tel" placeholder="请输入您的手机号">
            </div>
            <div class="form-group">
                <label>志愿方向</label>
                <input type="text" placeholder="投喂/宣传/救助/摄影">
            </div>
            <div class="form-group">
                <label>可参与时间</label>
                <textarea rows="4" placeholder="请填写您可参与志愿的时间"></textarea>
            </div>
            <button class="submit-btn" onclick="submitForm('志愿者报名')">提交报名</button>
        </div>
    </div>
</section>

<footer>
    <p>爪迹——校园流浪动物关怀与公共教育平台</p >
    <p>四川电力职业技术学院 | 公益红旅</p >
    <p>用爱守护，让流浪有归途</p >
</footer>

<script>
    function scrollToSection(id) {
        document.getElementById(id).scrollIntoView({ behavior: 'smooth' });
    }
    function switchTab(tab) {
        document.querySelectorAll('.form-content').forEach(item => item.classList.remove('show'));
        document.querySelectorAll('.tab-btn').forEach(btn => btn.classList.remove('active'));
        document.getElementById(tab).classList.add('show');
        event.target.classList.add('active');
    }
    function showCatDetail(name) {
        alert(`您查看的是猫咪【${name}】的详情，可对接项目团队获取完整信息~`);
    }
    function showProcessTip(step) {
        const tips = [
            '发现流浪动物后，可通过平台小程序上传位置、照片、健康状态，团队第一时间响应！',
            '平台为每只流浪动物建立专属档案，记录性格、健康、出没位置，全程追踪！',
            '联合合作宠物医院，为流浪动物提供低价绝育、驱虫、伤病救治，保障健康！',
            '严格审核领养人资质，定期回访，确保猫咪被妥善照顾，拥有温暖新家！'
        ];
        alert(tips[step-1]);
    }
    function submitForm(type) {
        alert(`${type}提交成功！项目团队将在3个工作日内与您联系~`);
    }
</script>

</body>
</html>
