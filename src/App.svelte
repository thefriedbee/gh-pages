<script>
	import Header from "./components/Header.svelte";
	import IntroCard from "./components/IntroCard.svelte";
	import Footer from "./components/Footer.svelte";
	import Rightbar from "./components/Rightbar.svelte";
	import PaperCard from "./components/PaperCard.svelte";
    import AboutMe from "./components/AboutMe.svelte";

	import photo_lp from './assets/img/lp_method_comparison.jpeg'
	import photo_tmas from './assets/img/ga_tmas_flow.jpg'
	import photo_rm from './assets/img/travel_speed_plot.png'
	import photo_pnr2 from './assets/img/pnr_modes.png'
	import photo_pnr1 from './assets/img/pnr_carpool.png'
	import photo_gtfs from './assets/img/gtfs2stn_paper.png'
	import photo_cfs_share from './assets/img/cfs_share_by_origin.jpg'
	// add variables/functions for page navigation
	let items = ["Bio", "Papers"];
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

	// add variables for the cards...
	let research_interests = [
		'Scalable data computation tasks (data science)',
		'Machine Learning applications in transportation field (machine learning, deep learning)',
		'Computer Science algorithms, traffic simulation, optimization algorithms, etc.',
	];

	let research_interests_cn = [
		"大数据计算",
		"机器学习/深度学习/强化学习",
		"计算机算法, 交通仿真, 图算法,优化问题等"
	];

	let my_skills = [
		"Programming Language: Python, R, JavaScript/TypeScript, Rust, C++, SQL, git, etc.",
		"Python Packages: Numpy, Matplotlib, Pandas, PyTorch, Keras, Gurobipy, etc.",
		"Industrial Softwares: SUMO, Vissim, ArcGIS, QGIS, Matlab, Simio, etc."
	];

	let my_skills_cn = [
		"编程语言: Python, R, JavaScript/TypeScript, Rust, C++, SQL, git, etc.",
		"编程包: Numpy, Matplotlib, Pandas, PyTorch, Keras, Gurobipy, TraCI, etc.",
		"工业软件: SUMO, Vissim, ArcGIS, QGIS, Matlab, Simio, etc."
	];

	let my_methods = [
		"Modeling: Statistical Machine Learning & Deep Learning.",
		"Optimization: Reinforcement Learning, Linear/Convex Optimization, etc.",
		"Visualization: scientific & interactive diagrams"
	];

	let my_methods_cn = [
		"建模: 统计学习/机器学习",
		"优化: 强化学习/线性优化",
		"可视化: 科学绘图",
	];
</script>

<Header {activeItem} {items} on:tabChange={tabChange}
 {activeLang} {languages} on:langChange={langChange}/>

<main>
	<div class="row">
		<!-- svelte-ignore a11y-no-noninteractive-tabindex -->
		<div class="col-md-9" tabindex="0">

			<AboutMe {activeLang} />

			<hr>

			{#if activeLang == "en"}
				<IntroCard
					title="Research Interests"
					bullets={research_interests}
				/>
			{:else if activeLang == "中"}
				<IntroCard
					title="研究内容:"
					bullets={research_interests_cn}
				/>
			{/if}

			{#if activeLang == "en"}
				<IntroCard
					title="Skillsets"
					bullets={my_skills}
				/>
			{:else if activeLang == "中"}
				<IntroCard
					title="常用技术栈"
					bullets={my_skills_cn}
				/>
			{/if}
			
			{#if activeLang == "en"}
				<IntroCard
					title="Methdologies"
					bullets={my_methods}
				/>
			{:else if activeLang == "中"}
				<IntroCard
					title="研究方法"
					bullets={my_methods_cn}
				/>
			{/if}

			<div class="programs">
				<hr id="Papers">
				<h4>Important Papers & Reports</h4>

			</div>

			<PaperCard
				imageSrc={photo_gtfs}
				title="GTFS2STN: Analyzing GTFS Transit Data By Generating Spatiotemporal Transit Network"
				appLink="https://gtfs2stn.streamlit.app/"
				gitLink="https://github.com/thefriedbee/GTFS2STN"
				summary="GTFS, the General Transit Feed Specialization, is an open standard format 
				to record transit information. A preliminary tool named GTFS2STN is implemented to analyze
				 the accessibility of the transit system.
				 Furthermore, a simple application is built for users to generate spatiotemporal network online.
				 The online tool also supports some basic analysis including generate isochrone maps given origin,
				 generate travel time variability over time given a pair of origin and destination, etc."
			/>

			<PaperCard
				imageSrc={photo_tmas}
				title="An Iterative Algorithm to Impute Traffic Information over Nationwide Traffic Networks"
				summary="
				 Combining Annual Average Daily Traffic (AADT) volume from HPMS and Traffic Monitoring Analysis System (TMAS) dataset, 
				 this study, inspired by Bellman-Ford algorithm, proposes an elegant method of imputing information across the traffic network 
				 to generate both truck volumes and vehicle class distributions. 
				 Results show that the performance of the model achieves an R-square of over 0.4 for truck volume, 
				 outperforming benchmark methods such as Kriging method and Geographical Weighted Regression. 
				 It has great potentials to support traffic analysis, emission modeling, etc."
			/>
			
			<PaperCard
				imageSrc={photo_cfs_share}
				title="Improving the Accuracy of Freight Mode Choice Models"
				webLink=""
				paperLink="https://www.sciencedirect.com/science/article/pii/S0957417423029809"
				summary="Given 2017 Commodity Flow Survey Public Use File data set (6 million records), the proposed model achieved over 92% accuracy 
				in freight mode choice prediction, an over 19% increase against the Random Forests models over 10,000 samples. 
				SHAP (Shapely Additive Explanations) values were computed to explain the outputs."
			/>

			<PaperCard
				imageSrc={photo_lp}
				title="Innovative Method for Estimating Large Truck Volume"
				webLink=""
				paperLink="https://journals.sagepub.com/doi/abs/10.1177/03611981221094569"
				summary="Radar Detectors (or single loop detectors) are the most equipped traffic detectors aggregating traffic volume and occupancy every 20 or 30 seconds for each traffic lane.
				Assuming fleet is only composed of Short and Long Vehicles, we use Linear Programming to speculate the combination of Long/Short vehicles.
				Results are quite similar to the Weigh-in-Motion station results (see left figure comparing results lane by lane) outcompeting most previous proposed methods."
			/>

			<PaperCard
				imageSrc={photo_rm}
				title="Analyzing Robustness of the Deep Reinforcement Learning Algorithm in Ramp Metering Applications"
				webLink=""
				paperLink="https://arxiv.org/abs/2301.12036"
				summary="Ramp metering is the art of smoothly control on-ramp vehicles to the highway mainline.
				We analyzed the robustness of the learning algorithm using both the traditional ALINEA method and the Reinforcement Learning method.
				Furthermore, we try to use False Data Injection to attack and undermine the model.
				Results show that the proposed RL method outcompete ALINEA even under attacks."
			/>

			<PaperCard
				imageSrc={photo_pnr2}
				title="Evaluating Sustainability Impacts of Intelligent Carpooling System among SOV Commuters"
				webLink="https://ncst.ucdavis.edu/project/evaluating-sustainability-impacts-intelligent-carpoolingvanpooling-system-among-sov"
				paperLink=""
				summary="A simulation program and matching algorithm to find the upperbound of carpool potentials among SOV drivers. 
				Two modes are investigated: (1) driver picks up passenger at passegner's home (Direct Carpool mode); 
				(2) both carpooler's meet at a parking lot before carpool together (PNR mode)."
			/>

			<PaperCard
				imageSrc={photo_pnr1}
				title="Evaluating the Sustainability Impacts of Intelligent Carpooling Systems for SOV Commuters"
				webLink="https://escholarship.org/uc/item/9c749361"
				paperLink="https://escholarship.org/uc/item/9c749361"
				summary="A simulation program and matching algorithm to find the upperbound of carpool potentials among SOV drivers."
			/>
			
			<hr>
			<div class="programs">
				<h4>Research programs Involved</h4>
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
			<Rightbar />
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

	h2, h4 {
		color: #555;
		max-width: 960px;
		margin: 20px auto;
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
		margin: 10px;
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