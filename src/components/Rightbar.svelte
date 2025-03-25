<script>
    export let activeLang;
</script>


<segment>
<div class="rightbar">
    <hr>
    {#if activeLang == "English"}
        <h4>Contact Me</h4>
    {:else if activeLang == "中文"}
        <h4>联系方式</h4>
    {/if}

    <ul class="list-group">
        <!-- <li class="list-group-item">Email: diyi93@outlook.com</li> -->
        <li class="list-group-item list-group-item-light" >
            Email: <a href="mailto:diyi.liu@gwu.edu">diyi.liu@gwu.edu</a></li>
        <li class="list-group-item list-group-item-light">
            Github: <a href="https://github.com/thefriedbee/">thefriedbee</a> </li>
    </ul>

    <hr>
    {#if activeLang == "English"}
        <h4>Fun Projects</h4>
    {:else if activeLang == "中文"}
        <h4>应用/网站项目</h4>
    {/if}

    <ul class="list-group">
        <li class="list-group-item list-group-item-light">
            {#if activeLang == "English"}
                <a href="https://thefriedbee.github.io/Covid-19-ABM/" target="_blank">Covid-19 Particle Simulation Game</a>
                <br>
                Demonstrate Covid-19 transmission using iteractive buttons, animations and moving particles.
                One particle could transmit virus to another when two particles are close to each other.
                One can recreate SIR-like patterns through this simulation.
                One can play with different strategies to see their effectiveness. 
                <br>
            {:else if activeLang == "中文"}
                <a href="https://thefriedbee.github.io/Covid-19-ABM/" target="_blank">疫情粒子模拟游戏</a>
            {/if}
        </li>
        <li class="list-group-item list-group-item-light">
            {#if activeLang == "English"}
                AI plays 2048
                <br>
                An agent-based algorithms excels at playing 2048
                <br>
            {:else if activeLang == "中文"}
                AI智能体玩2048
            {/if}
        </li>
        <li class="list-group-item list-group-item-light">
            {#if activeLang == "English"}
                <a href="speed_volume_occupancy.html" target="_blank">3D data visualizer</a>
                <br>
                    Visualzing the traffic Fundamental Diagram (speed vs. occupancy vs. volume)
                <br>
            {:else if activeLang == "中文"}
                <a href="speed_volume_occupancy.html" target="_blank">3D数据可视化</a>
                <br>
                    可视化交通基本图 (速度 vs. 占用率 vs. 流量)
                <br>
            {/if}
        </li>

        <li class="list-group-item list-group-item-light">
            {#if activeLang == "English"}
                <a href="https://github.com/thefriedbee/GTFS2STN" target="_blank">GTFS2STN (v1.0)</a>
                <br>
                Analyzing accessibilities of transit system using the GTFS open source datasets
                <br>
            {:else if activeLang == "中文"}
                <a href="https://github.com/thefriedbee/GTFS2STN" target="_blank">GTFS2STN (v1.0)</a>
                <br>
                使用GTFS开源数据集生成公交+步行时空网络
                <br>
            {/if}
        </li>

        <li class="list-group-item bg-transparent">
            {#if activeLang == "English"}
                <a href="https://github.com/thefriedbee/CarCounter" target="_blank">Video Car Counter</a>
                <br>
                A local app helps to manually counts vehicles (built by PyQt)
                <br>
            {:else if activeLang == "中文"}
                <a href="https://github.com/thefriedbee/CarCounter" target="_blank">视频车辆计数器</a>
                <br>
                手动计数车辆软件
                <br>
            {/if}
        </li>
    </ul>
    <hr>
</div>
</segment>


<style>
    .rightbar {
        float: left;
    }

    h4 {
        color: #555;
		margin: 10px auto;
		text-align: left;
    }

    .list-group {
        max-width: 300px;
        margin: 20px auto;
    }
</style>

