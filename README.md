# SvelteJS

## Intro

* Compiler for creating **reactive** web apps and interfaces
* can be used for small parts of a site, or entirely(SPA)
* no extra scripts or libraries are shipped to production
* often results in a faster running website
* it compiles the code into js during development and it doesnt have any extra code in prod code

## Installation
* npm i -g degit
* degit sveltejs/template myproject
  
## Files

* src folder - all src code
  * main.js - svelte uses to kickstart project
  * app.svelte - root component of project Note: file extension is svelte
* package.json - list all dependencies -- Note: all the svelte dependencies are dev dependencies
* rollup.config.js - a webpack kinda file, watches, bundles, etc
* public - svelte outputs prod code

## Start

* components are building block of appln
* like modal, header, footer, etc
* 2 way data binding using bind:attribute syntax
* {#each people as person (person.id)}
      <div>
        <h4>{person.name}</h4>
        <p>{person.age} years old, {person.beltColor} belt.</p>
        <button on:click={() => handleClick(person.id)}>delete</button>
      </div>
    {:else}
      <p>There are no people to show...</p>
    {/each}

* Slots
  * to pass content as html