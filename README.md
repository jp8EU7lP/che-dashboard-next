# About Eclipse Che Dashboard

This is the first step to implement a new Eclipse Che Dashboard.

## Requirements

- Node.js `v10.x.x` and later.

## Quick start

```sh
docker build . -f apache.Dockerfile -t quay.io/che-incubator/che-dashboard-next:next
```

## Running

Install all dependencies:

```sh
yarn
```

and start dev-server:

```sh
yarn start
```

The development server serves the project on [http://localhost:3000](http://localhost:3000).
By default it proxies all API requests to [che.openshift.io](https://che.openshift.io). You can change this behavior providing your own proxy target url and port using the following command as an example:

```sh
yarn start --env.server=https://che-che.192.168.99.100.nip.io  --port=3333
```

For better debugging experience you need to have React and Redux Developer Tools installed in your browser.

## License tool

It uses [dash-licenses](https://github.com/eclipse/dash-licenses) to check all dependencies (including transitive) to be known to Eclipse IPZilla or ClearlyDefined. It generates `.deps/dev.md` and `.deps/prod.md` that contains such information.

Firstly, build the license-tool dockerfile:

```sh
yarn licenseCheck:prepare
```

and then run the license-tool:

```sh
yarn licenseCheck:run
```

## License

Che is open sourced under the Eclipse Public License 2.0.
