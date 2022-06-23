# Winggy Angular

This package is mainly used for the following Common Contents:

- [**Installing winggy-angular Package**](#installing-winggy-angular)
- [**Integration of Common Modules**](#integration-of-common-modules)
- [**Integration of Common Translator Modules**](#integration-of-common-translator-modules)
- [**Integration of Common Services**](#integration-of-common-services)
- [**Integration of Common Components**](#integration-of-common-components)
- [**Integration of Common Styles**](#integration-of-common-styles)

## Installing winggy-angular

```
  npm install winggy-angular --save
```

## Integration of Common Modules

- Using of Common Modules, import the below lines in the \*.module.ts

```ts
  import { WinggyCommonModule } from 'winggy-angular';

  imports: [
    ...
    WinggyCommonModule.forRoot(),
    ...
  ]
```

## Integration of Common Translator Modules

- Using of Common Translator Module, import the below lines in app.module.ts

```ts
  import { WinggyTranslateModule } from 'winggy-angular';

  imports: [
    ...
    WinggyTranslateModule.forRoot(),
    ...
  ]
```

## Integration of Common Services

- Using of Common Services Import the below lines in the \*.component.ts

```ts
  import { WinggyCommonService } from 'winggy-angular';

  constructor(
    ...
    public commonService: WinggyCommonService
  ) {}
```

- To initiate the translator service and update the language for the translator service, follow the lines

```ts
    constructor(
    ...
    public commonService: WinggyCommonService
  ) {
      this.commonService.initiateTranslator();
  }

  this.commonService.setLanguage('english');
```

## Integration of Common Components

- Using of Common Components Import the below lines in parent module of the component.

```ts
  import { WinggyTranslateModule } from 'winggy-angular';

  imports: [
    ...
    WinggyTranslateModule.forRoot(),
    ...
  ]
```

- Please follow the common components to integrate.

  - No data or Loader Component

    - HTML Template

    ```html
    <winggy-no-data [error]="error"></winggy-no-data>
    ```

    - Properties

      | Property Type | Property | Default Values | Parameters/Data Type |
      | ------------- | -------- | -------------- | -------------------- |
      | Input         | error    | No data found  | string               |

  - Breadcrumb Component

    - HTML Template

    ```html
    <winggy-breadcrumb [breadcrumbData]="breadcrumbData"></winggy-breadcrumb>
    ```

    - Properties

      | Property Type | Property       | Default Values | Parameters/Data Type           |
      | ------------- | -------------- | -------------- | ------------------------------ |
      | Input         | breadcrumbData | []             | [{name: string, path: string}] |

    - Sample Data Format

    ```ts
    breadcrumbData = [
      {
        name: "Home",
        path: null,
      },
      {
        name: "Menus",
        path: "/menu-management/menu-builder",
      },
      {
        name: "Menu Management",
        path: "/menu-management/menu-builder",
      },
      {
        name: "Edit Menus",
        path: null,
      },
    ];
    ```

  - Table Component

    - HTML Template

    ```html
    <winggy-table
      [columns]="columns"
      [data]="data"
      (tableChanges)="tableChanges($event)"
      (tableAction)="tableAction($event)"
    ></winggy-table>
    ```

    - Properties

      | Property Type | Property     | Default Values | Parameters/Data Type                                                                                                                                                                      | Description                                            |
      | ------------- | ------------ | -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------ |
      | Input         | columns      | []             | [{ header: string, field: string, type: string(value/input/select/radio/checkbox/action), hideAllSelect: boolean, options: Array, selectOptions: Object, actions: Array, style: Object }] | -                                                      |
      | Input         | data         | []             | [{}]                                                                                                                                                                                      | -                                                      |
      | Output        | tableChanges | -              | -                                                                                                                                                                                         | Every Input Changes will reflect in this Output Event  |
      | Output        | tableAction  | -              | -                                                                                                                                                                                         | Every Action Changes will reflect in this Output Event |

    - Sample Data Format

    ```ts
    columns = [
      {
        header: "",
        field: "expand",
        type: "tree",
      },
      {
        header: "",
        field: "multiSelection",
        type: "checkbox",
        hideAllSelect: false,
      },
      {
        header: "",
        field: "singleSelection",
        type: "radio",
      },
      {
        header: "Name",
        field: "name",
        type: "value",
        style: { width: "20%" },
      },
      {
        header: "Sample Input",
        field: "inputData",
        type: "input",
        style: { width: "20%" },
      },
      {
        header: "Course",
        field: "course",
        type: "select",
        style: { width: "20%" },
        options: [
          {
            label: "Select",
            value: "",
          },
          {
            label: "None",
            value: "None",
          },
          {
            label: "Drinks",
            value: "Drinks",
          },
          {
            label: "Appetizers",
            value: "Appetizers",
          },
          {
            label: "Entrees",
            value: "Entrees",
          },
          {
            label: "Deserts",
            value: "Deserts",
          },
        ],
        selectOptions: {
          label: "label",
          value: "value",
        },
      },
      {
        header: "Actions",
        field: "action",
        type: "action",
        style: { width: "20%" },
        actions: [
          {
            icon: "edit",
            title: "Edit",
            action: "edit",
          },
          {
            icon: "more_horiz",
            title: "Menu",
            contextMenu: [
              {
                name: "Archieve",
                action: "archieve",
              },
            ],
          },
        ],
      },
    ];

    data = [
      {
        name: "Food",
        inputData: "Food",
        course: "Drinks",
        prepStations: "No Print",
      },
      {
        name: "Drinks",
        course: "",
        prepStations: "",
      },
      {
        name: "Open Items",
        course: "",
        prepStations: "",
      },
    ];
    ```

## Integration of Common Styles

- Using of Common Styles Import the below lines in the style.scss

```scss
@import "node_modules/winggy-angular/assets/scss/common";
```

- Use the below template to start the new menu component

```html
<div class="winggy-page-layout">
  <div class="winggy-page-header">
    <!-- Breadcrumb Component -->
  </div>
  <div class="winggy-page-content">
    <div class="indo-menu-title">
      <h2>Menu Header</h2>
      <!-- Actions Div -->
    </div>
    <!-- Contents -->
  </div>
</div>
```

- Please follow the styles to integrate with the common styles.

| Class Name            | Description                                      | Sample Classes        |
| --------------------- | ------------------------------------------------ | --------------------- |
| winggy-w-\*           | Width in percentage from 1 to 100                | winggy-w-10           |
| winggy-width-\*       | Width in vh from 1 to 100                        | winggy-width-10       |
| winggy-min-width-\*   | Min Width in vh from 1 to 100                    | winggy-min-width-10   |
| winggy-max-width-\*   | Max Width in vh from 1 to 100                    | winggy-max-width-10   |
| winggy-h-\*           | Height in percentage from 1 to 100               | winggy-h-10           |
| winggy-height-\*      | Height in vh from 1 to 100                       | winggy-height-10      |
| winggy-min-height-\*  | Min Height in vh from 1 to 100                   | winggy-min-height-10  |
| winggy-max-height-\*  | Max Height in vh from 1 to 100                   | winggy-max-height-10  |
| winggy-p-\*           | Padding in vh from 1 to 100                      | winggy-p-10           |
| winggy-pt-\*          | Padding Top in vh from 1 to 100                  | winggy-pt-10          |
| winggy-pb-\*          | Padding Bottom in vh from 1 to 100               | winggy-pb-10          |
| winggy-pr-\*          | Padding Right in vh from 1 to 100                | winggy-pr-10          |
| winggy-pl-\*          | Padding Left in vh from 1 to 100                 | winggy-pl-10          |
| winggy-m-\*           | Margin in vh from 1 to 100                       | winggy-m-10           |
| winggy-mt-\*          | Margin Top in vh from 1 to 100                   | winggy-mt-10          |
| winggy-mb-\*          | Margin Bottom in vh from 1 to 100                | winggy-mb-10          |
| winggy-mr-\*          | Margin Right in vh from 1 to 100                 | winggy-mr-10          |
| winggy-ml-\*          | Margin Left in vh from 1 to 100                  | winggy-ml-10          |
| winggy-capitalize     | Text-transform is captialize                     | winggy-capitalize     |
| winggy-button         | Button Styles                                    | winggy-button         |
| winggy-rounded-button | Rounded Button Styles                            | winggy-rounded-button |
| winggy-cur-pointer    | This is used for cursor: pointer;                | winggy-cur-pointer    |
| winggy-d-flex         | This is used for display: flex;                  | winggy-d-flex         |
| winggy-fd-col         | This is used for flex-direction: column;         | winggy-fd-col         |
| winggy-fw-wrap        | This is used for flex-wrap: wrap;                | winggy-fw-wrap        |
| winggy-jc-c           | This is used for justify-content: center;        | winggy-jc-c           |
| winggy-jc-fe          | This is used for justify-content: flex-end;      | winggy-jc-fe          |
| winggy-jc-sa          | This is used for justify-content: space-around;  | winggy-jc-sa          |
| winggy-jc-sb          | This is used for justify-content: space-between; | winggy-jc-sb          |
| winggy-ai-c           | This is used for align-items: center;            | winggy-ai-c           |
| winggy-ai-fe          | This is used for align-items: flex-end           | winggy-ai-fe          |
| winggy-ai-sa          | This is used for align-items: space-around       | winggy-ai-sa          |
| winggy-ai-sb          | This is used for align-items: space-between      | winggy-ai-sb          |

#### Author: [Narenthiran Y](http://github.com/ynarenthiran)

#### License: MIT
