---
layout: archive
title: "COMMITTEE" 
permalink: /committee/
author_profile: true
---

{% include base_path %}

<style>
.i-list[data-v-662c1668] {
	width: 100%;
	display: flex;
	justify-content: space-between;
	margin-top: 20px
}

.l-img[data-v-662c1668] {
	width: 30%;
	margin-right: 20px
}

.img-bottom[data-v-662c1668] {
	background: #fff;
	width: 100%;
	overflow: hidden
}
</style>

Organizational Structure
---
The Committee on Automatic Driving and Simulation and Testing (CSF-ADST) is affiliated with the China Simulation Society and Tsinghua University, and its initiator, Wu Jianping, is a professor at the Department of Civil Engineering of Tsinghua University and the head of Alibaba's automatic driving simulation. CSF-ADST is composed of enterprise leaders and core experts and scholars covering the fields of autonomous driving, simulation and software testing. The Ad Hoc Committee is an authoritative organization in the field of automatic driving simulation and testing in China, and has played an active role in promoting the development of the industry. Aiming at the core challenges in the field of automatic driving and simulation testing, the committee carries out professional academic exchanges, scientific research cooperation, technology promotion and professional consulting work in the fields of automatic driving and simulation testing theory, education, scientific research and application, etc., which mainly include. 
> Organizing academic conferences, symposiums, competitions and other academic activities - Editing and publishing professional journals, books and media products - Providing professional and technical consulting, and undertaking professional tasks entrusted by the government - Evaluating and consulting on academic achievements, and promoting new theories, technologies, and methods - Organizing and carrying out international academic exchanges and training activities - Assisting and cooperating with the higher-level societies and departments in formulating relevant standards, norms and technical guidelines - Providing professional consultation on national policies in the field of autonomous driving and simulation testing Assisting in formulating relevant standards, norms and technical guidelines in cooperation with higher societies and departments - Playing an advisory role on national policies, development plans and major issues in relevant fields 
> Cooperate with and assist the higher societies in organizing and carrying out relevant program for members.

Methodology
---
As mentioned earlier, each route contians two roads and one junction. 

We define the following features to classify the junctions:

* has_traffic_light
* has_stop_sign
* has_incoming_crosswalk
* has_outgoing_crosswalk
* topology feature

The topolgy feature is denoted by the co nectivity of the connected roads and thus represents the direction of the traffic flow through the junction.

The following diagram visualizes some of the topology features extracted from the San Francisco map. It can be seen that the topology feature not only records the traffic flow information but also implies the shape (i.e. geometry) of the junction. 

![test_img](../images/tupian01.png)

We define the following features to model the driving behavior on roads:

* number_of_lane_changes_before_junction
* number_of_lane_changes_after_junction

The extracted road features are shown below:

![test_img](../images/tupian02.png)

We then define the route feature to be a combination of road features and junction features and classify routes extracted from the whole map into route groups. 

In each route group, all the route members are considered equivalent in and can be selected as a representative test case.

As a result, duplicated test cases can be elimitated by selecting only one route from each group, and the total number of test cases is significantly reduced while covering the same level of scenario diverisity. 

Below are some of the discovered issues of the open-source Apollo stack:

<div class="i-list" data-v-662c1668="">
	<div class="l-img" data-v-662c1668="">
    		<div class="img-bottom" data-v-662c1668="">
      			<img src="../images/TOPOdongtu01.GIF" alt="" data-v-662c1668="">
			<p><b>Failed to change lane</b></p>
    		</div>
  	</div>
  	<div class="l-img" data-v-662c1668="">
    		<div class="img-bottom" data-v-662c1668="">
      			<img src="../images/TOPOdongtu02.GIF" alt="" data-v-662c1668="">
			<p><b>Stuck at stop sign junction</b></p>
    		</div>
  	</div>
  	<div class="l-img" data-v-662c1668="">
    		<div class="img-bottom" data-v-662c1668="">
      			<img src="../images/TOPOdongtu03.GIF" alt="" data-v-662c1668="">
			<p><b>Produced inefficient routing</b></p>
    		</div>
  	</div>
</div>

Readers are referred to the following paper for more details.

Y. Tang et al., "Route Coverage Testing for Autonomous Vehicles via Map Modeling," 2021 IEEE International Conference on Robotics and Automation (ICRA), 2021, pp. 11450-11456, doi: 10.1109/ICRA48506.2021.9560890, [see details](https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9560890&isnumber=9560666).
