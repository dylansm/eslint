## Docker eslint stuff

Docker eslint executable will just have eslint and none of the other dependencies, which should be installed locally in each project.

First initialize npm package, if necessary:

    docker run --rm -it -v $PWD:/home/app -w /home/app -u node node:alpine npm init -y

Then install packages as needed.


#### Common React linting libraries

    npm install --save-dev eslint-config-recommended eslint-config-airbnb eslint-plugin-jsx-a11y eslint-plugin-import eslint-plugin-react eslint-plugin-react-hooks


#### Common JS linting libraries

    npm install --save-dev eslint-config-recommended eslint-config-airbnb eslint-plugin-jsx-a11y eslint-plugin-import

---

Run this for a react project with src dir:

    docker run -it --rm --name vim-ale-eslint -v $(pwd):/data dylansm/eslint --ext js,jsx ./src

(Pass --ext js,jsx to include both extensions)

Or this for plain-old-JS project:

    docker run -it --rm --name vim-ale-eslint -v $(pwd):/data dylansm/eslint --ext js .
