# Secret Share


## Development
You need a recent version of Node.js and NPM installed. Tested with:

* v4.1.0
* v5.7.0
* v7.5.0

### Quickstart
1. Clone the git repository
2. `npm install`
3. `npm run dev`

For development use `npm run dev`. This does two things: it starts an electron instance with development features enabled, and it starts a webpack dev server. The dev server is to enable 'hot module reloading', which means that changes to the source on your file system will be reflected in the running application code in real time.

### Testing

- To run the unit tests: `npm run test`
- For development you might enjoy the continuously updating tests: `npm run test-watch`
- The end-to-end integration suite can be run with `npm run test-e2e`. Note that this runs agains built code, so an `npm run build-app` is prudent and/or necessary.

## Building

### Linux

Linux packages are built in a Vagrant-based virtual environment, so they can be
built on either Linux or Mac OS X. You will need to install the following
prerequisites for the build environment:

1. [Vagrant](https://www.vagrantup.com/)
2. [Ansible](https://docs.ansible.com/ansible/intro_installation.html). We
   recommend using an Ansible version >= 2.2.1.

Once you have the prerequisites installed, you should be able to

```
make build
```

to create a VM and run a full build of the Linux packages.

### OS X

To package up the app for your current platform (e.g. OS X):

```
npm run dist
```

Note that this will run `build-app` so there's no need to run that beforehand.

Packages will be stored in `dist/<platform>`.

### Code Signing

Code signing is handled automatically by the `electron-builder` package. All you should need to do is add the signing identity through xcode, and electron-builder will discover it automatically. See [Apple documentation](https://developer.apple.com/library/content/documentation/IDEs/Conceptual/AppDistributionGuide/MaintainingCertificates/MaintainingCertificates.html) and [electron-builder documentation](https://github.com/electron-userland/electron-builder/wiki/Code-Signing) for more info.
