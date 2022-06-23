# Winggy Angular

This package is mainly used for the following Common Contents:

- [**Installing winggy-angular Package**](<#installing-winggy-angular>)
- [**Integration of Common Modules**](<#integration-of-common-modules>)
- [**Integration of Common Translator Modules**](<#integration-of-common-translator-modules>)
- [**Integration of Common Services**](<#integration-of-common-services>)
- [**Integration of Common Components**](<#integration-of-common-components>)
- [**Integration of Common Styles**](<#integration-of-common-styles>)

## Installing winggy-angular
```
  npm install winggy-angular --save
```

## Integration of Common Modules

* Using of Common Modules, import the below lines in the *.module.ts

``` ts
  import { WinggyCommonModule } from 'winggy-angular';

  imports: [
    ...
    WinggyCommonModule.forRoot(),
    ...
  ]
```
## Integration of Common Translator Modules

* Using of Common Translator Module, import the below lines in app.module.ts

``` ts
  import { WinggyTranslateModule } from 'winggy-angular';

  imports: [
    ...
    WinggyTranslateModule.forRoot(),
    ...
  ]
```

## Integration of Common Services

* Using of Common Services Import the below lines in the *.component.ts

``` ts
  import { WinggyCommonService } from 'winggy-angular';

  constructor(
    ...
    public commonService: WinggyCommonService
  ) {}
```

* To initiate the translator service and update the language for the translator service, follow the lines

``` ts
    constructor(
    ...
    public commonService: WinggyCommonService
  ) {
      this.commonService.initiateTranslator();
  }

  this.commonService.setLanguage('english');
```

## Integration of Common Components



## Integration of Common Styles

* Using of Common Styles Import the below lines in the style.scss

``` scss
  @import "node_modules/winggy-angular/assets/scss/common";
```

| Name | Description | Sample Classes |
| ---- | ----------- | -------------- |
| winggy-w-* | Width in percentage from 1% to 100% | winggy-w-10 |
| winggy-width-* | Width in vh from 1vh to 100vh | winggy-width-10 |
| winggy-h-* | Height in percentage from 1% to 100% | winggy-h-10 |
| winggy-height-* | Height in vh from 1vh to 100vh | winggy-height-10 |


#### Author: [Narenthiran Y](http://github.com/ynarenthiran)
#### License: MIT
