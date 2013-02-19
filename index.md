#How does it work?

We use grunt to make the build super simple.

```sh
npm install #install dependencies

grunt #default task is live-reload
```

Under the hood, grunt is doing a couple things. Firstly, it is initiating a live-reload session. This is a server that will notify the browser when changes are made.

Secondly, it is creating a static server on port `9001`. We take advantage of [Connect's](http://www.senchalabs.org/connect/) ability to add middleware so that the JS dependency we need in the markdown is completely transparent.

Lastly, we use [regarde](http://www.senchalabs.org/connect/) to watch for changes with the markdown content and then run a home-brewed version of [grunt-markdown](https://github.com/stephenvisser/grunt-markdown) to build.

#What can it do?

- You can use Github-Flavoured Markdown (GFM). 
- Highlight.js does the syntax-highlighting, just drop in the CSS that you want to use.
- Edit the template.html file to change the wrapper. The wrapper just needs to have the line `<%=content%>` somewhere in it. (Uses grunt-templating styles)
- Add html directly anywhere you want, just make sure that it is separated by a newlines so markdown can format everything correctly.

__Enjoy...__