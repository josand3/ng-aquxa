--- 
title: Right-to-left support
category: general
noApi: true



---
# Overview
All components in our Component Library have built-in support for right-to-left (RTL) locales.

There are 2 requirements for the component to display and behave properly in RTL environment:

1. Your app should import `BidiModule` from [Angular CDK](https://material.angular.io/cdk/bidi/overview) in the `app.module.ts`:

    ```ts
    // ...
    import { BidiModule } from '@angular/cdk/bidi';

    @NgModule({
        imports: [
            // ...
            BidiModule,
        ],
        // ...
    })
    export class AppModule {}
    ```

1. Any of the parent containers of the component needs to have `dir` HTML attribute set to `rtl`. For most cases a good place to add `dir` attribute is on the `app.component.ts/.html` level.
    <!-- HINT: for some reason there's no space between end of the list and an example, so have to go with linebreak -->
    <br>

<!-- example(rtl-basic) -->
