# Angular 5

## what are components?
Components are the fundamental building blocks of Angular applications. They display data on the screen, listen for user input, and take action based on that input.

## Angular components
The page you see is the application shell. The shell is controlled by an Angular component named AppComponent.

Components are the fundamental building blocks of Angular applications. They display data on the screen, listen for user input, and take action based on that input.

```typescript
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'app-users',
  templateUrl: './users.component.html',
  styleUrls: ['./users.component.css']
})
export class UsersComponent implements OnInit {

  constructor() { }

  ngOnInit() {
  }

}
```
You always import the `Component` symbol from the Angular core library.

`@Component` is a decorator function that specifies the Angular metadata for the component.

**Note: ** The CLI generated three metadata properties:

selector— the component's CSS element selector
templateUrl— the location of the component's template file.
styleUrls— the location of the component's private CSS styles.



## What ng serve does?
The ng serve command builds the app, starts the development server, watches the source files, and rebuilds the app as you make changes to those files.

The --open flag opens a browser to http://localhost:4200/.

## Install nginx
sudo add-apt-repository ppa:nginx/stable
sudo apt-get update
sudo apt-get install nginx
pwd
sudo vim /etc/nginx/sites-available/default
sudo nginx -t
sudo service nginx restart

## setting up angular app with nginx
sudo add-apt-repository ppa:nginx/stable
sudo apt-get update
sudo apt-get install nginx
pwd up to dist
sudo vim /etc/nginx/sites-available/default and change root property to your dist folder
sudo nginx -t
sudo service nginx restart

## Start array from index 1 in angular 5
<ion-slide *ngFor="let img of images.imageUrl | slice:1 or <any index you want to start array from> ">
	
	
## How to use CryptoJS with Angular 4?

Install using NPM and import below statement in you component file.

npm install crypto-js

import * as crypto from 'crypto-js';
now you can use crypto in your component file.

## **Error: npm ERR! write after end** while installing angular-cli?

Try downgrading your npm version this happens a lot with ionic.

npm install -g npm@5.6.0
If this doesn't work I advise you to switch to yarn. It's faster & easier to use. This is the link to download YARN. After installing just run this command  yarn global add 
cordova ionic

Ionic CLI uses npm by default. So go to your project & run $ yarn install.

If you want Ionic to use yarn by default run this: $ ionic config set -g yarn true