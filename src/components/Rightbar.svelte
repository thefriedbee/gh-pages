<script>
    export let activeLang;
</script>


<segment>
<div class="rightbar">
    <hr>
    {#if activeLang === "en"}
    <h4>Contact Me</h4>
    {:else if activeLang === "中"}
    <h4>联系方式</h4>
    {/if}

    <p>Feel free to contact me by the following ways:</p>
    <ul class="list-group">
        <li class="list-group-item list-group-item-light" >
            Email: <a href="mailto:dliu27@vols.utk.edu"  target="_blank">dliu27@vols.utk.edu</a></li>
        <li class="list-group-item list-group-item-light">
            Github: <a href="https://github.com/thefriedbee/"  target="_blank">thefriedbee</a> </li>
    </ul>

    <hr>
    {#if activeLang === "en"}
    <h4>Papers & Reports:</h4>
    {:else if activeLang === "中"}
    <h4>部分论文/报告</h4>
    {/if}
    
    <ul class="list-group">
        <li class="list-group-item list-group-item-light">
            <a href="https://journals.sagepub.com/doi/abs/10.1177/03611981221094569" target="_blank">
            Long Short Vehicle Identification through RDS records
            </a>
        </li>
        <li class="list-group-item list-group-item-light">
            <a href="https://arxiv.org/abs/2301.12036" target="_blank">
            Ramp Metering Reinforcement Learning
            </a>
        </li>
        <li class="list-group-item list-group-item-light">
            <a href="https://escholarship.org/uc/item/9c749361" target="_blank">
            Carpool Simulation report 1
            </a>
        </li>
        <li class="list-group-item list-group-item-light">
            <a href="https://ncst.ucdavis.edu/project/evaluating-sustainability-impacts-intelligent-carpoolingvanpooling-system-among-sov" target="_blank">
            Carpool Simulation report 2
            </a>
        </li>
    </ul>

    <hr>
    {#if activeLang === "en"}
    <h4>Fun Projects: </h4>
    <ul class="list-group">
        <li class="list-group-item list-group-item-light">
            <a href="https://thefriedbee.github.io/Covid-19-ABM/" target="_blank">Covid-19 Particle Simulation Game</a>
            <br>
            Demonstrate Covid-19 transmission using iteractive buttons, animations and moving particles.
            One particle could transmit virus to another when two particles are close to each other.
            One can recreate SIR-like patterns through this simulation.
            One can play with different strategies to see their effectiveness. 
            <br>
        </li>

        <li class="list-group-item list-group-item-light">
            AI plays 2048
            <br>
            An agent-based algorithms excels at playing 2048
            <br>
        </li>

        <li class="list-group-item list-group-item-light">
            <a href="speed_volume_occupancy.html" target="_blank">3D speed data visualizer</a>
            <br>
            Visualzing the traffic Fundamental Diagram (speed vs. occupancy vs. volume)
            <br>
        </li>

        <li class="list-group-item list-group-item-light">
            <a href="https://github.com/thefriedbee/GTFS2STN" target="_blank">GTFS2STN (v1.0)</a>
            <br>
            Analyzing accessibilities of transit system using the GTFS open source datasets
            <br>
        </li>

        <li class="list-group-item bg-transparent">
            <a href="https://github.com/thefriedbee/CarCounter" target="_blank">Video Car Counter</a>
            <br>
            A local app helps to manually counts vehicles (built by PyQt).
            Generates results as a spreadsheet of vehicle counts. 
            <br>
        </li>

        <li class="list-group-item bg-transparent">
            <!-- <a href="#" target="_blank">PABE</a> -->
            PABE
            <br>
            Plan Ahead and Breathe Ease. A demonstration of using Google Maps API for routing information
            in Python. The App can help you find a travel route miminize inhale air pollution risks, especially for asthma patients.
            <br>
        </li>
    </ul>
    {:else if activeLang === "中"}
    <h4>交互项目: </h4>
    <ul class="list-group">
        <li class="list-group-item list-group-item-light">
            <a href="https://thefriedbee.github.io/Covid-19-ABM/" target="_blank">新冠仿真颗粒模拟小游戏</a>
            <br>
            Demonstrate Covid-19 transmission using iteractive buttons, animations and moving particles.
            One particle could transmit virus to another when two particles are close to each other.
            One can recreate SIR-like patterns through this simulation.
            One can play with different strategies to see their effectiveness. 
            <br>
        </li>

        <li class="list-group-item list-group-item-light">
            AI运行2048小游戏
            <br>
            An agent-based algorithms excels at playing 2048
            <br>
        </li>

        <li class="list-group-item list-group-item-light">
            <a href="speed_volume_occupancy.html" target="_blank">3D可视化交通速度/密度/流量三项关系</a>
            <br>
            Visualzing the traffic Fundamental Diagram (speed vs. occupancy vs. volume)
            <br>
        </li>

        <li class="list-group-item list-group-item-light">
            <a href="https://github.com/thefriedbee/GTFS2STN" target="_blank">公交时刻表数据分析工具GTFS2STN(v1.0)</a>
            <br>
            Analyzing accessibilities of transit system using the GTFS open source datasets
            <br>
        </li>

        <li class="list-group-item bg-transparent">
            <a href="https://github.com/thefriedbee/CarCounter" target="_blank">人工视频数车小软件</a>
            <br>
            A local app helps to manually counts vehicles (built by PyQt)
            Generates results as a spreadsheet of vehicle counts.
            <br>
        </li>

        <li class="list-group-item bg-transparent">
            谷歌地图规划应用(考虑空气污染物摄入量)
            <br>
            Plan Ahead and Breathe Ease. A demonstration of using Google Maps API for routing information
            in Python. The App can help you find a travel route miminize inhale air pollution risks, especially for asthma patients.
            <br>
        </li>
    </ul>
    {/if}
    <hr>
</div>
</segment>


<style>
    .rightbar {
        float: left;
    }

    h4 {
        color: #555;
    }

    .list-group {
        max-width: 300px;
        margin: 20px auto;
    }
</style>

