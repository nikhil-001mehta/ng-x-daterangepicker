# ng-x-daterangepicker

This module is strictly intended to work on browsers only and not in node/browserless environments

This is a work in progress and you are always welcome to help me going forward with this project.

### Installation

```bash
# NPM
npm install ng-x-daterangepicker
```
### Depends on 
[moment.js](http://momentjs.com/) version greater than 2.17.1<br/>
[moment-range.js](https://github.com/gf3/moment-range) version 2.2.0 <br/>

I will suggest you to install dependancy modules before this module

If you are using bootstrap.css then just include style code given below in your code <br/>

if you do not want to include whole bootstrap.css then include [this css](https://raw.githubusercontent.com/nikhil-001mehta/ng-x-daterangepicker/master/daterangepicker-component.css) in your code.

```html
<style>
	.daterangepicker {
		font-family: "Helvetica Neue",Helvetica,Arial,sans-serif !important;
		font-size: 14px;
	}
	.hidden {
		display: none;
		visibility: false;
	}
	@media (min-width: 450px) {
		.daterangepicker {
			z-index: 3000;
			border-radius: 4px;
			box-shadow: 0px 2px 2px 2px #888888;
			max-width: 450px;
			min-width: 450px;
		}
	}
	@media (max-width: 450px) {
		.daterangepicker {
			z-index: 3000;
			border-radius: 4px;
			box-shadow: 0px 2px 2px 2px #888888;
			max-width: 270px;
		}
		.text-center .pull-right {
			float: none !important;
		}
		.ranges{
			display: none;
		}
	}

	.daterangepicker .calendar {
		margin: 4px;
		float: left;
		border-radius: 4px !important;
	}
	.applyBtn{
		margin: 4px;
	}
	.daterangepicker  .flush {
		padding: 0 !important;
		margin: 0 !important;
	}
	.daterangepicker  .flush-bottom{
		padding-bottom: 0 !important;
	}
	.daterangepicker  .flush-left {
		padding-left: 0 !important;
	}
	.daterangepicker  .flush-right {
		padding-right: 0 !important;
	}
	.daterangepicker  .flush-half--left {
		padding-left: 4px !important;
	}
	.daterangepicker .flush-half--right {
		padding-right: 4px !important;
	}
	.daterangepicker .nudge-top {
		top: 5px;
	}
	.daterangepicker th {
		margin: 1px !important;
		padding: 1px !important;
		text-align: center;
		border-radius: 4px !important;
	}
	.daterangepicker td {
		font-size: 14px;
		height: 20px;
		width: 20px;
		text-align: center;
		padding: 2px !important;
		margin: 1px !important;
		border-radius: 4px !important;
		white-space: nowrap;
		text-align: center;
	}
	.daterangepicker .btn.btn-flat {
		border: none;
		background: transparent;
		margin: 3px !important;
		padding: 1px !important;
	}
	.daterangepicker .off {
		color: #A2A2A2;
	}
	.daterangepicker table {
	  border-spacing: 0;
	  border-collapse: collapse;
	}
	.daterangepicker td,
	.daterangepicker th {
	  padding: 0;
	}
	.daterangepicker .clickable{
		cursor: pointer;
	}
	.daterangepicker .clickable-link{
		color: #337ab7;
	}
	.daterangepicker .clickable.disabled{
		pointer-events: none;
		color: #A2A2A2;
	}
	.daterangepicker label{
		display: inline-block;
		max-width: 100%;
		margin-bottom: 5px;
		font-weight: bold;
	}
	.daterangepicker .btn-link {
		padding: 1px 6px 1px 6px !important;
	}
  </style>
```
### Demo
see [Demo](https://nikhil-001mehta.github.io/ng-x-daterangepicker/)
or [Plunker](https://run.plnkr.co/plunks/BtKrOwY8nNLMIdAikubM/) to how to consume this module

### Usage
Import DaterangepickerModule into your module as following

```ts
import { NgModule } from '@angular/core';
import { AppComponent } from './app.component';
import { BrowserModule } from '@angular/platform-browser';
import { DaterangepickerModule } from 'ng-x-daterangepicker';
@NgModule({
	imports: [BrowserModule, DaterangepickerModule],
	declarations: [ AppComponent ],
	bootstrap: [AppComponent]
})
export class AppModule {
	
}
```

### options
```js
{
	format: 'date format'
	startDate: 'Default start date'
	endDate: 'default end date'
	minDate: 'default minimum date not including this date'
	maxDate: 'default maximum date not including this date'
	inactiveBeforeStart: 'blurs all dates before selected start date'
	autoApply: 'removes apply and cancel buttons and applies as soon as user selects end date'
	showRanges: 'set to true if you want to see the predefine ranges'
	preDefinedRanges: 'custom ranges if you want to define your own ranges'
	noDefaultRangeSelected: 'if set to true all input boxes will be blank when the rangepicker is loaded'
}
```
And more options are on the way...
All dates are suppossed to be string and in format as you are passing.
You can also use

```ts
import { Options } from 'ng-x-daterangepicker';
```
class for passing options to the component.

## Events

Subscribe to rangeSelected event as 

```html
<date-range-picker [class]="'col-md-12 form-control'" [options]="daterangepickerOptions" (rangeSelected)="rangeSelected($event)"></date-range-picker>
```
the event listener will receive a javscript object conaining 
```js
{
	start: 'moment object representing start date selected by user'
	end: 'moment object representing end date selected by user'
}
```

### How pass options to the component
The input box automatically takes class of the date-range-picker tag

```ts
import { Component } from '@angular/core';

@Component({
	selector: "my-datepicker-demo",
	template: `
		<date-range-picker class="col-md-4" [options]="daterangepickerOptions" class="col-md-4">
		</date-range-picker>
	`
})
export class AppComponent{
	daterangepickerOptions = {
		startDate: '09/01/2017',
		endDate: '09/02/2017',
		format: 'DD/MM/YYYY'
	}
}

```

Please let me know if your are facing any issues [here](https://github.com/nikhil-001mehta/ng-x-daterangepicker/issues)
