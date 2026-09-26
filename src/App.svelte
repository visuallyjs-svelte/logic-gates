<script>
    import {
        DiagramProvider, DiagramComponent,
		DiagramPaletteComponent, ExportControlsComponent,
        ControlsComponent
    } from "@visuallyjs/browser-ui-svelte"

    import Inspector from './Inspector.svelte'
    import diagramOptions from './diagram-options'
    import './logic-gates.css'


    let { url = "/dataset.json" } = $props();


</script>

<div class="vjs-lg-main">
    <DiagramProvider>
        <div class="vjs-palette-wrapper">
            <DiagramPaletteComponent showLabels={true}
                                     iconSize={{width:120,height:120}}
                                     allowDropOnEdge={true}
                                     autoEdgeConnect={{
                                       enabled:true,
                                       connectMode:"eager"
                                   }}/>
        </div>
        <DiagramComponent style="flex-grow:1" options={diagramOptions} {url}/>
        <div class="vjs-lg-controls">
			<ControlsComponent/>
			<ExportControlsComponent/>
			<Inspector/>
		</div>
    </DiagramProvider>
</div>

<style>
    :global(html, body) {
        margin:0;
        padding:0;
        width:100vw;
        height:100vh;
    }
</style>
