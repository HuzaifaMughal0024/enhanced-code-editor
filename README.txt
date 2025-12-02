Step 1:
Upload the contents of the panelfiles folder.

Step 2:

Open the (/var/www/pterodactyl/webpack.config.js) file and add the following lines:

Below:
            {
                test: /\.mjs$/,
                include: /node_modules/,
                type: 'javascript/auto',
            },
Add:
            {
                test: /\.m?js$/,
                include: /node_modules\/@?monaco-editor/,
                type: 'javascript/auto',
                loader: 'esbuild-loader',
            },

Step 3:
Use the following commands to install dependencies and build the project:

yarn add esbuild-loader
yarn add monaco-editor@0.43.0 @monaco-editor/react@4.4.6 monaco-editor-webpack-plugin

yarn build:production
