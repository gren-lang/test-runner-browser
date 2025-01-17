# Gren Browser Test Runner

This package allows you to execute [Gren](https://gren-lang.org/) tests and output the results in the browser.

See [`gren-lang/test-runner-node`](https://packages.gren-lang.org/package/gren-lang/test-runner-node/version/latest/overview) if you want to run your tests on node.

To define the actual tests, you'll need to use the [`gren-lang/test`](https://packages.gren-lang.org/package/gren-lang/test/version/latest/overview) package.

## Quick start

Initialize a gren program:

```sh
mkdir tests
cd tests
gren init
```

Install the necessary packages:

```sh
gren package install gren-lang/test
gren package install gren-lang/test-runner-browser
```

Create a `src/Main.gren` with your tests:

```elm
module Main exposing (main)

import Expect
import Test exposing (describe, test)
import Test.Runner.Browser exposing (Program, run)

main : Program
main =
    run <|
        describe "All tests"
            [ test "Failing test" <| \_ ->
                Expect.equal True False
            ]
```

Compile and open the resulting HTML file in your browser:

```
gren make src/Main.gren
open index
```

If you have any questions, please [reach out](https://gren-lang.org/community)!
