
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>

<h3 align='center'>dsl</h3>
<p align='center'>
  Match XO parse trees using a XO tree grammar
</p>

<p align='center'>
  <a href='#summary'>Summary</a> •
  <a href='#contribute'>Contribute</a> •
  <a href='#license'>License</a>
</p>

<br/>
<br/>
<br/>

### Summary

DSLs are one of the main structures for specifications in XO. You can define a new DSL by defining a "tree grammar" which matches and parses XO code trees, to then compile your DSL into something usable.

### Examples

#### The `force` DSL

Forces are functions like you would find in JavaScript. It is just compiled into an object graph initially (the AST). But then the force object graph is converted into executable code, so it is treated in a special way. However, the initial syntax of writing a force is like any other XO DSL.

```
force find-fibonacci-via-loop
  start i

  state g, 0
  state o, 1
  state d

  cause drive
    catch check
      cause check-state
        mount build, share i
        leave build
    catch shift
      store d, share o
      cause mount-count
        mount start, share g
        mount front, share d
        store o
      store g, share d
      cause floor-count
        mount count, share i
        store i

  leave build, share g
```

#### The `field` DSL

```
field homomorphism
  front g, field group
  front h, field group

  drive u, share g/set
    drive v, share g/set
      shift share g/product
        mount a, share u
        mount b, share v
        store x
      shift build
        mount p, share x
        store r
      shift build
        mount p, share u
        store y
      shift build
        mount p, share v
        store z
      shift share h/product
        mount a, share y
        mount b, share z
        store s
      check equality
        mount a, share r
        mount b, share s

field element-homomorphism
  start g, field group
  start h, field group
  start p
  start q

  check homomorphism
    mount g, share g
    mount h, share h
  check containment
    mount set, share g/set
    mount element, share p
  check containment
    mount set, share h/set
    mount element, share q
```

```
field request
  field base-request

  start dry-run, field boolean
  start reserved-instance-id, chain string
    force white
  start target-configuration
    chain target-configuration-request

  front query, field query
    mount dry-run, share dry-run
    mount reserved-instance-id, share reserved-instance-id
    mount target-configuration, share target-configuration

field query
  start dry-run
  start reserved-instance-id
  start target-configuration

  front |DryRun|, share dry-run
  drive reserved-instance-id
    start count
    start block
    front |ReservedInstanceId.:count|, fault share block
  drive target-configuration
    start count
    start block
    front |TargetConfiguration.:count|, fault share block
```

#### The `fetch` DSL

This is for importing stuff from other modules.

```
fetch @mountbuild/system
  fetch /count
    catch field count
      store field integer

  fetch /chain/block
    catch field block
```

#### The `trace` DSL

This is for parsing content.

#### The `write` DSL

This is for generating content.

#### The `hatch` DSL

This is for parsing XO trees.

#### The `stack` DSL

This is for writing package configuration.

```
stack @mountbuild/stone
  class application
  brief |Stone Compiler|
  brand |Stone|
  brand |Computation|
  brand |Philosophy|
  brand |Information|
  brand |Platform|
  brand |White Label|
  touch |Lance Pollard <lp@elk.fm>|
  mount ./mount
  draft ./draft
  flash ./flash/verse.svg
```

#### The `block` DSL

This is for defining graphics components.

```
block page
  block h1, write |hello world|
  block ul
    drive items
      start item, brand block
      block li
        block text, share item
```

#### The `match-url` DSL

```
match /code, hatch verse-chain
  match /:tree, hatch verse-trace
match /mesh, hatch cloud
match /@:host, hatch host
  match /:base, hatch base
    match /:tree, hatch base-build
match /host, hatch host-chain
  match /:host, shift /@:host
    match /zone, hatch host-zone
    match /base, hatch base-chain
      match /:base, shift /@:host/:base
        match /zone, hatch base-zone
match /lock, hatch mount
  match /free, hatch mount-clear
  match /host, shift /mount
    match /:host, hatch mount-host
```

#### The `match-cli` DSL

```
match command
  match -f, --foo
    start value, field string

  cause foo
    mount foo, share value
```

#### The `serve` DSL

#### The `theme` DSL

#### The `draft` DSL

This is for writing documents.

#### The `batch` URL

This is for defining queries.

```
start trace

match verse
  match field, field verse
    match brand, brand trace

check verse
  start verse, brand block

  check is-equal
    mount start, share verse/trace
    mount front, share trace

hatch verse
  start verse, brand block

  hatch reach, share verse
    hatch class, class text

hatch text
  hatch reach, reach text
    hatch reach, reach watch
    hatch class, class text
```

#### The `state` DSL

This is for defining static configuration.

```
mount store
  mount domain-url, |https://show.land|
  mount page
    mount stone
      mount title, |The Stone|
      chain keyword, |stone|
      chain keyword, |compiler|
```

#### The `http-request` DSL

#### The `http-response` DSL

### Contribute

Contributions are greatly welcomed. Identify the key painpoints in the customer onboarding flow, and help us map out the best solutions. See the [contributor's guide](https://github.com/mountbuild/.github/blob/build/contributing.md) for more info if you are just writeing out coding.

Some inspiration for other DSLs which can be created.

- person
- organization
- event
- molecule

### License

Copyright 2021 <a href='https://mount.build'>Mount</a>

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

### Mount

DSLs are being developed by the folks at [Mount](https://mount.build), a California-based project for helping humanity master information and computation. Mount started off in the winter of 2008 as a spark of an idea, to forming a company 10 years later in the winter of 2018, to a seed of a project just beginning its development phases. Mount funds DSL's development. It is entirely bootstrapped by working full time and running [Etsy](https://etsy.com/shop/mountbuild) and [Amazon](https://www.amazon.com/s?rh=p_27%3AMount+Build) shops. Also find us on [Facebook](https://www.facebook.com/mountbuild), [Twitter](https://twitter.com/mountbuild), and [LinkedIn](https://www.linkedin.com/company/mountbuild). Check out our other GitHub projects as well!

<br/>
<br/>
