### steamer-example

steamer starter kit example

#### How to write a starter kit

* Create starter kit config
You need to create a config file under `.steamer` folder. If your starter kit is called `steamer-example`, the config file name should be `steamer-example.js`.

The content of the config should be the options you need to specify in starter kit config. For example:

```
module.exports = {
    "files": [
        "src",
        "tools",
        "README.md"
    ],
    options: [
    	{
            type: 'input',
            name: 'webserver',  // host for html
            message: 'html url(//localhost:9000/)'
        },
        {
            type: 'input',
            name: 'cdn',	// host for cdn, e.g. js, css, png, etc.
            message: 'cdn url(//localhost:8000/)'
        },
    	{
            type: 'input',
            name: 'port',	// development port
            message: 'development server port(9000)'
        },
        {
            type: 'input',
            name: 'route', // development proxy router
            message: 'development server directory(/news/)'
        }
    ]
};
```

We use [inquirer](https://github.com/sboudrias/Inquirer.js) to read such options, for more details, please check the documentation.

`files` field is files or folders needed to be copied to the target folder.

`src` and `tools` are must. `src` is the folder for source code and `tools` is the folder for building tools.


* Specify a main file in package.json

You need to speicify the config file as the `main` file in package.json

```
"main": "./.steamer/steamer-example.js",
```

#### Develop
```
// link you module to global path, then you can use steamer xxx directly
npm link

// when you finish testing, please unlink the module
npm unlink steamer-xxx

```
