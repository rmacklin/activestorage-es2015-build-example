This is a demo repository to show the benefits of publishing [activestorage]'s
source code along with its compiled code.

It is based on the [webpack-esnext-boilerplate] repository which demostrates the
techniques described in Philip Walton's article:
[Deploying ES2015+ Code in Production Today].

Switching this app from depending on activestorage's compiled code to its source
code shrinks this app's javascript bundle for modern browsers shrinks from `19K`
to `14K`.

To verify this result:

1. Clone the repository and install its dependencies:
   ```sh
   git clone git@github.com:rmacklin/activestorage-es2015-build-example.git
   cd activestorage-es2015-build-example
   npm install
   ```

2. Check out the commit which uses activestorage's compiled code and build the
   app:
   ```sh
   git checkout 6e15aea5c4d6fea33ac781e99b97d7ee59bcb5be
   NODE_ENV=production npm run build
   ```
   The compiled bundle (`public/main-db52432ca7.js`) is 19260 bytes.

3. Check out the commit which uses activestorage's source code and build the
   app:
   ```sh
   git checkout 0cab0106919d53fc545f9f0aeadaa7ed5065481f
   NODE_ENV=production npm run build
   ```
   The compiled bundle (`public/main-c9f6c71d22.js`) is 14692 bytes.

[activestorage]: https://github.com/rails/rails/tree/v5.2.0.rc1/activestorage
[Deploying ES2015+ Code in Production Today]: https://philipwalton.com/articles/deploying-es2015-code-in-production-today/
[webpack-esnext-boilerplate]: https://github.com/philipwalton/webpack-esnext-boilerplate
