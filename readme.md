### Introduction

Quick scratch Vectors and Quaternions for PlayCanvas to avoid constant definition
of oddly named local variables and subsequent bugs!

### Installation

```language-shell
npm install --save playcanvas-working-vectors
```

### Usage

```language-javascript
import {V, Q} from 'playcanvas-working-vectors'

...

this.entity.setLocalPosition(V(this.entity.getLocalPosition()).sub(this.enemy.getPosition())); 


let rotation = Q(this.entity.getRotation()).mul(this.entity.getRotation());

let rotation = Q().fromToRotation(this.entity.up, hit.normal);

let vector = V(0,0,distance).mul(this.entity.getRotation()); 

```

### Notes

There are 2048 scratch quaternions and vectors used in a rolling buffer, allocation of more than
this before a function completes will cause them to be overwritten.  **Values are for working
purposes only and should not be stored between frames**.

### Requirements

Requires PlayCanvas Engine to be running on the page.  Uses ES6/Babel/PlayCanvas template.
