<script>
	import Header from "./components/Header.svelte";
	import IntroCard from "./components/IntroCard.svelte";
	import Footer from "./components/Footer.svelte";
	import Rightbar from "./components/Rightbar.svelte";
	import PaperCard from "./components/PaperCard.svelte";
    import AboutMe from "./components/AboutMe.svelte";

	import photo_vehicle_track from './assets/img/vehicle_track.png'
	import photo_lp from './assets/img/lp_method_comparison.jpeg'
	import photo_tmas from './assets/img/ga_tmas_flow.jpg'
	import photo_rm from './assets/img/travel_speed_plot.png'
	import photo_pnr2 from './assets/img/pnr_modes.png'
	import photo_pnr1 from './assets/img/pnr_carpool.png'
	import photo_gtfs from './assets/img/gtfs2stn_paper.png'
	import photo_cfs_share from './assets/img/cfs_share_by_origin.jpg'

	// add variables/functions for page navigation
	const items = ["Bio", "Papers"];
	let activeItem = "Bio";
	const tabChange = (e) => {
		activeItem = e.detail;
	}

	// language settings
	const languages = ["中文", "English"]
	let activeLang = "中文";
	const langChange = (e) => {
		activeLang = e.detail;
	}

	// add variables for the cards...
	const research_interests = [
		'Scalable data computation tasks (data science)',
		'Machine Learning applications in transportation field (machine learning, deep learning)',
		'Computer Science algorithms, traffic simulation, optimization algorithms, etc.',
	];

	const research_interests_cn = [
		"机器学习: 深度学习/强化学习/图学习",
		"大数据/统计学习",
		"计算机算法, 交通仿真, 优化问题等"
	];

	const my_skills = [
		"Programming Language: Python, R, JavaScript/TypeScript, Rust, C++, SQL, git, etc.",
		"Python Packages: Numpy, Matplotlib, Pandas, PyTorch, Keras, Gurobipy, etc.",
		"Industrial Softwares: SUMO, VISSIM, CUBE, ArcGIS, QGIS, Matlab, Simio, etc."
	];

	const my_skills_cn = [
		"编程语言: Python, R, JavaScript/TypeScript, Rust, C++, SQL, git, etc.",
		"编程包: Numpy, Matplotlib, Pandas, PyTorch, Keras, Gurobipy, TraCI, etc.",
		"工业软件: SUMO, VISSIM, CUBE, ArcGIS, QGIS, Matlab, Simio, etc."
	];

	const my_methods = [
		"Modeling: Statistical Machine Learning & Deep Learning.",
		"Machine Learning: Deep Learning, Reinforcement Learning, Graph Learning, etc.",
		"Optimization: Linear/Convex Optimization, etc.",
		"Big data: Data Science, Data Visualization, etc.",
	];

	const my_methods_cn = [
		"建模: 统计学习/机器学习",
		"机器学习: 深度学习/强化学习/图学习",
		"优化: 线性优化/凸优化",
		"大数据: 数据科学, 数据可视化等",
	];

	const paper_links_gtfs2stn = {
		"App": "https://gtfs2stn.streamlit.app/",
		"GitHub": "https://github.com/thefriedbee/GTFS2STN",
		"Paper": "https://www.mdpi.com/2078-2489/16/1/24",
	}

	const paper_links_cfs = {
		"Paper": "https://www.sciencedirect.com/science/article/pii/S0957417423029809",
	}

	const paper_links_lp = {
		"Paper": "https://journals.sagepub.com/doi/abs/10.1177/03611981221094569"
	}

	const paper_links_rm = {
		"Paper": "https://arxiv.org/abs/2301.12036"
	}

	const paper_links_pnr2 = {
		"Report": "https://ncst.ucdavis.edu/project/evaluating-sustainability-impacts-intelligent-carpoolingvanpooling-system-among-sov"
	}

	const paper_links_pnr1 = {
		"Report": "https://escholarship.org/uc/item/9c749361",
	}

	
</script>

<Header {activeItem} {items} on:tabChange={tabChange}
 {activeLang} {languages} on:langChange={langChange}/>

<main>
	<div class="row">
		<!-- svelte-ignore a11y-no-noninteractive-tabindex -->
		<div class="col-md-9" tabindex="0">

			<AboutMe {activeLang} />

			<hr>
			{#if activeLang == "English"}
				<IntroCard
					title="Research Interests"
					bullets={research_interests}
				/>
			{:else if activeLang == "中文"}
				<IntroCard
					title="研究内容:"
					bullets={research_interests_cn}
				/>
			{/if}

			{#if activeLang == "English"}
				<IntroCard
					title="Skillsets"
					bullets={my_skills}
				/>
			{:else if activeLang == "中文"}
				<IntroCard
					title="常用技术栈"
					bullets={my_skills_cn}
				/>
			{/if}
			
			{#if activeLang == "English"}
				<IntroCard
					title="Methdologies"
					bullets={my_methods}
				/>
			{:else if activeLang == "中文"}
				<IntroCard
					title="研究方法"
					bullets={my_methods_cn}
				/>
			{/if}

			<div class="programs">
				<hr id="Papers">
				{#if activeLang == "English"}
					<h4>Important Papers & Reports</h4>
				{:else if activeLang == "中文"}
					<h4>重要论文与报告</h4>
				{/if}
			</div>
			
			{#if activeLang == "English"}
				<PaperCard
					imageSrc={photo_vehicle_track}
					title="Identifying vehicles combining YOLO and self-supervised learning on low-resolution CCTV videos"
					summary="It is not possible to use pretrained YOLO to identify all vehicles in low resolution videos.
					This study propose a framework to extra traffic information from low resolution videos
					by decomposing the task is decomposed to four sub-tasks:
					vehicle identification, vehicle classification, vehicle tracking, and trajectory transformation.
					Each task has their own specialized model. YOLO is retrained for vehicle identification.
					SimCLR is applied to learn vehicle representations for classification tasks.
					Finally, ByteTrack is used for vehicle tracking."
					activeLang={activeLang}
				/>
			{:else if activeLang == "中文"}
				<PaperCard
					imageSrc={photo_vehicle_track}
					title="识别低分辨率视频中的车辆信息"
					summary="使用YOLO和自监督学习识别低分辨率视频中的车辆信息"
					activeLang={activeLang}
				/>
			{/if}

			{#if activeLang == "English"}
				<PaperCard
				imageSrc={photo_cfs_share}
				title="Improving the Accuracy of Freight Mode Choice Models"
				links={paper_links_cfs}
				summary="Given 2017 Commodity Flow Survey Public Use File data set (6 million records), the proposed model achieved over 92% accuracy 
					in freight mode choice prediction, an over 19% increase against the Random Forests models over 10,000 samples. 
					SHAP (Shapely Additive Explanations) values were computed to explain the outputs."
					activeLang={activeLang}
				/>
			{:else if activeLang == "中文"}
				<PaperCard
					imageSrc={photo_cfs_share}
					title="提高重载交通系统的预测精度"
					links={paper_links_cfs}
					summary="根据2017年商品流调查公共使用文件数据集(600万条记录), 该模型在重载交通系统预测中实现了超过92%的准确率, 
					比随机森林模型高出19%以上, 并使用SHAP值解释了输出结果."
					activeLang={activeLang}
				/>
			{/if}
			
			{#if activeLang == "English"}
				<PaperCard
					imageSrc={photo_lp}
					title="Innovative Method for Estimating Large Truck Volume"
				links={paper_links_lp}
				summary="Radar Detectors (or single loop detectors) are the most equipped traffic detectors aggregating traffic volume and occupancy every 20 or 30 seconds for each traffic lane.
				Assuming fleet is only composed of Short and Long Vehicles, we use Linear Programming to speculate the combination of Long/Short vehicles.
					Results are quite similar to the Weigh-in-Motion station results (see left figure comparing results lane by lane) outcompeting most previous proposed methods."
					activeLang={activeLang}
				/>
			{:else if activeLang == "中文"}
				<PaperCard
					imageSrc={photo_lp}
					title="创新方法估算重载卡车流量"
					links={paper_links_lp}
					summary="雷达探测器(或单环探测器)是聚合每20或30秒每个车道的车流量和占有率的最常用交通探测器.
					假设车队仅由'短车'(小汽车)和'长车'(拖挂卡车)组成, 我们使用线性规划来推测长/短车辆的组合.
					结果与自动称重站分类的结果相比非常接近。该方法超过了大多数以前提出的分类方法(见左图, 按车道比较结果)."
					activeLang={activeLang}
				/>
			{/if}

			{#if activeLang == "English"}
				<PaperCard
					imageSrc={photo_gtfs}
					title="GTFS2STN: Analyzing Transit Systems Using General Transit Feed Specification (GTFS) by Generating Spatiotemporal Transit Networks "
					links={paper_links_gtfs2stn}
					summary="GTFS, the General Transit Feed Specialization, is an open standard format 
					to record transit information. A preliminary tool named GTFS2STN is implemented to analyze
					the accessibility of the transit system.
					Furthermore, a simple application is built for users to generate spatiotemporal network online.
					The online tool also supports some basic analysis including generate isochrone maps given origin,
					generate travel time variability over time given a pair of origin and destination, etc."
					activeLang={activeLang}
				/>
			{:else if activeLang == "中文"}
				<PaperCard
					imageSrc={photo_gtfs}
					title="通过GTFS公交数据标准自动生成/分析公交时空网络"
					links={paper_links_gtfs2stn}
					summary="GTFS, 通用交通数据标准, 是记录公交信息的标准格式。一个名为GTFS2STN的工具被实现用于分析公交系统的可达性。
					此外，一个简单的应用程序被构建用于用户在线生成公交时空网络。该在线工具还支持一些基本分析，包括生成给定起点的等时线图，
					以及生成给定起点和终点的时间变异性等。"
					activeLang={activeLang}
				/>
			{/if}

			{#if activeLang == "English"}
				<PaperCard
					imageSrc={photo_tmas}
					title="An Iterative Algorithm to Impute Traffic Information over Nationwide Traffic Networks"
					summary="Combining Annual Average Daily Traffic (AADT) volume from HPMS and Traffic Monitoring Analysis System (TMAS) dataset, 
					this study, inspired by Bellman-Ford algorithm, proposes an elegant method of imputing information across the traffic network 
					to generate both truck volumes and vehicle class distributions. 
					Results show that the performance of the model achieves an R-square of over 0.4 for truck volume, 
					outperforming benchmark methods such as Kriging method and Geographical Weighted Regression. 
					It has great potentials to support traffic analysis, emission modeling, etc."
					activeLang={activeLang}
				/>
			{:else if activeLang == "中文"}
				<PaperCard
					imageSrc={photo_tmas}
					title="通过HPMS和TMAS数据集迭代算法估算全国交通网络的交通信息"
					summary="结合HPMS和TMAS数据集, 基于Bellman-Ford算法, 
					提出了一种优雅的方法, 用于估算交通网络上的交通信息, 
					包括卡车流量和车辆分类分布。结果显示，该模型的性能在卡车流量估算方面表现出色，"
					activeLang={activeLang}
				/>
			{/if}
			
			{#if activeLang == "English"}
				<PaperCard
					imageSrc={photo_rm}
					title="Analyzing Robustness of the Deep Reinforcement Learning Algorithm in Ramp Metering Applications"
					links={paper_links_rm}
					summary="Ramp metering is the art of smoothly control on-ramp vehicles to the highway mainline.
					We analyzed the robustness of the learning algorithm using both the traditional ALINEA method and the Reinforcement Learning method.
					Furthermore, we try to use False Data Injection to attack and undermine the model.
					Results show that the proposed RL method outcompete ALINEA even under attacks."
					activeLang={activeLang}
				/>
			{:else if activeLang == "中文"}
				<PaperCard
					imageSrc={photo_rm}
					title="分析深度强化学习算法在匝道控制中的鲁棒性"
					links={paper_links_rm}
					summary="匝道控制是一种通过平滑控制匝道车辆进入高速公路主线的交通控制策略。
						我们使用传统的ALINEA方法和强化学习方法分析了学习算法的鲁棒性。
						此外, 我们尝试使用虚假数据注入攻击和破坏模型。
						结果显示, 提出的RL方法在受到攻击的情况下仍然优于ALINEA方法。"
					activeLang={activeLang}
				/>
			{/if}

			{#if activeLang == "English"}
				<PaperCard
					imageSrc={photo_pnr2}
					title="Evaluating Sustainability Impacts of Intelligent Carpooling System among SOV Commuters"
					links={paper_links_pnr2}
					summary="A simulation program and matching algorithm to find the upperbound of carpool potentials among SOV drivers. 
					Two modes are investigated: (1) driver picks up passenger at passegner's home (Direct Carpool mode); 
					(2) both carpooler's meet at a parking lot before carpool together (PNR mode)."
					activeLang={activeLang}
				/>
			{:else if activeLang == "中文"}
				<PaperCard
					imageSrc={photo_pnr2}
					title="评估智能拼车系统在独自驾车通勤者中的可持续性影响"
					links={paper_links_pnr2}
					summary="一个模拟程序和匹配算法, 用于找到独自驾车通勤者的拼车潜力上限。
					两种模式被研究: (1) 司机在乘客家门口接乘客(直接拼车模式); (2) 司机和乘客在停车场见面后一起拼车(PNR模式)."
					activeLang={activeLang}
				/>
			{/if}

			{#if activeLang == "English"}
				<PaperCard
					imageSrc={photo_pnr1}
					title="Evaluating the Sustainability Impacts of Intelligent Carpooling Systems for SOV Commuters"
					links={paper_links_pnr1}
					summary="A simulation program and matching algorithm to find the upperbound of carpool potentials among SOV drivers."
					activeLang={activeLang}
				/>
			{:else if activeLang == "中文"}
				<PaperCard
					imageSrc={photo_pnr1}
					title="评估智能拼车系统在独自驾车通勤者中的可持续性影响"
					links={paper_links_pnr1}
					summary="一个模拟程序和匹配算法, 用于找到独自驾车通勤者的拼车潜力上限。"
					activeLang={activeLang}
				/>
			{/if}
			<hr>
			<div class="programs">
				{#if activeLang == "English"}
					<h4>Research programs Involved</h4>
				{:else if activeLang == "中文"}
					<h4>参与的研究项目</h4>
				{/if}
				<ul class="list-unstyled">
					<li><a href="https://fersc.utk.edu/research-focus/fersc-projects/">FERSC: Freight Network Resilience Analysis</a></li>
					<li><a href="https://www.nsf.gov/awardsearch/showAward?AWD_ID=2038922&HistoricalAwards=false">CPS: Cyber-Physical System Analysis</a></li>
					<li><a href="https://utorii.com/gate/">GATE Scholarship</a></li>
					<li><a href="https://smartway.tn.gov/">TDOT Smartway</a></li>
					<li><a href="https://ncst.ucdavis.edu/project/evaluating-sustainability-impacts-intelligent-carpoolingvanpooling-system-among-sov">NCST CarpoolSim phase 1</a></li>
					<li><a href="https://ncst.ucdavis.edu/project/evaluating-sustainability-impacts-intelligent-carpooling-system-among-single-occupancy">NCST CarpoolSim phase 2</a></li>
				</ul>
			</div>
		</div>

		<div class="col-md-3">
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
		margin: 20px auto;
		text-align: left;
		background-color: rgba(255, 255, 255, 1.0);
	}

	.list-unstyled {
		margin: 10px auto;
	}

	hr {
		margin: 5px 0;
		padding: 0;
	}

	h2, h4 {
		color: #555;
		max-width: 960px;
		margin: 10px auto;
		text-align: left;
	}

	p {
		max-width: 960px;
		margin: 20px auto;
		text-align: left;
	}

	ul {
		max-width: 960px;
		margin: 20px auto;
		text-align: left;
	}

	h4 {
		font-weight: 900;
	}
	
	.programs{
		margin: 0px;
    	padding: 10px;
	}

	/* style for large screen*/
	@media (min-width: 1080px) {
		main {
			max-width: 1080px;
		}
	}

	/* style for mobile devise*/
	@media (max-width: 768px) {
		main {
			text-align: center;
			padding: 1em;
			max-width: 768px;
			margin: 1px auto;
			text-align: left;
			background-color: rgba(255, 255, 255, 1.0);
		}
	}
</style>