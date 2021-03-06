# modeler-ui-components

Reusable components and styles, for Camunda Modeler.

## Installation

```sh
git clone https://github.com/pinussilvestrus/modeler-ui-components.git
cd modeler-ui-components
npm install
```

## Build that project

```sh
npm run build
```

## Usage

Integrate the style sheet to your web application to add the basic styles, colors, and font definitions.

```js
import 'modeler-ui-components/dist/styles/modeler-ui.css';
```

All variables are available in your application.

```css
.modeler-header {
  position: relative;
  flex-basis: 36px;
  background: var(--color-grey-225-10-85);
  border-bottom: 1px solid var(--color-grey-225-10-75);
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
```

Use the defined class selectors to apply the styles, e.g., for form elements

```html
<div class="cm-form-element">
  <label for="name">Deployment name</label>
  <input type="text" id="" name="name" value="diagram">
</div>
```

![Form element](./docs/form-element.png)

or overlays

```html
<div class="cm-overlay cm-overlay-content">
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
      <input type="text" id="clientId" name="clientId" value="xxxxxxxxxxxx">
    </div>
    <div class="cm-form-element warning">
      <label for="name">Client secret</label>
      <input type="password" id="clientSecret" name="clientSecret" value="">
      <p class="cm-description">Client secret must not be empty.</p>
    </div>
    <button class="cm-btn cm-btn-primary" id="deploy">Deploy</button>
  </div>
</div>
```

![Overlay](./docs/overlay.png)

or notifications.

```html
<div class="cm-notification-container">
  <div class="cm-notification slidein">
    <button 
      class="cm-btn cm-btn-icon cm-btn-close" 
      title="Close notification">
        {@html NotificationCloseIcon }
    </button>
    <span>{@html NotificationSuccessIcon}</span> <h3>Deployment succeeded</h3>
  </div>
</div>
```

![Notification](./docs/notification.png)

To use the available icons, import them into your application. A bundler is likely needed to consume then.

```js
import CloudConnectConnectedIcon from 'modeler-ui-components/dist/icons/CloudConnectConnected.svg';
import DeployIcon from 'modeler-ui-components/dist/icons/Deploy.svg';
import FeedbackIcon from 'modeler-ui-components/dist/icons/Feedback.svg';
import RunIcon from 'modeler-ui-components/dist/icons/Run.svg';
```

Checkout the [example](./example) to get further information.

## License

MIT
