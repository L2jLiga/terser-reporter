# terser-reporter
An application to visualise mapping from result to source at every pass in real time.

## Motivations:

Currently Terser doesn't have any utilities to debug things. Debug process looks like create file, run Terser with defaults, see results, change one or more options, run again and so on..

## Goals

- Visualize minification process to make debugging easier
- Show output changes when options were changed on the go
- Ability to get information for creating meaningful issue

## Interface may contains:

- input text area
- output text area
- switcher between compression stages (may be between passes specified)
- configurator for Terser options

## UX notes:
- left part contains textarea for user input
- center part contains text area (read only) with drop-down ahead for switching between stages (Terser passes)
- right part contains settings to configure Terser on the go
- hovering elements in output causes highlighting related part in input
- in case if error happened then red popup shown over output with error details

## Technical notes:

- Terser already has repl, hence we can see how to integrate it
- passes option should work different comparing to other Terser options: passes defines how many times to run Terser (to get results and mappings of each stage) instead of passing passes as Terser option
- tba

## Technologies stack:

### Terser

Goal of project is to make it easier to understand and debug what happening with code minificating by Terser

### Angular as UI framework

Angular is very powerful framework. It has many tools out-of-the-box like schematics.

### NgRx as state manager

We can use it as state manager, for example, in component we dispatch debounced input event with, then it do transformation in service (Angular workers) and dispatch result (easier to handle error)

### GH pages

As far as Terser can done things on client side we don't need to create any Backend.
