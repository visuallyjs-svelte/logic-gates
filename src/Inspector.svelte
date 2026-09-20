<script lang="ts">
import { InspectorComponent } from "@visuallyjs/browser-ui-svelte"
import { isNode, type Base } from "@visuallyjs/browser-ui"

let current = $state<Base | null>(null)

</script>

<InspectorComponent bind:current={current}>
	{#if current != null && isNode(current)}
		<div class="vjs-inspector-pane">
			<div class="vjs-inspector-properties">
				<div class="vjs-inspector-field">
					<label>Label</label>
					<input type="text" vjs-att="label" placeholder="Label"/>
				</div>
			</div>
		</div>
	{/if}
</InspectorComponent>
