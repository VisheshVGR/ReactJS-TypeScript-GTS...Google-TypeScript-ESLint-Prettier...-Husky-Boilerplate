# ReactJS + TypeScript + GTS (Google TypeScript + ESLint + Prettier) + Husky Boilerplate

## To use this **Boilerplate** follow below steps:

1. Download and open repository in code editor.
2. Install all packages using ```npm install```.
3. Setup Husky (*to run pre-checks before commiting to github*) -
   1. Initialize git in repository if not already by running ```git init```.
   2. Run ```npm run prepare```.
   3. Add a hook 
        ```
        npx husky add .husky/pre-commit "npm test"
        git add .husky/pre-commit
        ```
   4. Optional -> Change ```./.husky/pre-commit``` from
        ```
        #!/usr/bin/env sh
        . "$(dirname -- "$0")/_/husky.sh"

        npm test
        ```
        to
        ```
        #!/usr/bin/env sh
        . "$(dirname -- "$0")/_/husky.sh"

        npm run fix
        ```
        to check linting and format errors and fix them.


## To Build from scratch follow below steps:

1. [Create ReactJS app with TypeScript](https://create-react-app.dev/docs/adding-typescript/).
    ```
    npx create-react-app my-app --template typescript
    ```
2. [Install Google GTS TypeScript style guide, formatter, and linter](https://github.com/google/gts).
    ```
    npx gts init
    ```
3. [Install Husky](https://www.npmjs.com/package/husky).
    ```
    npm install husky --save-dev

    npm pkg set scripts.prepare="husky install"
    npm run prepare
    
    npx husky add .husky/pre-commit "npm test"
    git add .husky/pre-commit

    git commit -m "Keep calm and commit"
    # `npm test` will run
    ```
-------------------------------------------------------