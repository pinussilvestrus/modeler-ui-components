<script>
  import DeploymentOverlay from './DeploymentOverlay.svelte';

  import CloudConnectConnectedIcon from 'modeler-ui-components/dist/icons/CloudConnectConnected.svg';
  import DeployIcon from 'modeler-ui-components/dist/icons/Deploy.svg';
  import FeedbackIcon from 'modeler-ui-components/dist/icons/Feedback.svg';
  import RunIcon from 'modeler-ui-components/dist/icons/Run.svg';

  let hideDeployOverlay = true;
  const toggleDeployShow = () => {
    hideDeployOverlay = !hideDeployOverlay;
  }
  const deploy = () => {
    toggleDeployShow();

    // todo: show notification
  }
</script>

<style>
  #status-bar {
    display: flex;
    justify-content: space-between;
    align-items: stretch;
    position: relative;
    flex-basis: 32px;
    background: var(--color-grey-225-10-85);
    border-top: 1px solid var(--color-grey-225-10-75);
  }

  #status-bar .cm-btn {
    padding: 0 10px;
    border-radius: 0;
    white-space: nowrap;
    background-color: transparent;
  }

  #status-bar .cm-btn:hover {
    background-color: var(--color-grey-225-10-80);
  }

  #status-bar .cm-btn.active {
    background-color: var(--color-grey-225-10-75);
  }

  /* svelte quirk to enable styles for svgs */
  :global(#status-bar .cm-btn-icon svg) {
    margin-left: -3px;
    margin-top: 2px;
  }

  .file-scope,
  .app-scope {
    display: flex;
  }
</style>

<div id="status-bar">
  <div class="file-scope">
    <button class="cm-btn" title="Select execution platform and version">Camunda Cloud 1.2</button>
    <button class="cm-btn cm-btn-icon" class:active="{!hideDeployOverlay}" title="Deploy" on:click="{ toggleDeployShow }">
      {@html DeployIcon}
    </button>
    <button class="cm-btn cm-btn-icon" title="Start an process instance">
      {@html RunIcon}
    </button>
    <!-- <button class="cm-btn cm-btn-error" title="14 validation errors">14 errors</button> -->
  </div>
  <div class="app-scope">
    <button class="cm-btn cm-btn-icon" title="Camunda Cloud connection status">
      {@html CloudConnectConnectedIcon}
    </button>
    <button class="cm-btn cm-btn-icon" title="Feedback">
      {@html FeedbackIcon}
    </button>
    <button class="cm-btn" title="Toggle log view">Log</button>
    <button class="cm-btn" title="Version information">4.11.0</button>
  </div>
</div>

<DeploymentOverlay hidden={ hideDeployOverlay } onDeploy={ deploy } />