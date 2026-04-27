<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ザ・フューチャー協同組合</title>
    <style>
        /* 基础重置与全局样式 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        :root {
            /* 品牌主色（日式商务沉稳蓝） */
            --primary: #003366;
            --primary-light: #004080;
            --primary-accent: #0066cc;
            /* 中性色（层次化） */
            --neutral-100: #f8fafc;
            --neutral-200: #f0f4f8;
            --neutral-300: #e2e8f0;
            --neutral-600: #475569;
            --neutral-700: #334155;
            --neutral-800: #1e293b;
            /* 阴影层级 */
            --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.05);
            --shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.08), 0 2px 4px -1px rgba(0, 0, 0, 0.04);
            --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
            /* 过渡动画 */
            --transition: all 0.4s cubic-bezier(0.25, 0.1, 0.25, 1);
        }

        body {
            font-family: "Noto Sans JP", "ヒラギノ角ゴ Pro W3", "Hiragino Kaku Gothic Pro", "ＭＳ Ｐゴシック", sans-serif;
            color: var(--neutral-700);
            line-height: 1.8;
            background: linear-gradient(180deg, var(--neutral-100) 0%, var(--neutral-200) 100%);
            /* 文字抗锯齿，提升精致度 */
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
            /* 平滑滚动 */
            scroll-behavior: smooth;
            min-height: 100vh;
        }

        .wrap {
            max-width: 900px;
            margin: 0 auto;
            padding: 0 24px;
        }

        /* 顶部Banner（高端质感核心） */
        .banner {
            width: 100%;
            height: 220px;
            /* 渐变叠加+图片，提升层次感 */
            background: linear-gradient(rgba(0, 20, 40, 0.65), rgba(0, 30, 60, 0.75)), 
                        url('https://picsum.photos/id/1076/1920/400') center/cover no-repeat;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-bottom: 40px;
            /* 多层阴影+轻微模糊，营造悬浮感 */
            box-shadow: var(--shadow-lg);
            /* 顶部轻微圆角，避免生硬 */
            border-radius: 0 0 16px 16px;
            position: relative;
            overflow: hidden;
        }

        /* Banner装饰性光效（高端细节） */
        .banner::after {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            width: 40%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.08));
            transform: skewX(-15deg) translateX(100%);
            animation: light-flow 8s infinite linear;
        }

        @keyframes light-flow {
            0% { transform: skewX(-15deg) translateX(100%); }
            100% { transform: skewX(-15deg) translateX(-200%); }
        }

        .banner h1 {
            font-size: 36px;
            color: #fff;
            text-shadow: 0 2px 8px rgba(0, 0, 0, 0.3);
            letter-spacing: 3px;
            font-weight: 500;
            /* 轻微发光效果 */
            text-shadow: 0 0 10px rgba(255, 255, 255, 0.15);
        }

        /* 导航栏（克制的高端感） */
        .nav {
            text-align: center;
            margin-bottom: 48px;
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
        }

        .nav a {
            display: inline-block;
            padding: 12px 32px;
            background: var(--primary);
            color: #fff;
            border-radius: 50px;
            text-decoration: none;
            transition: var(--transition);
            box-shadow: var(--shadow-sm);
            font-size: 15px;
            letter-spacing: 0.5px;
            /* 边框质感 */
            border: 1px solid transparent;
            position: relative;
            overflow: hidden;
        }

        /* 导航按钮hover动效（高端交互） */
        .nav a::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transition: var(--transition);
        }

        .nav a:hover {
            background: var(--primary-light);
            transform: translateY(-3px);
            box-shadow: var(--shadow-md);
            border-color: rgba(255, 255, 255, 0.2);
        }

        .nav a:hover::before {
            left: 100%;
        }

        /* 内容容器（卡片质感） */
        .content {
            background: #fff;
            padding: 48px;
            border-radius: 20px;
            /* 多层阴影营造深度 */
            box-shadow: var(--shadow-md);
            margin-bottom: 48px;
            position: relative;
            overflow: hidden;
            /* 轻微内阴影，提升材质感 */
            box-shadow: 0 8px 30px rgba(0, 0, 0, 0.06), inset 0 1px 0 rgba(255, 255, 255, 0.8);
            border: 1px solid rgba(255, 255, 255, 0.9);
        }

        /* 内容板块装饰（低饱和度，不抢焦点） */
        .content::before {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            width: 180px;
            height: 180px;
            background: linear-gradient(rgba(0, 51, 102, 0.03), rgba(0, 102, 204, 0.02)),
                        url('https://picsum.photos/id/180/300/300') center/cover no-repeat;
            opacity: 0.06;
            border-radius: 0 20px 0 0;
        }

        /* 标题样式（层次化） */
        h2 {
            font-size: 24px;
            margin: 36px 0 20px;
            color: var(--primary);
            border-left: 4px solid var(--primary-accent);
            padding-left: 20px;
            position: relative;
            font-weight: 500;
            letter-spacing: 0.8px;
        }

        h2:first-child {
            margin-top: 0;
        }

        /* 标题下划线（精致细节） */
        h2::after {
            content: '';
            position: absolute;
            bottom: -8px;
            left: 20px;
            width: 80px;
            height: 2px;
            background: linear-gradient(90deg, var(--primary-accent), transparent);
            opacity: 0.6;
            border-radius: 1px;
        }

        /* 页面切换基础样式 */
        .page {
            display: none;
            animation: fade-in 0.6s ease;
        }

        .page.on {
            display: block;
        }

        @keyframes fade-in {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        /* 组合介绍信息样式 */
        .intro-info p {
            color: var(--neutral-700);
            margin-bottom: 12px;
            font-size: 16px;
            padding-left: 8px;
            border-left: 2px solid transparent;
            transition: var(--transition);
        }

        .intro-info p:hover {
            border-left: 2px solid var(--primary-accent);
            color: var(--neutral-800);
        }

        .intro-info p strong {
            color: var(--primary);
            font-weight: 500;
        }

        /* 核心说明区块（质感突出） */
        .intro-desc {
            margin-top: 24px;
            padding: 20px 24px;
            background: linear-gradient(135deg, var(--neutral-100) 0%, var(--neutral-200) 100%);
            border-left: 3px solid var(--primary-accent);
            color: var(--neutral-700);
            border-radius: 0 8px 8px 0;
            box-shadow: var(--shadow-sm);
            font-size: 15.5px;
            line-height: 1.9;
        }

        /* 规程板块样式 */
        .rule-section {
            margin-bottom: 32px;
            padding-bottom: 20px;
            border-bottom: 1px dashed var(--neutral-300);
        }

        .rule-section p {
            color: var(--neutral-600);
            margin-bottom: 12px;
            font-size: 15px;
            line-height: 1.85;
        }

        .rule-section p:first-child {
            font-weight: 500;
            color: var(--primary);
            font-size: 18px;
            margin-bottom: 16px;
            letter-spacing: 0.5px;
        }

        /* 签名样式（正式感） */
        .signature {
            color: var(--neutral-800);
            font-weight: 500;
            font-size: 15px;
            letter-spacing: 0.8px;
        }

        /* 高亮文本（联系方式） */
        .highlight-text {
            color: var(--primary-accent);
            font-weight: 500;
            /* 轻微发光，突出重要信息 */
            text-shadow: 0 0 5px rgba(0, 102, 204, 0.1);
        }

        /* 响应式适配（移动端保持质感） */
        @media (max-width: 768px) {
            .banner {
                height: 180px;
            }
            .banner h1 {
                font-size: 28px;
            }
            .content {
                padding: 32px 24px;
                border-radius: 16px;
            }
            .nav a {
                padding: 10px 24px;
            }
            h2 {
                font-size: 20px;
            }
        }
    </style>
</head>
<body>
    <!-- 顶部banner -->
    <div class="banner">
        <h1>ザ・フューチャー協同組合</h1>
    </div>

    <div class="wrap">
        <div class="nav">
            <a href="javascript:switchPage('intro')">組合紹介</a>
            <a href="javascript:switchPage('rule')">運営規程</a>
        </div>

        <!-- 組合紹介 -->
        <div id="intro" class="page on content">
            <h2>組合概要</h2>
            <div class="intro-info">
                <p><strong>■ 組合名：</strong>ザ・フューチャー協同組合</p>
                <p><strong>■ 代表者：</strong>苗　欣</p>
                <p><strong>■ 設立日：</strong>2023年1月31日</p>
                <p><strong>■ 事務所：</strong>〒466-0824 愛知県名古屋市昭和区川名町4－24 中商ビル401</p>
                <p><strong>■ TEL：</strong><span class="highlight-text">052-870-4041</span></p>
                <p><strong>■ FAX：</strong><span class="highlight-text">052-308-4638</span></p>
                <p><strong>■ メール：</strong><span class="highlight-text">futurejp.mx@gmail.com</span></p>
                <p><strong>■ 監理団体許可番号：</strong>許2306000068</p>
                <p><strong>■ 登録支援機関許可番号：</strong>23登-009000</p>
                <p><strong>■ 無料職業紹介事業許可番号:</strong>23-特-000292</p>
                <p><strong>■ 認可地区：</strong>栃木県　群馬県　埼玉県　千葉県　岐阜県　愛知県　三重県　滋賀県　大阪府　広島県</p>
                <p><strong>■ 受入れ国：</strong>中国　ベトナム　インドネシア　ミャンマー</p>
            </div>
            
            <div class="intro-desc">
                <p>当組合は、外国人技能実習生及び特定技能外国人の適正な受入れ・支援を行う監理団体・登録支援機関です。</p>
                <p>法令遵守を基本とし、企業と外国人材の架け橋となり、安定した運営と信頼性の高いサポートを提供いたします。</p>
            </div>
        </div>

        <!-- 運営規定 -->
        <div id="rule" class="page content">
            <h2>監理団体の業務の運営に関する規程</h2>
            
            <div class="rule-section">
                <p>事業所名 ザ・フューチャー協同組合</p>
            </div>
            
            <div class="rule-section">
                <p>第１ 目的</p>
                <p>この規定は、外国人の技能実習の適正な実施及び技能実習生の保護に関する法律及びその関係法令（以下「技能実習関係法令」という。）に基づいて、本事業所において 監理事業を行うに当たって必要な事項について、規程として定めるものです。</p>
            </div>
            
            <div class="rule-section">
                <p>第２ 求人</p>
                <p>１ 本事業所は、（取扱職種の範囲等）の技能実習に関するもの限り、いかなる求人の申 込みについてもこれを受理します。 ただし、その申込みの内容が法令に違反する場合、その申込みの内容である賃金、 労働時間その他の労働条件が通常の労働条件と比べて著しく不適当であると認める場合、又は団体監理型実習実施者等が労働条件等の明示をしない場合は、その申込みを 受理しません。</p>
                <p>２ 求人の申込みは、団体監理型実習実施者等（団体監理型実習実施者又は団体監理型 実習実施者になろうとする者をいう。以下同じ。）又はその代理人の方が直接来所され て、所定の求人票によりお申込みください。なお、直接来所できないときは、郵便、 電話、ファックス又は電子メールでも差し支えありません。</p>
                <p>３ 求人申込みの際には、業務の内容、賃金、労働時間その他の労働条件をあらかじめ 書面の交付又は電子メールの使用により明示してください。ただし、紹介の実施について緊急の必要があるため、あらかじめ書面の交付又は電子メールの使用による明示 ができないときは、当該明示すべき事項をあらかじめこれらの方法以外の方法により 明示してください。</p>
                <p>４ 求人受付の際には、監理費（職業紹介費）を、別表の監理費表に基づき申し受けます。いったん申し受けました手数料は、紹介の成否にかかわらずお返しいたしません。</p>
            </div>
            
            <div class="rule-section">
                <p>第３ 求職</p>
                <p>１ 本事業所は、（取扱職種の範囲等）の技能実習に関する限り、いかなる求職の申込み についてもこれを受理します。 ただし、その申込みの内容が法令に違反するときは、これを受理しません。</p>
                <p>２ 求職申込みは、団体監理型技能実習生等（団体監理型技能実習生又は団体監理型技 能実習生になろうとする者をいう。以下同じ。）又はその代理人（外国の送出機関から 求職の申込みの取次ぎを受けるときは、外国の送出機関）から、所定の求人票によりお申込みください。郵便、電話、ファックス又は電子メールで差し支えありません。</p>
            </div>
            
            <div class="rule-section">
                <p>第４ 技能実習に関する職業紹介</p>
                <p>１ 団体監理型技能実習生等の方には、職業安定法第２条にも規定される職業選択の自由の趣旨を踏まえ、その御希望と能力に応ずる職業に速やかに就くことができるよう 極力お世話いたします。</p>
                <p>２ 団体監理型実習実施者等の方には、その御希望に適合する団体監理型技能実習生等を極力お世話いたします。</p>
                <p>３ 技能実習職業紹介に際しては、団体監理型技能実習生等の方に、技能実習に関する職業紹介において、従事することとなる業務の内容、賃金、労働時間その他の労働条 件をあらかじめ書面の交付又は希望される場合には電子メールの使用により明示します。ただし、技能実習に関する職業紹介の実施について緊急の必要があるためあらかじめ書面の交付又は電子メールの使用による明示ができないときは、あらかじめそれらの方法以外の方法により明示を行います。</p>
                <p>４ 団体監理型技能実習生等の方を団体監理型実習実施者等に紹介する場合には、紹介状を発行します。その紹介状を持参して団体監理型実習実施者等との面接を行っていただきます。</p>
                <p>５ いったん求人、求職の申込みを受けた以上、責任をもって技能実習に関する職業紹介の労をとります。</p>
                <p>６ 本事業所は、労働争議に対する中立の立場をとるため、同盟罷業又は作業閉鎖の行われている間は団体監理型実習実施者等に、技能実習に関する職業紹介をいたしません。</p>
                <p>７ 就職が決定しましたら求人された方から監理費（職業紹介費）を、別表の監理費表に基づき申し受けます。</p>
            </div>
            
            <div class="rule-section">
                <p>第５ 団体監理型技能実習の実施に関する監理</p>
                <p>１ 団体監理型実習実施者が認定計画に従って技能実習を行わせているか等、監理責任 者の指揮の下、主務省令第 52 条第１号イからホまでに定める方法（団体監理型技能実 習生が従事する業務の性質上当該方法によることが著しく困難な場合にあっては、他の適切な方法）によって３か月に１回以上の頻度で監査を行うほか、実習認定の取消し事由に該当する疑いがあると認めたときは、直ちに監査を行います。</p>
                <p>２ 第１号団体監理型技能実習に係る実習監理にあっては、監理責任者の指揮の下、１か月に１回以上の頻度で、団体監理型実習実施者が認定計画に従って団体監理型技能実習を行わせているかについて実地による確認（団体監理型技能実習生が従事する業務の性質上当該方法によることが著しく困難な場合にあっては、他の適切な方法による確認）を行うとともに、団体監理型実習実施者に対し必要な指導を行います。</p>
                <p>３ 技能実習を労働力の需給の調整の手段と誤認させるような方法で、団体監理型実習実施者等の勧誘又は監理事業の紹介をしません。</p>
                <p>４ 第一号団体監理型技能実習にあっては、認定計画に従って入国後講習を実施し、かつ、入国後講習の期間中は、団体監理型技能実習生を業務に従事させません。</p>
                <p>５ 技能実習計画作成の指導に当たって、団体監理型技能実習を行わせる事業所及び団 体監理型技能実習生の宿泊施設を実地に確認するほか、主務省令第52 条第８号イからハに規定する観点から指導を行います。</p>
                <p>６ 技能実習生の帰国旅費（第３号技能実習の開始前の一時帰国を含む。）を負担するとともに技能実習生が円滑に帰国できるよう必要な措置を講じます。</p>
                <p>７ 団体監理型技能実習生との間で認定計画と反する内容の取決めをしません。</p>
                <p>８ 実習監理を行っている団体監理型技能実習生からの相談に適切に応じるとともに、 団体監理型実習実施者及び団体監理型技能実習生への助言、指導その他の必要な措置 が講じます。</p>
                <p>９ 本事業所内に監理団体の許可証を備え付けるとともに、本規程をインターネットに より公表（インターネットによる公表が困難である相当の理由がある場合は本事業所内の一般の閲覧に便利な場所に本規程を掲示）します。</p>
                <p>10 技能実習の実施が困難となった場合には、技能実習生が引き続き技能実習を行うことを希望するものが技能実習を行うことができるよう、他の監理団体等との連絡調整等を行います。</p>
                <p>11 上記のほか、技能実習関係法令に従って業務を実施します。</p>
            </div>
            
            <div class="rule-section">
                <p>第６ 監理責任者</p>
                <p>１ 本事業所の監理責任者は、苗　欣です。</p>
                <p>２ 監理責任者は、以下に関する事項を統括管理します。</p>
                <p>(1) 団体監理型技能実習生の受入れの準備</p>
                <p>(2) 団体監理型技能実習生の技能等の修得等に関する団体監理型実習実施者への指導及び助言並びに団体監理型実習実施者との連絡調整</p>
                <p>(3) 団体監理型技能実習生の保護</p>
                <p>(4) 団体監理型実習実施者等及び団体監理型技能実習生等の個人情報の管理</p>
                <p>(5) 団体監理型技能実習生の労働条件、産業安全及び労働衛生に関し、技能実習責任者との連絡調整に関すること</p>
                <p>(6) 国及び地方公共団体の機関、機構その他関係機関との連絡調整。</p>
            </div>
            
            <div class="rule-section">
                <p>第７ 監理費の徴収</p>
                <p>１ 監理費は、団体監理型実習実施者等へあらかじめ用途及び金額を明示した上で徴収します。</p>
                <p>２ 監理費（職業紹介費）は、団体監理型実習実施者等から求人の申込みを受理した時 以降に当該団体監理型実習実施者等から、別表の監理費表に基づき申し受けます。その額は、団体監理型実習実施者等と団体監理型技能実習生等との間における雇用関係の成立のあっせんに係る事務に要する費用（募集及び選抜に要する人件費、交通費、外国の送出機関へ支払う費用その他の実費に限る。）の額を超えない額とします。</p>
                <p>３ 監理費（講習費）は、入国前講習に要する費用にあっては入国前講習の開始日以降 に、入国後講習に要する費用にあっては入国後講習の開始日以降に、団体監理型実習 実施者等から、別表の監理費表に基づき申し受けます。 その額は、監理団体が実施する入国前講習及び入国後講習に要する費用（監理団体 が支出する施設使用料、講師及び通訳人への謝金、教材費、第一号団体監理型技能実 習生に支給する手当その他の実費に限る。）の額を超えない額とします。</p>
                <p>４ 監理費（監査指導費）は、入団体監理型技能実習生が団体監理型実習実施者の事業 所において業務に従事し始めた時以降一定期間ごとに当該団体監理型実習実施者から、 別表の監理費表に基づき申し受けます。 その額は、団体監理型技能実習の実施に関する監理に要する費用（団体監理型実習 実施者に対する監査及び指導に要する人件費、交通費その他の実費に限る。）の額を超 えない額とします。</p>
                <p>５ 監理費（その他諸経費）は、当該費用が必要となった時以降に団体監理型実習実施 者等から、別表の監理費表に基づき申し受けます。その額は、その他技能実習の適正な実施及び技能実習生の保護に資する費用（実費に限る。）の額を超えない額とします。</p>
            </div>
            
            <div class="rule-section">
                <p>第８ その他</p>
                <p>１ 本事業所は、国及び地方公共団体の機関であって技能実習に関する事務を所掌するもの、外国人技能実習機構その他関係機関と連携を図りつつ、当該事業に係る団体監理型実習実施者等又は団体監理型技能実習生等からの苦情があった場合には、迅速に、適切に対応いたします。</p>
                <p>２ 雇用関係が成立しましたら、団体監理型実習実施者等、団体監理型技能実習生等の 両方から本事業所に対して、その報告をしてください。また、技能実習に関する職業紹介されたにもかかわらず、雇用関係が成立しなかったときにも同様に報告をしてください。</p>
                <p>３ 本事業所は、団体監理型技能実習生等の方又は団体監理型実習実施者等から知り得 た個人的な情報は個人情報適正管理規程に基づき、適正に取り扱います。</p>
                <p>４ 本事業所は、団体監理型技能実習生等又は団体監理型実習実施者等に対し、その申込みの受理、面接、指導、技能実習に関する職業紹介等の業務について、人種、国籍、信条、性別、社会的身分、門地、従前の職業、労働組合の組合員であること等を理由として差別的な取扱いは一切いたしません。</p>
                <p>５ 本事業所の取扱職種の範囲等は、別紙添付通りです。</p>
                <p>６ 本事業所の業務の運営に関する規程は、以上のとおりですが、本事業所の業務は、全て技能実習関係法令に基づいて運営されますので、御不審の点は係員に詳しくお尋ねください。</p>
            </div>
        </div>
    </div>

    <script>
        function switchPage(id){
            document.querySelectorAll('.page').forEach(item=>{
                item.classList.remove('on');
            });
            document.getElementById(id).classList.add('on');
        }
    </script>
</body>
</html>
