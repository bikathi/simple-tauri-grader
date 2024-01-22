<script setup lang="ts">
	import { ref, onMounted } from "vue";
	// import { invoke } from "@tauri-apps/api/tauri";

	function handleFormSubmit(): void {
		console.log("form submitted");
	}

	const subjectOne = ref("");
	const subjectTwo = ref("");
	const subjectThree = ref("");
	const subjectFour = ref("");
	const subjectFive = ref("");

	onMounted(() => {
		document.onkeydown = function (e) {
			if (e.key === "s" && (e.ctrlKey || e.metaKey)) {
				e.preventDefault(); // present "Save Page" from getting triggered.

				console.log("ctrl + s cliecked");
			}
		};
	});
</script>

<template>
	<div class="flex justify-center flex-col items-center">
		<h1 class="text-center text-4xl font-bold py-2">Tauri GUI Grader</h1>
		<form
			class="flex flex-col w-1/2 p-2 rounded-md"
			@submit.prevent="handleFormSubmit">
			<div class="flex flex-col">
				<label
					for="subject-one"
					class="input-labels"
					>Subject 1</label
				>
				<input
					type="text"
					id="subject-one"
					class="input-styles"
					v-model="subjectOne" />
			</div>
			<div class="flex flex-col mt-3">
				<label
					for="subject-two"
					class="input-labels"
					>Subject 2</label
				>
				<input
					type="text"
					id="subject-two"
					class="input-styles"
					v-model="subjectTwo" />
			</div>
			<div class="flex flex-col mt-3">
				<label
					for="subject-three"
					class="input-labels"
					>Subject 3</label
				>
				<input
					type="text"
					id="subject-three"
					class="input-styles"
					v-model="subjectThree" />
			</div>
			<div class="flex flex-col mt-3">
				<label
					for="subject-four"
					class="input-labels"
					>Subject 4</label
				>
				<input
					type="text"
					id="subject-four"
					class="input-styles"
					v-model="subjectFour" />
			</div>
			<div class="flex flex-col mt-3">
				<label
					for="subject-five"
					class="input-labels"
					>Subject 5</label
				>
				<input
					type="text"
					id="subject-five"
					class="input-styles"
					v-model="subjectFive" />
			</div>
			<div class="mt-3">
				<button
					type="submit"
					class="form-submit">
					Submit
				</button>
			</div>
		</form>
	</div>
</template>
