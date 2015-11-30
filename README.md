# webtest0123
網頁程式設計 測試專案
<!DOCTYPE html>
<html lang="zh_TW">
	<head>
		<meta charset="UTF-8" />
		<title>純 CSS 選單 Example</title>
		<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.9.0/jquery.min.js"></script>
		<script type="text/javascript">
			$(function(){
				$("ul.navigation > li:has(ul) > a").append('<div class="arrow-bottom"></div>');
				$("ul.navigation > li ul li:has(ul) > a").append('<div class="arrow-right"></div>');
			});
		</script>
		<style type="text/css">
			/* 初始化 */
			body, ul, li, a{
				margin: 0;
				padding: 0;
				font-size: 13px;
				text-decoration: none;
			}
			ul, li {
				list-style: none;
			}
			/* 選單 li 之樣式 */
			ul.navigation li {
				position: relative;
				float: left;
			}
			/* 選單 li 裡面連結之樣式 */
			ul.navigation li a{
				display: block;
				padding: 12px 20px;
				background: #888;
				color: #FFF;
			}
			/* 特定在第一層，以左邊灰線分隔 */
			ul.navigation > li > a{
				border-bottom: 1px solid #CCC;				
				border-left: 1px solid #CCC;
			}
			ul.navigation > li > a:hover{
				color: #666;
				background: #DDD
			}
			/* 特定在第一層 > 第二層或以後下拉部分之樣式 */
			ul.navigation ul{
				display: none;
				float: left;
				position: absolute;			
				left: 0;	
				margin: 0;
			}
			/* 當第一層選單被觸發時，指定第二層顯示 */
			ul.navigation li:hover > ul{
				display: block;
			}			
			/* 特定在第二層或以後下拉部分 li 之樣式 */
			ul.navigation ul li {
				border-bottom: 1px solid #DDD;
			}
			/* 特定在第二層或以後下拉部分 li （最後一項不要底線）之樣式 */
			ul.navigation ul li:last-child {
				border-bottom: none;
			}
			/* 第二層或以後選單 li 之樣式 */
			ul.navigation ul a {
				width: 120px;
				padding: 10px 12px;	
				color: #666;		
				background: #EEE;			
			}
			ul.navigation ul a:hover {		
				background: #CCC;				
			}
			/* 第三層之後，上一層的選單觸發則顯示出來（皆為橫向拓展） */
			ul.navigation ul li:hover > ul{
				display: block;
				position: absolute;
				top: 0;				
				left: 100%;
			}
			/* 箭頭向下 */
			.arrow-bottom {
				display: inline-block;
				margin-left: 5px;
				border-top: 4px solid #FFF;
				border-right: 4px solid transparent;				
				border-left: 4px solid transparent;		
				width: 1px;
				height: 1px;
			}

			/* 箭頭向右 */
			.arrow-right {
				display: inline-block;
				margin-left: 12px;	
				border-top: 3px solid transparent;
				border-bottom: 3px solid transparent;
				border-left: 3px solid #666;		
				width: 1px;
				height: 1px;
			}
		</style>		
	</head>
	<body>
		<ul class="navigation">
			<li>
				<a href="#">選單內容 1</a>
				<ul>
					<li><a href="#">選單內容 1 - 1</a></li>
					<li>
						<a href="#">選單內容 1 - 2</a>
						<ul>
							<li><a href="#">選單內容 2 - 1</a></li>
							<li>
								<a href="#">選單內容 2 - 2</a>
								<ul>
									<li><a href="#">選單內容 3 - 1</a>
										<ul>
											<li>
												<a href="#">選單內容 4 - 1</a>
											</li>
											<li>
												<a href="#">選單內容 4 - 2</a>
												<ul>
													<li><a href="#">選單內容 5 - 1</a></li>
													<li>
														<a href="#">選單內容 5 - 2</a>
													</li>	
												</ul>
											</li>	
										</ul>	
									</li>
									<li>
										<a href="#">選單內容 3 - 2</a>
									</li>	
								</ul>
							</li>	
						</ul>
					</li>
				</ul>
			</li>
			<li><a href="#">選單內容 2</a></li>
			<li><a href="#">選單內容 3</a></li>
			<li><a href="#">選單內容 4</a></li>
			<li><a href="#">選單內容 5</a></li>
			<li><a href="#">選單內容 6</a></li>
			<li><a href="#">選單內容 7</a></li>
		</ul>
		<ul>
			<li>123</li>
			<li>456</li>
			<li>789</li>
		</ul>
	</body>
</html>
