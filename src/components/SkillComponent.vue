<template>
	<b-container id="skill-component">
		<!-- Skills Component-->
		<b-row id="skill-item">
			<b-col>
				<!-- Title -->
				{{name}}

				<!-- Info skills Button -->
				<button id="info-button" v-b-toggle="'collapse-' + info">
					<img src="@/assets/images/info.png">
				</button>
				<b-collapse :id="'collapse-' + info" class="mt-2">
					<p id="skill-desc" >{{ desc }}</p>
				</b-collapse>

				<!-- Progress bar Skill -->
				<progress max="100" :value="progress"/>
			</b-col>
		</b-row>
	</b-container>
</template>

<script>
export default {
	name: 'SkillComponent',
	props: {
		name: String,
		progress: Number,
		info: Number,
		desc: String,
	}
}
</script>

<style lang="scss">
#skill-component {
	padding:0;
}

#skill-item {
  margin-bottom: 10px;
}

#info-button {
  background: black;
  margin-bottom: 5px;
  border: 0;
}

#info-button img{
	vertical-align: middle;
}

#skill-desc{
	font-style: italic;
	font-size: small;
	text-align: start;
}

progress {
  border: 1px solid white;
  padding: 2px;
  width: 100%;
  height: 20px;
}

progress::-webkit-progress-value {
  background: repeating-linear-gradient(90deg, 
	#16D30D, 
	#16D30D 12px, 
	#000000 12px, 
	#000000 13.6px,
  );
}

progress::-webkit-progress-bar {
  background: repeating-linear-gradient(90deg, 
	#475841, 
	#475841 12px, 
	#000000 12px, 
	#000000 13.6px,
  );
}
</style>
