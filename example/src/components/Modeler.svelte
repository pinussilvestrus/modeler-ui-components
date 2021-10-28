<script>
  import { onMount } from 'svelte';

  import BpmnModeler from 'bpmn-js/lib/Modeler';

  import ZeebeModdleExtension from 'zeebe-bpmn-moddle/lib';
  import ZeebeModdle from 'zeebe-bpmn-moddle/resources/zeebe';

  import {
    BpmnPropertiesPanelModule,
    BpmnPropertiesProviderModule,
    ZeebePropertiesProviderModule
  } from '@bpmn-io/bpmn-properties-panel';

  import '@bpmn-io/bpmn-properties-panel/dist/assets/properties-panel.css';
  import 'bpmn-js/dist/assets/diagram-js.css';
  import 'bpmn-js/dist/assets/bpmn-font/css/bpmn-embedded.css';

  const noop = () => {};


  onMount(async () => {
    const modeler = new BpmnModeler({
      container: '.diagram-container',
      keyboard: { 
        bindTo: 
        document 
      },
      propertiesPanel: {
        parent: '.properties-container'
      },
      additionalModules: [
        ZeebeModdleExtension,
        BpmnPropertiesPanelModule,
        BpmnPropertiesProviderModule,
        ZeebePropertiesProviderModule
      ],
      moddleExtensions: {
        zeebe: ZeebeModdle
      }
    });

    const { error } = await modeler.importXML(xml);

    if (error) {
      console.error(error);
      return;
    }

    const canvas = modeler.get('canvas');

    canvas.zoom('fit-viewport');

    onDiagramLoaded(modeler);
  });

  export let xml = '';

  export let onDiagramLoaded = noop;
</script>

<style>
  #diagram {
    position: relative;
    flex-grow: 1;
    background: white;
    display: flex;
    height: 100%;
  }

  #diagram .diagram-container {
    flex: 1;
    position: relative;
    background: var(--color-white);
  }

  #diagram .properties-container {
    flex: none;
    width: 350px;
    height: 100%;
    border-left: 1px solid var(--color-grey-225-10-75);
    background: var(--color-white);
  }
</style>

<div id="diagram">
  <div class="diagram-container"></div>
  <div class="properties-container"></div>
</div>