<script>
	// import svelteLogo from './assets/svelte.svg'
	// import viteLogo from '/vite.svg'
	// import Counter from './lib/Counter.svelte'
	import myphoto from "./lib/img/my-img.jpeg"
	
	import Footer from "./components/Footer.svelte"
	import Header from "./components/Header.svelte"
	import Rightbar from "./components/Rightbar.svelte"

	// let name = "Diyi Liu's website";
	let items = ["Bio", "Research", "Skillsets", "Methods", "Tutorial"];
	let activeItem = "Bio";
	const tabChange = (e) => {
		activeItem = e.detail;
	}

	// language settings
	let languages = ["en", "中"]
	let activeLang = "en";

	const langChange = (e) => {
		activeLang = e.detail;
	}
</script>


<Header {activeItem} {items} on:tabChange={tabChange} 
 {activeLang} {languages} on:langChange={langChange}/>

<main>
  <div class="row">
		<!-- svelte-ignore a11y-no-noninteractive-tabindex -->
		<div data-bs-spy="scroll" data-bs-target="#navbar-example2"
		data-bs-offset="0" class="scrollspy-example col-md-8" tabindex="0">
			<hr>
			<div class="row">
				<div class="col-md-8">
					{#if activeLang === "en"}
						<h2 id="Bio" class="myLang">Diyi Liu</h2>

						<ul class="list-unstyled">
							<li>Ph.D student in Transportation Engineering at University of Tennessee, Knoxville</li>
							<li>Advisor: <a href="https://cee.utk.edu/people/lee-d-han/" target="_blank">Dr. Lee D Han</a></li>
						</ul>
					{:else if activeLang === "中"}
						<h2 id="Bio" lang="zh-CN" class="myLang">刘迪一</h2>
						<ul class="list-unstyled">
							<li>田纳西大学, 诺克斯维尔分校(UT, Knoxville)交通工程专业在读博士</li>
							<li>导师: <a href="https://cee.utk.edu/people/lee-d-han/" target="_blank">Dr. Lee D Han(韩立教授)</a></li>
						</ul>
					{/if}
				</div>
				<div class="col-md-4">
					<img src={myphoto} class="img-fluid" alt="My Photo">
				</div>
			</div>
			
			<hr>
			{#if activeLang === "en"}
				<h2 id="Research">Research Interests</h2>
				<ul class="list-unstyled">
					<li>Scalable data computation tasks</li>
					<li>Machine Learning applications</li>
					<li>Computer Science algorithms, traffic simulation, optimization algorithms, etc.</li>
				</ul>
			{:else if activeLang === "中"}
				<h2 id="Research">研究兴趣,与交通相关的:</h2>
				<ul class="list-unstyled">
					<li>大数据计算</li>
					<li>机器学习/深度学习</li>
					<li>计算机算法, 交通仿真, 图算法,优化问题等</li>
				</ul>
			{/if}
			
			<hr>
			{#if activeLang === "en"}
				<h2>Programs Involved</h2>
				<ul class="list-unstyled">
					<li><a href="https://www.nsf.gov/awardsearch/showAward?AWD_ID=2038922&HistoricalAwards=false" target="_blank">CPS program</a></li>
					<li><a href="https://utorii.com/gate/" target="_blank">GATE scholarship</a></li>
					<li><a href="https://smartway.tn.gov/" target="_blank">TDOT Smartway</a></li>
					<li><a href="https://ncst.ucdavis.edu/project/evaluating-sustainability-impacts-intelligent-carpoolingvanpooling-system-among-sov" target="_blank">NCST 1</a></li>
					<li><a href="https://ncst.ucdavis.edu/project/evaluating-sustainability-impacts-intelligent-carpooling-system-among-single-occupancy" target="_blank">NCST 2</a></li>
				</ul>
			{:else if activeLang === "中"}
				<h2>近期项目</h2>
				<ul class="list-unstyled">
					<li><a href="https://www.nsf.gov/awardsearch/showAward?AWD_ID=2038922&HistoricalAwards=false" target="_blank">CPS program</a></li>
					<li><a href="https://utorii.com/gate/" target="_blank">GATE scholarship</a></li>
					<li><a href="https://smartway.tn.gov/" target="_blank">TDOT Smartway</a></li>
					<li><a href="https://ncst.ucdavis.edu/project/evaluating-sustainability-impacts-intelligent-carpoolingvanpooling-system-among-sov" target="_blank">NCST 1</a></li>
					<li><a href="https://ncst.ucdavis.edu/project/evaluating-sustainability-impacts-intelligent-carpooling-system-among-single-occupancy" target="_blank">NCST 2</a></li>
				</ul>
			{/if}

			<hr>
			{#if activeLang === "en"}
			<h2>Important Papers & Reports</h2>
				<ul class="list-unstyled">
					<li><a href="https://journals.sagepub.com/doi/abs/10.1177/03611981221094569" target="_blank">
						Innovative Method for Estimating Large Truck Volume Using Aggregate Volume and Occupancy Data Incorporating Empirical Knowledge Into Linear Programming</a></li>
					<br>
					<li><a href="https://arxiv.org/abs/2301.12036" target="_blank">
			Analyzing Robustness of the Deep Reinforcement Learning Algorithm in Ramp Metering Applications Considering False Data Injection Attack and Defense</li>
					<br>
			<li><a href="https://escholarship.org/uc/item/9c749361" target="_blank">
						Evaluating the Sustainability Impacts of Intelligent Carpooling Systems for SOV Commuters in the Atlanta Region</a></li>
					<br>
					<li><a href="https://ncst.ucdavis.edu/project/evaluating-sustainability-impacts-intelligent-carpoolingvanpooling-system-among-sov" target="_blank">
			Evaluating Sustainability Impacts of Intelligent Carpooling/Vanpooling System among SOV Commuters, Phase II: Park and Ride Interactions</li>
					<br>
				</ul>
			{:else if activeLang === "中"}
			<h2>部分重要的发表文章/报告</h2>
			<ul class="list-unstyled">
				<li><a href="https://journals.sagepub.com/doi/abs/10.1177/03611981221094569" target="_blank">
					Innovative Method for Estimating Large Truck Volume Using Aggregate Volume and Occupancy Data Incorporating Empirical Knowledge Into Linear Programming</a></li>
				<br>
				<li><a href="https://arxiv.org/abs/2301.12036" target="_blank">
					Analyzing Robustness of the Deep Reinforcement Learning Algorithm in Ramp Metering Applications Considering False Data Injection Attack and Defense</li>
				<br>	
				<li><a href="https://escholarship.org/uc/item/9c749361" target="_blank">
					Evaluating the Sustainability Impacts of Intelligent Carpooling Systems for SOV Commuters in the Atlanta Region</a></li>
				<br>
				<li><a href="https://ncst.ucdavis.edu/project/evaluating-sustainability-impacts-intelligent-carpoolingvanpooling-system-among-sov" target="_blank">
					Evaluating Sustainability Impacts of Intelligent Carpooling/Vanpooling System among SOV Commuters, Phase II: Park and Ride Interactions</li>
				<br>
			</ul>
			{/if}

			<hr>
			{#if activeLang === "en"}
			<h2 id="Skillsets">Skillsets</h2>
			<ul class="list-unstyled">
				<li>Programming Language: Python, R, JavaScript, C++, SQL, git, etc.</li>
				<li>Python Packages: Numpy, Matplotlib, Pandas, PyTorch, Keras, Gurobipy, TraCI, etc.</li>
				<li>Industrial Softwares: SUMO, Vissim, ArcGIS, QGIS, Matlab, Simio, etc.</li>
			</ul>
			{:else if activeLang === "中"}
			<h2 id="Skillsets">常用技术栈</h2>
			<ul class="list-unstyled">
				<li>编程语言: Python, R, JavaScript, C++, SQL, git, etc.</li>
				<li>编程包: Numpy, Matplotlib, Pandas, PyTorch, Keras, Gurobipy, TraCI, etc.</li>
				<li>工业软件: SUMO, Vissim, ArcGIS, QGIS, Matlab, Simio, etc.</li>
			</ul>
			{/if}

			<hr>
			{#if activeLang === "en"}
			<h2 id="Methods">Methods</h2>
			<ul class="list-unstyled">
				<li>Modeling: Statistical Machine Learning & Deep Learning.</li>
				<li>Optimization: Reinforcement Learning, Linear/Convex Optimization, etc.</li>
				<li>Visualization: scientific & interactive diagrams</li>
			</ul>
			{:else if activeLang === "中"}
			<h2 id="Methods">常用方法</h2>
			<ul class="list-unstyled">
				<li>建模: 统计学习/机器学习</li>
				<li>优化: 强化学习/线性优化</li>
				<li>可视化: 科学绘图</li>
			</ul>
			{/if}

			<hr>
			{#if activeLang === "en"}
			<h2 id="Tutorial">Public Tutorials</h2>
			{:else if activeLang === "中"}
			<h2 id="Tutorial">公开课/经验分享</h2>
			{/if}
			<!-- links to some of my tutorials on Bilibili or other websites -->
			<ul class="list-unstyled">
				<li>
					Bilibili: <a href="https://www.bilibili.com/video/BV17u411n7t8/" target="_blank">
						极客鸭geekDuckKonig
					</a>
				</li>
				<li>
					YouTube: <a href="https://www.youtube.com/channel/UC0thVOWX4ABslMUR_YGwgDA">
					geekDuckKonig
					</a>
				</li>
				<li>
					Github: <a href="https://github.com/thefriedbee/video-source-code">
					video repository
					</a>
				</li>
			</ul>
			<hr>
		</div>

		<div class="col-md-4">
			<Rightbar {activeLang} />
		</div>
	</div>
</main>

<Footer />


<style>
  main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 40px auto;
		text-align: left;
		background-color: rgba(255, 255, 255, 1.0);
	}

	/* h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	} */

	@media (min-width: 640px) {
		main {
			max-width: 1080px;
		}
	}

	h2 {
		color: #555;
		max-width: 960px;
		margin: 20px auto;
		text-align: left;
	}

	/* p {
		max-width: 960px;
		margin: 20px auto;
		text-align: left;
	} */
</style>
