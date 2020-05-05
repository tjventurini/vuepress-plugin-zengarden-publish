# VuePress Plugin Zengarden Publish

Adds the `publish` attribute to the frontmatter of each page.

## Installation

```bash
npm install vuepress-plugin-zengarden-publish
# or
yarn add vuepress-plugin-zengarden-publish
```

## Usage

In your `config.js` or `index.js` files of your VuePress configuration, add the following.

```javascript
['zengarden-publish']
```

Now you should have the `publish` flag set in the `frontmatter` of all your pages. 

You can set the `publish` flag your self, the plugin will not overwrite the value if it is already set.

## Configuration

Per default we use the `date` attribute of a pages `frontmatter` to determine if a page should be published. If you need to change this behavior, then you can just overwrite the used function like so.

```javascript
['zengarden-publish', {
    publish: function(page) {
        // this is the default logic used
        return dayjs().format('YYYY-MM-DD') >= dayjs(page.frontmatter.date).format('YYYY-MM-DD')
    }
}]
```

You will get the full page object so the setup is very flexible. Also as you can see.


