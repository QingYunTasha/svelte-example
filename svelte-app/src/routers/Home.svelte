<script>
	import axios from 'axios';
	let src="images/headshot.jpg";

	import { onMount } from 'svelte';
	export let stories = [];
    onMount(async () => {
		const res = await axios.get("http://localhost:8080/story/");
		stories = await res.data["context"];
	});

</script>

<main>
	<div class="row">
		<div class="leftcolumn">
			<div class="app">ð¾ð¾ð¾ð¾ð¾ð¾ð¾ð¾ð¾ð¾ð¾ð¾ð¾ð¾ð¾ð¾ð¾</div>
		</div>
		<div class="rightcolumn">
			<div class="card">
				<img {src} class="img" height="150px" width="auto" alt="error" />
				<h2>Zelinð¾</h2>
				<p>æè¬ä¼äºº</p>
			</div>
			<div class="card">
				<h3>popular articles</h3>
				<div><p>article</p></div>
				<div><p>article</p></div>
				<div><p>article</p></div>
			</div>
			<div class="card">
				<h3>Follow me</h3>
				<a href='https://github.com/QingYunTasha'>github</a><br>
				<a href='https://www.instagram.com/jimmyjenny0801/'>instagram</a><br>
				<a href='https://www.linkedin.com/in/zelin-huang-07aa4722a/'>linkedin</a><br>
				<a href='https://leetcode.com/rivendinner/'>leetcode</a>
			</div>
		</div>
		<div class="header">
			<h1>Zelin Design</h1>
			<p>ç±ææçæ ç±ææçæ è¥é¢æ¼æè ç¡æäº¦ç¡æ</p>
		</div>
		<div class="topnav">
			<a href="/backend">backend</a>
		</div>
		<div class="midcolumn">
			{#each stories as story}
			<div class="card">
				<h2>{story["Title"]}</h2>
				<h3>{story["Context"]}</h3>
				<p>{story["Label"]}</p>
				<h5>{story["Author"]}</h5>
			</div>
			{:else}
			<div class="card">
				<h2>æç« æ é¢</h2>
				<h5>2019 å¹´ 4 æ 17æ¥</h5>
				<div class="fakeimg" style="height:200px;">å¾ç</div>
				<p>ä¸äºææ¬...</p>
				<p>èé¸æç¨ - å­¦çä¸ä»æ¯ææ¯ï¼æ´æ¯æ¢¦æ³ï¼èé¸æç¨ - å­¦çä¸ä»æ¯ææ¯ï¼æ´æ¯æ¢¦æ³ï¼èé¸æç¨ - å­¦çä¸ä»æ¯ææ¯ï¼æ´æ¯æ¢¦æ³ï¼èé¸æç¨ - å­¦çä¸ä»æ¯ææ¯ï¼æ´æ¯æ¢¦æ³ï¼</p>
			</div>
			{/each}
		</div>
	</div>
</main>

<style>
	* {
	  box-sizing: border-box;
	}
	 
	.app {
		line-height: 180%;
		font-size: 38px;
	}

	/* å¤´é¨æ é¢ */
	.header {
	  padding: 8px;
	  text-align: center;
	  color: #9966FF;
	  background: white;
	}
	 
	.header h1 {
	  font-size: 45px;
	}
	 
	/* å¯¼èªæ¡ */
	.topnav {
	  overflow: hidden;
	  background-color: rgb(101, 149, 238);
	}
	 
	/* å¯¼èªæ¡é¾æ¥ */
	.topnav a {
	  float: left;
	  display: block;
	  color: #f2f2f2;
	  padding: 1px 16px;
	  text-decoration: none;
	}
	 
	/* é¾æ¥é¢è²ä¿®æ¹ */
	.topnav a:hover {
	  background-color: #aaa;
	  color: rgb(160, 26, 154);
	}
	 
	/* åå»ºä¸¤å */
	/* Left column */
	.leftcolumn {
		float: left;
		height: 100vh;
		padding-left: 10px;
		padding-right: 50px;
		width: 3%;
	}
	.midcolumn {   
	  float: left;
	  width: 72%;
	  overflow: scroll;
	}
	 
	/* å³ä¾§æ  */
	.rightcolumn {
	  float: right;
	  width: 23%;
	  background-color: #f1f1f1;
	  padding-left: 20px;
	}
	 
	/* å¾åé¨å */
	.fakeimg {
	  background-color: #aaa;
	  width: 100%;
	  padding: 20px;
	}
	 
	/* æç« å¡çææ */
	.card {
	  background-color: white;
	  padding: 20px;
	  margin-top: 20px;
	}
	 
	/* ååé¢æ¸é¤æµ®å¨ */
	.row:after {
	  content: "";
	  display: table;
	  clear: both;
	}
	 
	/* ååºå¼å¸å± - å±å¹å°ºå¯¸å°äº 800px æ¶ï¼ä¸¤åå¸å±æ¹ä¸ºä¸ä¸å¸å± */
	@media screen and (max-width: 800px) {
	  .midcolumn, .rightcolumn {   
		width: 100%;
		padding: 0;
	  }
	}
	 
	/* ååºå¼å¸å± -å±å¹å°ºå¯¸å°äº 400px æ¶ï¼å¯¼èªç­å¸å±æ¹ä¸ºä¸ä¸å¸å± */
	@media screen and (max-width: 400px) {
	  .topnav a {
		float: none;
		width: 100%;
	  }
	}
</style>
