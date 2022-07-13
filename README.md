# Intro

This project contains TailwindCSS customizations mainly for my own use. You are free to adopt and adapt to your own situation. 

## 1. Tailwind Custom Animations

The animations are inspired by https://animate.style and others. 
This library provides a integration point for some of the animations with tailwind. 

### Examples 

Check out [animate.style](https://animate.style) for effects of the animations. 

Note: Not all [animate.style](https://animate.style) animations are included. This project only contains animations I personally use plus some others not on [animate.style](https://animate.style). 

### How To Use

In `tailwind.config.js` do: 
```js
module.exports = {
  ...
  theme: {
    ...
    extend: {
      ...
      ...require('./_tailwindcss/_tw-animations'), // Update path to fit your setup
    }
  }
}
```

Then on any element that you wish to animate, give it a class e.g. `animate-tada`.

## 2. Tailwind Plugin

The plugin adds the following Components to tailwind: 

- btn
- btn-outline
- btn-group
- btn-[color name]
- btn-outline-[color name]
- divider-text

### Examples 

```html
<button class="btn btn-indigo">Submit</button>
```
<button class="demo btn btn-indigo">Submit</button>

```html
<button class="btn btn-outline-indigo">Home</button>
```
<button class="demo btn btn-outline-indigo">Home</button>

```html
<div class="flex btn-group">
  <input type="text" class="grow" placeholder="Search or Create A Room" value="game" />
  <button class="btn btn-outline-green grow-0">Join</button>
  <button class="btn btn-outline-cyan grow-0">Observe</button>
</div>
```
<div class="demo flex btn-group">
  <input type="text" class="grow" placeholder="Search or Create A Room" value="game" />
  <button class="btn btn-outline-green grow-0">Join</button>
  <button class="btn btn-outline-cyan grow-0">Observe</button>
</div>

```html
<div class="divider-text mx-8">
  <span class="bg-white p-1 font-bold text-gray-500">OR</span>
</div>
```
<div class="demo divider-text mx-8">
  <span class="bg-white p-1 font-bold text-gray-500">OR</span>
</div>

### How To Use 

Add to `tailwind.config.js`: 
```js
module.exports = {
  ...
  plugins: [
    ...,
    require('./_tailwindcss/_tw-components'), // Update path to fit your setup
  ]
}
```

<style>
  .btn {
    border-radius: 0.25rem;
    font-size: .875rem;
    font-weight: 500;
    line-height: 1.25rem;
    padding: 0.5rem 3rem;
    transition-duration: .15s;
    transition-property: color,background-color,border-color,-webkit-text-decoration-color;
    transition-property: color,background-color,border-color,text-decoration-color;
    transition-property: color,background-color,border-color,text-decoration-color,-webkit-text-decoration-color;
    transition-timing-function: cubic-bezier(.4,0,.2,1);
  }
  .btn-indigo {
    background-color: #6366f1;
    color: #fff;
  }
  .btn-indigo:hover {
    background-color: #4338ca;
  }
  .btn-outline-indigo {
    --tw-ring-offset-shadow: var(--tw-ring-inset) 0 0 0 var(--tw-ring-offset-width) var(--tw-ring-offset-color);
    --tw-ring-shadow: var(--tw-ring-inset) 0 0 0 calc(1px + var(--tw-ring-offset-width)) var(--tw-ring-color);
    --tw-ring-inset: inset;
    --tw-ring-opacity: 1px;
    --tw-ring-color: #6366f1;
    box-shadow: var(--tw-ring-offset-shadow),var(--tw-ring-shadow),var(--tw-shadow,0 0 #0000);
    color: #6366f1;
  }
  .btn-outline-indigo:hover {
    background-color: #6366f1;
    color: #fff;
  }
  .btn-group :not(:last-child) {
    border-bottom-right-radius: 0;
    border-right-width: 0;
    border-top-right-radius: 0;
  }
  .btn-group :not(:first-child) {
    border-bottom-left-radius: 0;
    border-top-left-radius: 0;
  }
  .btn-group .btn {
    padding: 0.5rem 1rem;
  }
  .flex {
    display: flex;
  }
  .grow-0 {
    flex-grow: 0;
  }
  .grow {
    flex-grow: 1;
  }
  .btn-outline-green {
    --tw-ring-offset-shadow: var(--tw-ring-inset) 0 0 0 var(--tw-ring-offset-width) var(--tw-ring-offset-color);
    --tw-ring-shadow: var(--tw-ring-inset) 0 0 0 calc(1px + var(--tw-ring-offset-width)) var(--tw-ring-color);
    --tw-ring-inset: inset;
    --tw-ring-opacity: 1px;
    --tw-ring-color: #22c55e;
    box-shadow: var(--tw-ring-offset-shadow),var(--tw-ring-shadow),var(--tw-shadow,0 0 #0000);
    color: #22c55e;
  }
  .btn-outline-green:hover {
    background-color: #22c55e;
    color: #fff;
  }
  .btn-outline-cyan {
    --tw-ring-offset-shadow: var(--tw-ring-inset) 0 0 0 var(--tw-ring-offset-width) var(--tw-ring-offset-color);
    --tw-ring-shadow: var(--tw-ring-inset) 0 0 0 calc(1px + var(--tw-ring-offset-width)) var(--tw-ring-color);
    --tw-ring-inset: inset;
    --tw-ring-opacity: 1px;
    --tw-ring-color: #06b6d4;
    box-shadow: var(--tw-ring-offset-shadow),var(--tw-ring-shadow),var(--tw-shadow,0 0 #0000);
    color: #06b6d4;
  }
  .btn-outline-cyan:hover {
    background-color: #06b6d4;
    color: #fff;
  }
  button {
    cursor: pointer;
    -webkit-appearance: button;
    background-color: initial;
    background-image: none;
    text-transform: none;
    margin: 0;
    text-indent: 0px;
    text-shadow: none;
    display: inline-block;
    text-align: center;
    align-items: flex-start;
  }
  input {
    border-radius: 0.5rem;
    border-color: transparent;
    border: 1px solid rgb(209 213 219);
    background-color: white;
    color: rgb(55 65 81);
    --tw-shadow: 0 1px 2px 0 rgb(0 0 0 / 0.05);
    --tw-shadow-colored: 0 1px 2px 0 var(--tw-shadow-color);
    box-shadow: var(--tw-ring-offset-shadow, 0 0 #0000), var(--tw-ring-shadow, 0 0 #0000), var(--tw-shadow);
    padding: 0.5rem 1rem;
  }
  input::placeholder {
    color: rgb(156 163 175);
  }
  div.demo {
    /* background-color: white; */
  }
  .divider-text {
    align-items: center;
    display: flex;
    justify-content: center;
    position: relative;
  }
  .divider-text:before {
    border: 0.5px solid #d3d3d3;
    content: "";
    position: absolute;
    width: 100%;
    z-index: -10;
  }
  .mx-8 {
    margin-left: 2rem;
    margin-right: 2rem;
  }
  .text-gray-500 {
    --tw-text-opacity: 1;
    color: rgb(107 114 128/var(--tw-text-opacity));
  }
  .font-bold {
    font-weight: 700;
  }
  .p-1 {
    padding: 0.25rem;
  }
  .text-gray-500 {
    --tw-text-opacity: 1;
    color: rgb(107 114 128/var(--tw-text-opacity));
  }
  .font-bold {
    font-weight: 700;
  }
  .p-1 {
    padding: 0.25rem;
  }
  .bg-white {
    --tw-bg-opacity: 1;
    background-color: rgb(255 255 255/var(--tw-bg-opacity));
  }
</style>