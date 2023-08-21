<script lang="ts">
	import * as Select from '$lib/components/ui/select';

	const fruits = [
		{ value: 'apple', label: 'Apple' },
		{ value: 'banana', label: 'Banana' },
		{ value: 'blueberry', label: 'Blueberry' },
		{ value: 'grapes', label: 'Grapes' },
		{ value: 'pineapple', label: 'Pineapple' }
	];
</script>

<div class="p-4">
	<h1 class="text-lg font-medium">Select Open Bug Repro</h1>
	<p>
		Focus on the "First Name" input text field then press Enter, you'll notice the select dropdown
		will open.
	</p>
	<form class="mt-8 space-y-6">
		<input required type="text" name="firstName" placeholder="First Name" class="border" />
		<Select.Root>
			<Select.Trigger class="w-[180px]">
				<Select.Value placeholder="Select a fruit" />
			</Select.Trigger>
			<Select.Content>
				<Select.Group>
					<Select.Label>Fruits</Select.Label>
					{#each fruits as fruit}
						<Select.Item value={fruit.value} label={fruit.label}>{fruit.label}</Select.Item>
					{/each}
				</Select.Group>
			</Select.Content>
			<Select.Input name="favoriteFruit" />
		</Select.Root>
		<button>Submit</button>
	</form>
</div>
