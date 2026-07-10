# clojure-action

A basic action to install Java, Clojure, and Babashka and set up
caching for these.

## Usage

Add the following in your workflow, and `java`, `clojure`, and `bb` will
be available for your workflow steps.

```yaml
  - uses: jomco/clojure-action
    with:
      java-version: 25
```

## Inputs

This action is configurable with the following inputs:

- `java-version` and `java-distribution`

  Inputs for
  [actions/setup-java](https://github.com/actions/setup-java) (for
  defaults, see [action.yml](./action.yml)).

- `clojure-version` and `babashka-version`

  Clojure and Babashka versions to use (for defaults, see
  [action.yml](./action.yml)).

- `babashka-arch`

  The architecture variant to install for Babashka (defaults to
  `linux-amd64`).

- `m2-cache-key`
  Partial key to use for caching the `~/.m2` directory.  This value
  defaults to `m2` and is combined with `${{runner.os}}`, the versions
  above, and suffixed with the current date.  A fallback restore key is
  supplied without the date suffix.

- `install-prefix`

  Installation prefix directory for Clojure and Babashka (defaults to
  `~/clojure-action`).

## Motivation

Why not use
[DeLaGuardo/setup-clojure](https://github.com/DeLaGuardo/setup-clojure)?
It is too complex.  This action aims to be as simple as possible.

## License

Copyright (c) 2026 Jomco B.V.

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
