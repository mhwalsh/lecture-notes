##Grunt lecture notes

#### References:

- [http://gruntjs.com/](http://gruntjs.com/)
- [http://gruntjs.com/plugins](http://gruntjs.com/plugins)
- [https://www.youtube.com/watch?v=XJ5F-Auhato&list=PLoYCgNOIyGAB0_YBfdNP5oqAD98HtAQqL&index=7](https://www.youtube.com/watch?v=XJ5F-Auhato&list=PLoYCgNOIyGAB0_YBfdNP5oqAD98HtAQqL&index=7)
- [https://www.youtube.com/watch?v=TMKj0BxzVgw&list=PLoYCgNOIyGAB0_YBfdNP5oqAD98HtAQqL&index=8](https://www.youtube.com/watch?v=TMKj0BxzVgw&list=PLoYCgNOIyGAB0_YBfdNP5oqAD98HtAQqL&index=8)


#### Why you need a build system?
**From the Grunt site:** 

*In one word: automation. The less work you have to do when performing repetitive tasks like minification, compilation, unit testing, linting, etc, the easier your job becomes. After you've configured it through a Gruntfile, a task runner can do most of that mundane work for you—and your team—with basically zero effort.*

*The Grunt ecosystem is huge and it's growing every day. With literally hundreds of plugins to choose from, you can use Grunt to automate just about anything with a minimum of effort.*

- Do repetitive tasks. Like concatenation of javascript or css
- Run utilities: JSHint, Uglify (minify)
- Run live reloads, when we save
- Speed, of loading your non minified files is expensive. You want to load 1-3 js files. One file for your vendor code. One for your application code. Fewer file requests.
- Development work flow: smaller files well named, but still concatenated into one file. Less likely to conflict with this structure.

#### Common Build Systems
- Grunt - still the industry standard
- Gulp - very popular and new companies are starting to use

#### How to Install
[http://gruntjs.com/getting-started]()

[http://gruntjs.com/project-scaffolding]()

#### Joel's tool
This will copy a template to start out with into every project you run it in. So you don't have to start from scratch with your grunt file.

[https://github.com/joeltmiller/grunt-init-gruntfile](https://github.com/joeltmiller/grunt-init-gruntfile)

#### Project specific
```
$: npm install grunt --save-dev
```
and any plugins:

```
$: npm install grunt-contrib-<name> --save-dev
```

1. uglify - minification 
	- w/ simple and a function
	- note that this and the mangle false. must have the [] in your angular to have mangle true.
2. watch - watch files for changes, run tasks on them
	- watch our client file and run uglify
3. show default
4. copy - npm install bootstrap, run copy
5. jshint - change some js to show linter error, run with jshint and as default. Default runs in order, if there are errors for jshint it wont get to watch. Thus, watch should be last.

Others to look into:
6. concat - show with two css files
7. cssmin