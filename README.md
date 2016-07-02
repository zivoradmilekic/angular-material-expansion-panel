# angular-material-expansion-panel

A module that implements design elements based on [Material Design](https://material.google.com) [Expansion Panels](https://material.google.com/components/expansion-panels.html). With additional features that are similar to Google Inbox style Expansion Panels.

To see Material Design Expansion Panels Specification go [here](https://material.google.com/components/expansion-panels.html).


This module is **In Progress** currently and should not be used in production. You can expect a tested and documented version in the near future.


<div style="border: 1px solid #ccc">
  <img src="https://cloud.githubusercontent.com/assets/11681147/16354667/4d9afefe-3a61-11e6-91a6-8f5addc40d0c.gif" alt="Angular Material docs website" style="display:block;">
</div>
<br />


Quick Links:
* [Installation](#installaton)
* [Building](#building)
* [Run Tests](#test)
* [Usage](#usage)
* [Documentation](#documentation)



## <a name="installation"></a> Installation

#### Bower

Change to your project's root directory.

```bash
# To install latest
bower install angular-material-expansion-panel

# To install latest and update bower.json
bower install angular-material-expansion-panel --save
```


#### Npm

Change to your project's root directory.

```bash
# To install latest
npm install angular-material-expansion-panel

# To install latest and update package.json
npm install angular-material-expansion-panel --save
```


#### setup

install modules

```bash
# install npm modules
npm install

# install bower components
bower install
```

Include the `material.components.expansionPanels` module as a dependency in your application.

```javascript
angular.module('myApp', ['ngMaterial', 'material.components.expansionPanels']);
```




## <a name="building"></a> Building

You can easily build using gulp.

The built files will be created in the `dist` folder

Run the **gulp** tasks:

```bash
# To run locally. This will kick of the watch process
# navigate to `localhost:8080`
gulp

# To build the js and css files to the `/build` directory
gulp build
```


## <a name="tests"></a> Run Tests

Test using Karma
Run the **gulp** tasks:

```bash
gulp test
```




## <a name="usage"></a> Usage

**Example Template**

```html
<md-expansion-panel>

  <md-expansion-panel-collapsed>
    <div class="md-title">Title</div>
    <div class="md-summary">Summary</div>
  </md-expansion-panel-collapsed>


  <md-expansion-panel-expanded>

    <md-expansion-panel-header>
      <div class="md-title">Expanded Title</div>
      <div class="md-summary">Expanded Summary</div>
    </md-expansion-panel-header>

    <md-expansion-panel-content>
      <h4>Content</h4>
      <p>Put content in here</p>
    </md-expansion-panel-content>

    <md-expansion-panel-footer>
      <div flex></div>
      <md-button class="md-warn" ng-click="$panel.collapse()">Collapse</md-button>
    </md-expansion-panel-footer>

  </md-expansion-panel-expanded>

</md-expansion-panel>
```




## <a name="documentation"></a> Documentation

To add Expansion Panels to you angular-material project, include the `material.components.expansionPanels` module as a dependency in your application.

```javascript
angular.module('myApp', ['ngMaterial', 'material.components.expansionPanels']);
```

* [mdExpansionPanelGroup](#mdExpansionPanelGroup)
* [mdExpansionPanel](#mdExpansionPanel)
* [mdExpansionPanelCollapsed](#mdExpansionPanelCollapsed)
* [mdExpansionPanelExpanded](#mdExpansionPanelExpanded)
* [mdExpansionPanelHeader](#mdExpansionPanelHeader)
* [mdExpansionPanelFooter](#mdExpansionPanelFooter)
* [$mdExpansionPanel](#$mdExpansionPanel)
* [$mdExpansionPanelGroup](#$mdExpansionPanelGroup)


#### Directives



## mdExpansionPanelGroup

`mdExpansionPanelGroup` is a container to manage multiple panels

```
<md-expansion-panel-group
  [md-component-id=""]
  [auto-expand=""]
  [multiple=""]>
...
</md-expansion-panel-group>
```

#### Attributes

| Param | Type | Details |
| :--: | :--: | :--: |
| md-component-id | string= | <p>add an id if you want to acces the panel via the <code>$mdExpansionPanelGroup</code> service</p>  |
| auto-expand | string= | <p>panels expand when added to <code><md-expansion-panel-group></code></p>  |
| multiple | string= | <p>allows for more than one panel to be expanded at a time</p>  |


## mdExpansionPanel

`mdExpansionPanel` is the main container for panels

```
<md-expansion-panel
  [md-component-id=""]>
...
</md-expansion-panel>
```

#### Attributes

| Param | Type | Details |
| :--: | :--: | :--: |
| md-component-id | string= | <p>add an id if you want to acces the panel via the <code>$mdExpansionPanel</code> service</p>  |



## mdExpansionPanelCollapsed

`mdExpansionPanelCollapsed` is used to contain content when the panel is collapsed

```
<md-expansion-panel-collapsed>
...
</md-expansion-panel>
```




## mdExpansionPanelExpanded

`mdExpansionPanelExpanded` is used to contain content when the panel is expanded

```
<md-expansion-panel-expanded
  [height=""]>
...
</md-expansion-panel-expanded>
```xpansion-panel>
```

#### Attributes

| Param | Type | Details |
| :--: | :--: | :--: |
| height | number= | <p>add this attribute set the max height of the expanded content. The container will be set to scroll</p>  |




## mdExpansionPanelHeader

`mdExpansionPanelHeader` is nested inside of `mdExpansionPanelExpanded` and contains content you want in place of the collapsed content
this is optional

```
<md-expansion-panel-header
  [md-no-sticky=""]>
...
</md-expansion-panel-header>
```

#### Attributes

| Param | Type | Details |
| :--: | :--: | :--: |
| md-no-sticky | boolean= | <p>add this aatribute to disable sticky</p>  |



## mdExpansionPanelFooter

`mdExpansionPanelFooter` is nested inside of `mdExpansionPanelExpanded` and contains content you want at the bottom.
By default the Footer will stick to the bottom of the page if the panel expands past
this is optional

```
<md-expansion-panel-footer
  [md-no-sticky=""]>
...
</md-expansion-panel-footer>
```

#### Attributes

| Param | Type | Details |
| :--: | :--: | :--: |
| md-no-sticky | boolean= | <p>add this aatribute to disable sticky</p>  |





### Services

## $mdExpansionPanel

Expand and collapse Expansion Panel using its `md-component-id`

```javascript
$mdExpansionPanel('theComponentId').then(function (instance) {
  instance.expand();
  instance.contract();
  instance.remove();
});
```

#### Methods

### $mdExpansionPanel

Get an instance of the expansion panel by its component id

**Parameters**

| Param | Type | Details |
| :--: | :--: | :--: |
| componentId | string | <p>the component id used on the element</p>  |

**Returns**

| Param | Details |
| :--: | :--: |
| promise | <p>a promise that will resolve with the panel instance</p>  |


### $mdExpansionPanel#expand

Exapnd Panel

**Returns**

| Param | Details |
| :--: | :--: |
| promise | <p>a promise that will resolve when panel is done animating</p>  |


### $mdExpansionPanel#collapse

Collapse Panle

**Returns**

| Param | Details |
| :--: | :--: |
| promise | <p>a promise that will resolve when panel is done animating</p>  |


### $mdExpansionPanel#remove

Remove panel from document

**Parameters**

| Param | Type | Details |
| :--: | :--: | :--: |
| noAnimation | boolean= | <p>remove without closeing animation</p>  |

**Returns**

| Type | Details |
| :--: | :--: |
| promise | <p>a promise that will resolve when panel is done animating</p>  |






## $mdExpansionPanelGroup

Control expansion panels and allow for adding and registering panels from code

```javascript
$mdExpansionPanelGroup('theComponentId').then(function (instance) {
  instance.register('name', {
    templateUrl: 'template.html',
    controller: 'Controller'
  });

  instance.add({
    templateUrl: 'template.html',
    controller: 'Controller'
  }).then(function (panelCtrl) {
    panelCtrl.expand();
  });

  instance.add('name', {locals: 'data'});
  instance.remove('name');
  instance.removeAll();
});
```



#### Methods

### $mdExpansionPanelGroup

Get an instance of the expansion panel group by its component id

**Parameters**

| Param | Type | Details |
| :--: | :--: | :--: |
| componentId | string | <p>the component id used on the element</p>  |

**Returns**

| Param | Details |
| :--: | :--: |
| promise | <p>a promise that will resolve with the panel group instance</p>  |


### $mdExpansionPanelGroup#register

register panel that can be added by the given name

**Parameters**

| Param | Type | Details |
| :--: | :--: | :--: |
| name | string | <p>the name you can use to add the template</p>  |
| options.template | string= | <p>template string</p>  |
| options.templateUrl | string= | <p>template url</p>  |
| options.controller | string= | <p>controller string or function</p>  |
| options.controllerAs | string= | <p>controller as name</p>  |
| options.locals | object= | <p>locals for injection</p>  |


### $mdExpansionPanelGroup#add

add a panel by either passing in a registered name or object. You can also pass in locals

**Parameters**

| Param | Type | Details |
| :--: | :--: | :--: |
| options | string|object | <p>registered panel name or object with details</p>  |
| locals | object= | <p>object of locals to inject intp controller</p>  |

**Options Object**

| Param | Type | Details |
| :--: | :--: | :--: |
| options.template | string= | <p>template string</p>  |
| options.templateUrl | string= | <p>template url</p>  |
| options.controller | string= | <p>controller string or function</p>  |
| options.controllerAs | string= | <p>controller as name</p>  |
| options.locals | object= | <p>locals for injection</p>  |

**Returns**

| Param | Details |
| :--: | :--: |
| promise | <p>a promise that will return the panel instance</p>  |


### $mdExpansionPanelGroup#remove

Remove a panel form the group

**Parameters**

| Param | Type | Details |
| :--: | :--: | :--: |
| componentId | string | <p>component id on panel</p>  |

**Returns**

| Type | Details |
| :--: | :--: |
| promise | <p>a promise that will resolve when panel is done animating</p>  |


### $mdExpansionPanelGroup#removeAll

Remove all panels form the group
