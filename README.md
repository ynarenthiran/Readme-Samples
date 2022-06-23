# Winggy Angular

This package is mainly used for the following Common Contents:

[**Demo**](<#demo>)
1. [**Installing winggy-angular Package**](<#installingwinggy-angular>)
2. [**Integration of Common Modules**](<#integrationofCommonModules>)
3. [**Integration of Common Translator Modules**](<#Integration of Common Translator Modules>)
4. [**Integration of Common Services**](<#Integration of Common Services>)
5. [**Integration of Common Components**](<#Integration of Common Components>)
6. [**Integration of Common Styles**](<#Integration of Common Styles>)

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

## Integration of Common Components

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

## Integration of Common Styles

* Using of Common Styles Import the below lines in the style.scss

``` scss
  @import "node_modules/winggy-angular/assets/scss/common";
```

## Demo

#### Author: [Narenthiran Y](http://github.com/ynarenthiran)
#### License: MIT
