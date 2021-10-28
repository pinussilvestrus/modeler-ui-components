<style>

  .modeler-header {
    position: relative;
    flex-basis: 36px;
    background: var(--color-grey-225-10-85);
    border-bottom: 1px solid var(--color-grey-225-10-75);
  }

  .app-buttons {
    position: absolute;
    top: 6px;
    left: 6px;
  }

  .app-btn {
    position: absolute;
    top: 5px;
    width: 13px;
    height: 13px;
    border-radius: 50%;
  }

  .app-btn-close {
    left: 8px;
    background-color: rgb(255,95,87);
    border: 1px solid rgba(0,0,0,.25);
  }

  .app-btn-min {
    left: 28px;
    background-color: rgb(255,189,46);
    border: 1px solid rgba(0,0,0,.35);
  }

  .app-btn-full {
    left: 48px;
    background-color: rgb(40,201,64);
    border: 1px solid rgba(0,0,0,.25);
  }

  .app-title {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    font-weight: 600;
  }
</style>

<div class="modeler-header">
  <div class="app-buttons">
    <div class="app-btn app-btn-min"></div>
    <div class="app-btn app-btn-full"></div>
    <div class="app-btn app-btn-close"></div>
  </div>
  <div class="app-title">
    Camunda Modeler
  </div>
</div>