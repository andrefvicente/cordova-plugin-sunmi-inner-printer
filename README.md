# cordova-plugin-sunmi-inner-printer
Cordova/Ionic Plugin for Sunmi V2 Printer that works with cordova and ionic. It doesn't have a native ionic wrapper yet. I will probably implement it in the near future. 

Still needs some thorough testing but I was able to compile, today, and the printer is working.


Example of usage in an angular component (I still need to document the rest of the possible functions, but you can take a look in the innerprinter.js:

```
import {Component} from '@angular/core';


declare var sunmiInnerPrinter: any;

@Component({
	selector: 'app-home',
	templateUrl: 'home.page.html',
	styleUrls: ['home.page.scss'],
})
export class HomePage {

	constructor() {
	}

	print() {

		const printer = new sunmiInnerPrinter();

		printer.printString(
			'This is some nice toast popup!',
			(msg) => {
				console.log(msg);
			},
			(err) => {
				console.log(err);
			}
		);

	}
}

```


Tested with:

```
Ionic:

   Ionic CLI                     : 5.2.6
   Ionic Framework               : @ionic/angular 4.9.0
   @angular-devkit/build-angular : 0.801.3
   @angular-devkit/schematics    : 8.1.3
   @angular/cli                  : 8.1.3
   @ionic/angular-toolkit        : 2.0.0

Cordova:

   Cordova CLI       : 8.1.2 (cordova-lib@8.1.1)
   Cordova Platforms : android 8.0.0

Utility:

   cordova-res : not installed
   native-run  : 0.2.6

System:

   Android SDK Tools : 26.1.1 
   NodeJS            : v10.16.3
   npm               : 6.11.3
   OS                : Windows 10

```

*Project Package.json* ( So you can see exactly what I am using in projects that are using this plugin)
```
	"dependencies": {
		"@angular/common": "~8.1.2",
		"@angular/compiler": "~8.1.2",
		"@angular/core": "^8.1.2",
		"@angular/forms": "~8.1.2",
		"@angular/platform-browser": "~8.1.2",
		"@angular/platform-browser-dynamic": "~8.1.2",
		"@angular/router": "~8.1.2",
		"@ionic-native/core": "^5.0.0",
		"@ionic-native/splash-screen": "^5.0.0",
		"@ionic-native/status-bar": "^5.0.0",
		"@ionic/angular": "^4.7.1",
		"cordova-android": "^8.0.0",
		"cordova-android-support-gradle-release": "^3.0.1",
		"cordova-plugin-device": "^2.0.2",
		"cordova-plugin-ionic-keyboard": "^2.2.0",
		"cordova-plugin-ionic-webview": "^4.1.1",
		"cordova-plugin-splashscreen": "^5.0.2",
		"cordova-plugin-statusbar": "^2.4.2",
		"cordova-plugin-sunmi-inner-printer-v2": "git+https://github.com/martinlombana/cordova-plugin-sunmi-inner-printer-v2.git",
		"cordova-plugin-whitelist": "^1.3.3",
		"core-js": "^2.5.4",
		"npm": "^6.11.3",
		"rxjs": "~6.5.1",
		"tslib": "^1.9.0",
		"zone.js": "~0.9.1"
	},
	"devDependencies": {
		"@angular-devkit/architect": "~0.801.2",
		"@angular-devkit/build-angular": "~0.801.2",
		"@angular-devkit/core": "~8.1.2",
		"@angular-devkit/schematics": "~8.1.2",
		"@angular/cli": "~8.1.2",
		"@angular/compiler": "~8.1.2",
		"@angular/compiler-cli": "~8.1.2",
		"@angular/language-service": "~8.1.2",
		"@ionic/angular-toolkit": "~2.0.0",
		"@types/jasmine": "~3.3.8",
		"@types/jasminewd2": "~2.0.3",
		"@types/node": "~8.9.4",
		"codelyzer": "^5.0.0",
		"jasmine-core": "~3.4.0",
		"jasmine-spec-reporter": "~4.2.1",
		"karma": "~4.1.0",
		"karma-chrome-launcher": "~2.2.0",
		"karma-coverage-istanbul-reporter": "~2.0.1",
		"karma-jasmine": "~2.0.1",
		"karma-jasmine-html-reporter": "^1.4.0",
		"protractor": "~5.4.0",
		"ts-node": "~7.0.0",
		"tslint": "~5.15.0",
		"typescript": "~3.4.3"
	},
	"description": "An Ionic project",
	"cordova": {
		"plugins": {
			"cordova-plugin-whitelist": {},
			"cordova-plugin-statusbar": {},
			"cordova-plugin-device": {},
			"cordova-plugin-splashscreen": {},
			"cordova-plugin-ionic-webview": {
				"ANDROID_SUPPORT_ANNOTATIONS_VERSION": "27.+"
			},
			"cordova-plugin-ionic-keyboard": {},
			"cordova-android-support-gradle-release": {
				"ANDROID_SUPPORT_VERSION": "27.+"
			},
			"cordova-plugin-sunmi-inner-printer-v2": {}
		},
		"platforms": [
			"android"
		]
	}
```


```

java version "1.8.0_221"
Java(TM) SE Runtime Environment (build 1.8.0_221-b11)
Java HotSpot(TM) 64-Bit Server VM (build 25.221-b11, mixed mode)

------------------------------------------------------------
Gradle 4.10.3
------------------------------------------------------------

Build time:   2018-12-05 00:50:54 UTC
Revision:     e76905e3a1034e6f724566aeb985621347ff43bc

Kotlin DSL:   1.0-rc-6
Kotlin:       1.2.61
Groovy:       2.4.15
Ant:          Apache Ant(TM) version 1.9.11 compiled on March 23 2018
JVM:          1.8.0_221 (Oracle Corporation 25.221-b11)
OS:           Windows 10 10.0 amd64
```

This plugin is based on other repos (as you can see I forked from them), but none of them where working propertly due to several factors (not up to date libraries, deprecated functions, incoherent package names, different names between the plugin and the repository, etc). 

Any issue is welcome and any collaboration as well. I haven't tested all the functions yet. This is an updated repository, with latest files from sunmi, ported as a cordova plugin.
