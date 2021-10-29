<script>
  const noop = () => {};

  export let hidden = true;
  export let onDeploy = noop;
</script>


{#if !hidden}
  <div class="cm-overlay cm-overlay-content" style="top: 859px; left: 143px; transform: translate(0px, -100%);">
    <div class="cm-overlay-group">
      <h2>Deployment</h2>
      <div class="cm-form-element">
        <label for="name">Deployment name</label>
        <input type="text" id="" name="name" value="diagram">
      </div>
      <div class="cm-form-element">
        <label for="name">Cluster URL</label>
        <input type="text" id="clusterUrl" value="xxxxxx.bru-2.zeebe.camunda.io:443">
      </div>
      <div class="cm-form-element">
        <label for="name">Client ID</label>
        <input type="text" id="clientId" name="clientId" value="v9G1La3nGRYayEFdfsdf66cxfeUrA4WZOaLI">
      </div>
      <div class="cm-form-element warning">
        <label for="name">Client secret</label>
        <input type="password" id="clientSecret" name="clientSecret" value="">
        <p class="cm-description">Client secret must not be empty.</p>
      </div>
      <button class="cm-btn cm-btn-primary" id="deploy" on:click="{ onDeploy }">Deploy</button>
    </div>
  </div>
{/if}