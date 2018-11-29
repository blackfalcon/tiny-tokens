# My first npm package

This is nothing but a really simple example of building a npm package and outlining the steps needed for building, deploying, and publishing a npm package of codes.

=)

### What it takes to build a npm package

npm is one of those things that make people go O_O

"How do I make a npm package and publish it? It's so scary!!!"

In reality, it's almost too simple compared to other things we have done in the past. I'm looking at you Ruby gems O_O! So, here is the list of things you must have to publish your very own npm package.

1. A `package.json` file
1. Some code

That's it really. While it is nice to push all the codes to something like Github, it's not required. Simply have a directory of some code, any code, and in the directory from which you intent to create the package from have a `package.json` file.

### What's in a package.json file?

See [here](https://docs.npmjs.com/files/package.json) for a full description of the `package.json` API.

This is as simple as it gets. Having the `name`, `description`, `version`, `author` and `license` keys in the json blob is a great start and more than enough to get this ball rolling.

```
{
  "name": "@blackfalcon/tiny-tokens",
  "description": "Token all the things",
  "version": "0.1.2",
  "author": "A dude with codes",
  "license": "MIT"
}
```

If you did have a Git repo, it's good to link the reference with the additional config

```
{
  "repository": {
    "type" : "git",
    "url" : "https://github.com/npm/cli.git"
  }
}
```

What's up with `@blackfalcon/` anyway? Well, this is a name space. For the vast majority of early npm time people put all kinds of things into the npm registry and named them at the root level. So when the first dev published _pixel_, that was it, 59naga won. No one can ever have the name of _pixel_ for their package ... but! You can! How? Easy, namespace it.

```
@blackfalcon/pixel
```

Boom! Now I can have that name too! And you can too! It's a great pattern and you should use it.

### Account and logging in

Prior to publishing you need to log into your npm account from the command line.

### Publish

Ok, now that we have a directory with some code and a `package.json` file we need to publish it to npmjs.com in order for the world to see your awesome stuff. But there is a small problem. Since I told you to use your username as a namespace with the name of the package, when simply publishing the code, it will be assumed to be private.

Now you may want this, but you have to pay for that option with npmjs.com. But there is a way around this. Using the `--access=public` flag with the publish command, you are willing. All the awesome of namespacing without the cost of keeping things private. But who keeps things private anyway?

```
npm publish --access=public
```

One that is done, go see your new package and profit!
